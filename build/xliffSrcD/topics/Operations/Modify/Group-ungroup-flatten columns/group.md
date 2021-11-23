<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="group" title="group" _md-based="true"> 
<p _o="91" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="ec703ef6">Group columns into <a _o="110" _o-sc="4,20" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,63" _o-tl="-1" _o-s="4,19" href="DataColumn.md#columngroup" _o-cl="19" id="98e71648"><code _o="111" _o-sc="4,21" _o-l="4" _o-e="4,35" _o-tl="-1" _o-s="4,20" _o-cl="20" id="dbc93bd0">ColumnsGroups</code></a>.</p>
<p _o="158" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="49e6a78f">It is a special case of <a _o="182" _o-sc="6,25" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,41" _o-tl="-1" _o-s="6,24" href="move.md" _o-cl="24" id="ddb8b616"><code _o="183" _o-sc="6,26" _o-l="6" _o-e="6,31" _o-tl="-1" _o-s="6,25" _o-cl="25" id="759f9eaa">move</code></a> operation.</p>
<code _o="212" _o-sc="9,0" _o-l="8" _o-e="13,3" _o-tl="129" _o-s="8,0" style="block" _o-cl="0" id="338ea010" lang="kotlin">group { columns }
    .into(groupName) | .into { groupNameExpression }

groupNameExpression = DataColumn.(DataColumn) -> String
</code>

<code _o="374" _o-sc="18,0" _o-l="17" _o-e="21,3" _o-tl="-1" _o-s="17,0" style="block" _o-cl="0" id="df956e48" lang="kotlin">df.group { age and city }.into("info")

df.group { all() }.into { it.type().toString() }.print()
</code>

<p _o="499" _o-sc="25,0" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="6178879c">To ungroup grouped columns use <a _o="530" _o-sc="25,32" LinkStatus="UNKNOWN" _o-l="25" _o-e="25,54" _o-tl="-1" _o-s="25,31" href="ungroup.md" _o-cl="31" id="8d206fca"><code _o="531" _o-sc="25,33" _o-l="25" _o-e="25,41" _o-tl="-1" _o-s="25,32" _o-cl="32" id="c683c36">ungroup</code></a> operation.</p>
</topic>