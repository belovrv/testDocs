<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="schema" title="schema" _md-based="true"> 
<p _o="93" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="5609ca7e">Returns <code _o="101" _o-sc="4,9" _o-l="4" _o-e="4,25" _o-tl="-1" _o-s="4,8" _o-cl="8" id="af4f685e">DataFrameSchema</code> object with <code _o="131" _o-sc="4,39" _o-l="4" _o-e="4,49" _o-tl="-1" _o-s="4,38" _o-cl="38" id="cd5668a8">DataFrame</code> schema description. It can be printed to see column structure.</p>
<p _o="207" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="b23b4c6e"><a _o="207" _o-sc="6,1" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,43" _o-tl="-1" _o-s="6,0" href="DataColumn.md#columngroup" _o-cl="0" id="10b2a7fa"><code _o="208" _o-sc="6,2" _o-l="6" _o-e="6,15" _o-tl="-1" _o-s="6,1" _o-cl="1" id="5376058f">ColumnGroups</code></a> are marked by indentation:</p>

<code _o="299" _o-sc="11,0" _o-l="10" _o-e="12,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="141c3b0" lang="kotlin">df.schema()
</code>

<p _o="339" _o-sc="16,0" _o-l="16" _o-e="17,0" _o-tl="-1" _o-s="16,0" _o-cl="0" id="6e69276e">Output:</p>
<code _o="348" _o-sc="19,0" _o-l="18" _o-e="26,3" _o-tl="-1" _o-s="18,0" style="block" _o-cl="0" id="49ee64da" lang="text">name:
    firstName: String
    lastName: String
age: Int
city: String?
weight: Int?
isHappy: Boolean
</code>
<p _o="463" _o-sc="28,0" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="c43b0f4e"><a _o="463" _o-sc="28,1" LinkStatus="UNKNOWN" _o-l="28" _o-e="28,43" _o-tl="-1" _o-s="28,0" href="DataColumn.md#framecolumn" _o-cl="0" id="3064766e"><code _o="464" _o-sc="28,2" _o-l="28" _o-e="28,15" _o-tl="-1" _o-s="28,1" _o-cl="1" id="d0c0791">FrameColumns</code></a> are marked with <code _o="523" _o-sc="28,61" _o-l="28" _o-e="28,63" _o-tl="-1" _o-s="28,60" _o-cl="60" id="1a4cdb70">*</code>:</p>

<code _o="556" _o-sc="33,0" _o-l="32" _o-e="34,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="6867796" lang="kotlin">df.groupBy { city }.schema()
</code>

<p _o="613" _o-sc="38,0" _o-l="38" _o-e="39,0" _o-tl="-1" _o-s="38,0" _o-cl="0" id="7136f350">Output:</p>
<code _o="622" _o-sc="41,0" _o-l="40" _o-e="50,3" _o-tl="-1" _o-s="40,0" style="block" _o-cl="0" id="e3cc2d03" lang="text">city: String?
group: *
    name:
        firstName: String
        lastName: String
    age: Int
    city: String?
    weight: Int?
    isHappy: Boolean
</code>
</topic>