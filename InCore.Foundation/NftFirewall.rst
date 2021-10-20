
.. _object_NftFirewall:


:index:`NftFirewall`
--------------------

Description
***********

The NftFirewall object represents a network firewall configuration and can be used to implement all kinds of networking and packet filtering scenarios. It uses `nftables <https://nftables.org/projects/nftables/index.html>`_, a modern firewall software solution provided in the Linux kernel. Consequently :ref:`NftFirewall <object_NftFirewall>` and all subobjects (such as :ref:`NftTable <object_NftTable>`, :ref:`NftChain <object_NftChain>` and :ref:`NftRule <object_NftRule>`) follow the nftables concepts and semantics while providing QML syntax including dynamic updates on any property change. See the `nftables Wiki <https://wiki.nftables.org/>`_ for more information on how nftables-based firewalling and packet filtering works.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`externalRulesetFile <property_NftFirewall_externalRulesetFile>`
  * :ref:`ruleset <property_NftFirewall_ruleset>`
  * :ref:`tables <property_NftFirewall_tables>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`flush() <method_NftFirewall_flush>`
  * :ref:`load() <method_NftFirewall_load>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`tablesDataChanged() <signal_NftFirewall_tablesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_NftFirewall_externalRulesetFile:

.. _signal_NftFirewall_externalRulesetFileChanged:

.. index::
   single: externalRulesetFile

externalRulesetFile
+++++++++++++++++++

This property holds a path to an external file containing the ruleset to load. If set, the :ref:`tables <property_NftFirewall_tables>` and :ref:`ruleset <property_NftFirewall_ruleset>` properties are ignored and the specified ruleset file is loaded instead.

:**› Type**: String
:**› Signal**: externalRulesetFileChanged()
:**› Attributes**: Writable


.. _property_NftFirewall_ruleset:

.. _signal_NftFirewall_rulesetChanged:

.. index::
   single: ruleset

ruleset
+++++++

This property holds the effective ruleset in nftables syntax which is being loaded and used.

:**› Type**: String
:**› Signal**: rulesetChanged()
:**› Attributes**: Readonly


.. _property_NftFirewall_tables:

.. _signal_NftFirewall_tablesChanged:

.. index::
   single: tables

tables
++++++

This property holds a list of tables containing chains and rules.

:**› Type**: :ref:`List <object_List>`\<:ref:`NftTable <object_NftTable>`>
:**› Signal**: tablesChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_NftFirewall_flush:

.. index::
   single: flush

flush()
+++++++





.. _method_NftFirewall_load:

.. index::
   single: load

load()
++++++




Signals
*******


.. _signal_NftFirewall_tablesDataChanged:

.. index::
   single: tablesDataChanged

tablesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`tables <property_NftFirewall_tables>` list itself emitted the dataChanged() signal.



.. _example_NftFirewall:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        id: app
    
        System {
            id: system
            Polling on cpuLoad { }
        }
    
        NftFirewall {
    
            NftTable {
                family: NftTable.IP
                name: "example"
    
                NftChain {
                    name: "incoming"
                    type: NftChain.Filter
                    hook: NftChain.Input
                    priority: NftChain.FilterPriority
                    policy: NftChain.Drop
                    rawRules: [ "ip protocol icmp icmp type { echo-request } accept" ]
                    NftRule { inputInterface: "lo"; statement.type: NftStatement.Accept }
                    NftRule { protocol: NftRule.Icmp; statement.type: NftStatement.Accept }
                    NftRule { connectionStates: NftRule.Established | NftRule.Related; statement.type: NftStatement.Accept }
                    // disable new SSH connections if system load is too high
                    NftRule {
                        connectionStates: NftRule.New
                        protocol: NftRule.Tcp
                        destinationPorts: 22
                        statement.type: system.cpuLoad < 1 ? NftStatement.Accept : NftStatement.Drop
                    }
                }
    
                NftChain {
                    id: proxy
                    enabled: app.commandLineArguments[0] === "proxy"
                    name: "transparentwebproxy"
                    type: NftChain.Nat
                    hook: NftChain.Postrouting
                    priority: NftChain.SourceNatPriority
                    policy: NftChain.Accept
                    NftRule {
                        protocol: NftRule.Tcp
                        sourceAddress: "192.168.19.1"
                        destinationPorts: [ 80, 443 ]
                        statement.type: NftStatement.Masquerade
                    }
                }
            }
    
            onRulesetChanged: console.log(ruleset)
        }
    }
    