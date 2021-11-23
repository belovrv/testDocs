<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="remove" title="remove" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="2104a46e">Returns <code _o="100" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="b25a295e">DataFrame</code> without selected columns.</p>
<code _o="139" _o-sc="7,0" _o-l="6" _o-e="8,3" _o-tl="-1" _o-s="6,0" style="block" _o-cl="0" id="58115268" lang="kotlin">remove { columns }
</code>
<p _o="173" _o-sc="10,0" _o-l="10" _o-e="11,0" _o-tl="-1" _o-s="10,0" _o-cl="0" id="f8a7d23">See <a _o="177" _o-sc="10,5" LinkStatus="UNKNOWN" _o-l="10" _o-e="10,42" _o-tl="-1" _o-s="10,4" href="ColumnSelectors.md" _o-cl="4" id="3887e8fd">Column Selectors</a></p>

<tabs id="3b93c247">
<tab id="a69c620f" title="Properties">
<code _o="269" _o-sc="17,0" _o-l="16" _o-e="18,3" _o-tl="-1" _o-s="16,0" style="block" _o-cl="0" id="67bf1714" lang="kotlin">df.remove { name and weight }
</code>
</tab>
<tab _o="314" _o-sc="20,6" _o-l="20" _o-e="22,0" _o-tl="5" _o-s="20,0" _o-cl="0" id="5b48f910" title="Accessors">
<code _o="346" _o-sc="24,0" _o-l="23" _o-e="28,3" _o-tl="61" _o-s="23,0" style="block" _o-cl="0" id="619fd072" lang="kotlin">val name by columnGroup()
val weight by column&lt;Int?>()

df.remove { name and weight }
</code>
</tab>
<tab _o="447" _o-sc="30,6" _o-l="30" _o-e="32,0" _o-tl="5" _o-s="30,0" _o-cl="0" id="5e7c3786" title="Strings">
<code _o="477" _o-sc="34,0" _o-l="33" _o-e="35,3" _o-tl="-1" _o-s="33,0" style="block" _o-cl="0" id="444bfe50" lang="kotlin">df.remove("name", "weight")
</code>
</tab></tabs>

</topic>