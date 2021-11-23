<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="ungroup" title="ungroup" _md-based="true"> 
<p _o="93" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="8cf7416a">Replaces <code _o="102" _o-sc="4,10" _o-l="4" _o-e="4,22" _o-tl="-1" _o-s="4,9" _o-cl="9" id="ebbc9f1f">ColumnGroup</code> with its nested columns.</p>
<p _o="143" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="37dc1c2">Reverse operation to <a _o="164" _o-sc="6,22" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,38" _o-tl="-1" _o-s="6,21" href="group.md" _o-cl="21" id="f795021c">group</a></p>
<code _o="183" _o-sc="9,0" _o-l="8" _o-e="10,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="50f6b56f" lang="kotlin">ungroup { columns }
</code>
<p _o="218" _o-sc="12,0" _o-l="12" _o-e="13,0" _o-tl="-1" _o-s="12,0" _o-cl="0" id="b3b88b59">See <a _o="222" _o-sc="12,5" LinkStatus="UNKNOWN" _o-l="12" _o-e="12,42" _o-tl="-1" _o-s="12,4" href="ColumnSelectors.md" _o-cl="4" id="a7c91cad">column selectors</a></p>

<code _o="283" _o-sc="17,0" _o-l="16" _o-e="20,3" _o-tl="29" _o-s="16,0" style="block" _o-cl="0" id="f29eb3b0" lang="kotlin">// name.firstName -> firstName
// name.lastName -> lastName
df.ungroup { name }
</code>

</topic>