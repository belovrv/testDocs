<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="move" title="move" _md-based="true"> 
<p _o="90" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="c82c34a2">Moves one or several columns within <code _o="126" _o-sc="4,37" _o-l="4" _o-e="4,47" _o-tl="-1" _o-s="4,36" _o-cl="36" id="d38a1961">DataFrame</code>.</p>
<code _o="140" _o-sc="7,0" _o-l="6" _o-e="11,3" _o-tl="191" _o-s="6,0" style="block" _o-cl="0" id="461928c9" lang="kotlin">move { columns }
    .into { pathSelector } | .under { parentColumn } | .after { column } | .to(position) | .toTop() | .toLeft() | .toRight()

pathSelector: DataFrame.(DataColumn) -> ColumnPath
</code>
<p _o="349" _o-sc="13,0" _o-l="13" _o-e="14,0" _o-tl="-1" _o-s="13,0" _o-cl="0" id="d91a8e30">See <a _o="353" _o-sc="13,5" LinkStatus="UNKNOWN" _o-l="13" _o-e="13,42" _o-tl="-1" _o-s="13,4" href="ColumnSelectors.md" _o-cl="4" id="6fb7bb4e">Column Selectors</a></p>
<p _o="393" _o-sc="15,0" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="e9f7453f">Can be used to change columns hierarchy by providing <code _o="446" _o-sc="15,54" _o-l="15" _o-e="15,65" _o-tl="-1" _o-s="15,53" _o-cl="53" id="1d391156">ColumnPath</code> for every moved column</p>

<code _o="501" _o-sc="20,0" _o-l="19" _o-e="46,3" _o-tl="70" _o-s="19,0" style="block" _o-cl="0" id="fc5dd85c" lang="kotlin">df.move { age }.toLeft()

df.move { weight }.to(1)

// age -> info.age
// weight -> info.weight
df.move { age and weight }.into { pathOf("info", it.name) }
df.move { age and weight }.into { "info"[it.name] }
df.move { age and weight }.under("info")

// name.firstName -> fullName.first
// name.lastName -> fullName.last
df.move { name.firstName and name.lastName }.into { pathOf("fullName", it.name.dropLast(4)) }

// a|b|c -> a.b.c
// a|d|e -> a.d.e
dataFrameOf("a|b|c", "a|d|e")(0, 0)
    .move { all() }.into { it.name.split("|").toPath() }

// name.firstName -> firstName
// name.lastName -> lastName
df.move { name.cols() }.toTop()

// a.b.e -> be
// c.d.e -> de
df.move { dfs { it.name == "e" } }.toTop { it.parent!!.name + it.name }
</code>

<p _o="1269" _o-sc="50,0" _o-l="50" _o-e="51,0" _o-tl="-1" _o-s="50,0" _o-cl="0" id="6047a1d5">Special cases of <code _o="1286" _o-sc="50,18" _o-l="50" _o-e="50,23" _o-tl="-1" _o-s="50,17" _o-cl="17" id="6e2b42fb">move</code>:</p>
<list _o="1294" _o-sc="51,0" _o-l="51" _o-e="54,0" _o-tl="-1" _o-s="51,0" _o-cl="0" id="d8b5e5f8">
<li _o="1294" _o-sc="51,2" _o-l="51" _o-e="52,0" _o-tl="-1" _o-s="51,0" _o-cl="0" id="e5e8eeb2"><a _o="1296" _o-sc="51,3" LinkStatus="UNKNOWN" _o-l="51" _o-e="51,21" _o-tl="-1" _o-s="51,2" href="group.md" _o-cl="2" id="36b116c1"><code _o="1297" _o-sc="51,4" _o-l="51" _o-e="51,10" _o-tl="-1" _o-s="51,3" _o-cl="3" id="dd974944">group</code></a> - groups columns into <a _o="1338" _o-sc="51,45" LinkStatus="UNKNOWN" _o-l="51" _o-e="51,87" _o-tl="-1" _o-s="51,44" href="DataColumn.md#columngroup" _o-cl="44" id="8eaf1098"><code _o="1339" _o-sc="51,46" _o-l="51" _o-e="51,59" _o-tl="-1" _o-s="51,45" _o-cl="45" id="f817a85e">ColumnGroups</code></a></li>
<li _o="1382" _o-sc="52,2" _o-l="52" _o-e="53,0" _o-tl="-1" _o-s="52,0" _o-cl="0" id="eaddd612"><a _o="1384" _o-sc="52,3" LinkStatus="UNKNOWN" _o-l="52" _o-e="52,25" _o-tl="-1" _o-s="52,2" href="ungroup.md" _o-cl="2" id="e91b702a"><code _o="1385" _o-sc="52,4" _o-l="52" _o-e="52,12" _o-tl="-1" _o-s="52,3" _o-cl="3" id="9a1ce053">ungroup</code></a> - ungroups <a _o="1419" _o-sc="52,38" LinkStatus="UNKNOWN" _o-l="52" _o-e="52,80" _o-tl="-1" _o-s="52,37" href="DataColumn.md#columngroup" _o-cl="37" id="2d238cd4"><code _o="1420" _o-sc="52,39" _o-l="52" _o-e="52,52" _o-tl="-1" _o-s="52,38" _o-cl="38" id="a6b5b5c1">ColumnGroups</code></a></li>
<li _o="1463" _o-sc="53,2" _o-l="53" _o-e="54,0" _o-tl="-1" _o-s="53,0" _o-cl="0" id="f39b4c15"><a _o="1465" _o-sc="53,3" LinkStatus="UNKNOWN" _o-l="53" _o-e="53,25" _o-tl="-1" _o-s="53,2" href="flatten.md" _o-cl="2" id="f98b6f50"><code _o="1466" _o-sc="53,4" _o-l="53" _o-e="53,12" _o-tl="-1" _o-s="53,3" _o-cl="3" id="c586dcd6">flatten</code></a> - removes all column groupings</li>
</list>
</topic>