<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="join" title="join" _md-based="true"> 
<p _o="88" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="bb606bd7">Joins two DataFrames by join columns.</p>
<code _o="127" _o-sc="7,0" _o-l="6" _o-e="17,3" _o-tl="106" _o-s="6,0" style="block" _o-cl="0" id="a2a367ec" lang="kotlin">join(otherDf, type = JoinType.Inner) [ { joinColumns } ]

joinColumns: JoinDsl.(LeftDataFrame) -> Columns

interface JoinDsl: LeftDataFrame {
    
    val right: RightDataFrame
    
    fun DataColumn.match(rightColumn: DataColumn)
}
</code>
<p _o="376" _o-sc="19,0" _o-l="19" _o-e="20,0" _o-tl="-1" _o-s="19,0" _o-cl="0" id="8fe1327a"><code _o="376" _o-sc="19,1" _o-l="19" _o-e="19,13" _o-tl="-1" _o-s="19,0" _o-cl="0" id="42ae9711">joinColumns</code> is a <a _o="395" _o-sc="19,20" LinkStatus="UNKNOWN" _o-l="19" _o-e="19,56" _o-tl="-1" _o-s="19,19" href="ColumnSelectors.md" _o-cl="19" id="4d847c4f">column selector</a> that defines column mapping for join:</p>

<tabs id="8f32e60e">
<tab id="df1964ad" title="Properties">
<code _o="531" _o-sc="26,0" _o-l="25" _o-e="27,3" _o-tl="-1" _o-s="25,0" style="block" _o-cl="0" id="4ac984a0" lang="kotlin">df.join(other) { name match right.fullName }
</code>
</tab>
<tab _o="591" _o-sc="29,6" _o-l="29" _o-e="31,0" _o-tl="5" _o-s="29,0" _o-cl="0" id="a451e57c" title="Accessors">
<code _o="623" _o-sc="33,0" _o-l="32" _o-e="37,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="b079ab2" lang="kotlin">val name by columnGroup()
val fullName by columnGroup()

df.join(other) { name match fullName }
</code>
</tab>
<tab _o="734" _o-sc="39,6" _o-l="39" _o-e="41,0" _o-tl="5" _o-s="39,0" _o-cl="0" id="1b7c0442" title="Strings">
<code _o="764" _o-sc="43,0" _o-l="42" _o-e="44,3" _o-tl="-1" _o-s="42,0" style="block" _o-cl="0" id="d8d9d9c" lang="kotlin">df.join(other) { "name" match "fullName" }
</code>
</tab></tabs>

<p _o="849" _o-sc="49,0" _o-l="49" _o-e="50,0" _o-tl="-1" _o-s="49,0" _o-cl="0" id="56e7c307">If mapped columns have the same name, just select join columns from the left <code _o="926" _o-sc="49,78" _o-l="49" _o-e="49,88" _o-tl="-1" _o-s="49,77" _o-cl="77" id="66ededb">DataFrame</code>:</p>

<tabs id="d669d468">
<tab id="21d06945" title="Properties">
<code _o="991" _o-sc="56,0" _o-l="55" _o-e="57,3" _o-tl="-1" _o-s="55,0" style="block" _o-cl="0" id="bbf3f4e1" lang="kotlin">df.join(other) { name and city }
</code>
</tab>
<tab _o="1039" _o-sc="59,6" _o-l="59" _o-e="61,0" _o-tl="5" _o-s="59,0" _o-cl="0" id="bfe72726" title="Accessors">
<code _o="1071" _o-sc="63,0" _o-l="62" _o-e="67,3" _o-tl="61" _o-s="62,0" style="block" _o-cl="0" id="df6fe650" lang="kotlin">val name by columnGroup()
val city by column&lt;String>()

df.join(other) { name and city }
</code>
</tab>
<tab _o="1175" _o-sc="69,6" _o-l="69" _o-e="71,0" _o-tl="5" _o-s="69,0" _o-cl="0" id="502c085f" title="Strings">
<code _o="1205" _o-sc="73,0" _o-l="72" _o-e="74,3" _o-tl="-1" _o-s="72,0" style="block" _o-cl="0" id="f656cf9e" lang="kotlin">df.join(other, "name", "city")
</code>
</tab></tabs>

<p _o="1278" _o-sc="79,0" _o-l="79" _o-e="80,0" _o-tl="-1" _o-s="79,0" _o-cl="0" id="32ad79cd">If <code _o="1281" _o-sc="79,4" _o-l="79" _o-e="79,16" _o-tl="-1" _o-s="79,3" _o-cl="3" id="67495c02">joinColumns</code> is not specified, columns with the same name from both DataFrames will be used as join columns:</p>

<code _o="1417" _o-sc="84,0" _o-l="83" _o-e="85,3" _o-tl="-1" _o-s="83,0" style="block" _o-cl="0" id="886398a9" lang="kotlin">df.join(other)
</code>

<chapter _o="1460" _o-sc="89,4" _o-l="89" _o-e="89,14" _o-tl="-1" _o-s="89,0" _o-cl="0" id="join-types" title="Join types">
<p _o="1476" _o-sc="91,0" _o-l="91" _o-e="92,0" _o-tl="-1" _o-s="91,0" _o-cl="0" id="dd2b2019">Supported join types:</p>
<list _o="1498" _o-sc="92,0" _o-l="92" _o-e="97,0" _o-tl="-1" _o-s="92,0" _o-cl="0" id="27b2b2c0">
<li _o="1498" _o-sc="92,2" _o-l="92" _o-e="93,0" _o-tl="-1" _o-s="92,0" _o-cl="0" id="b2ef4899"><code _o="1500" _o-sc="92,3" _o-l="92" _o-e="92,9" _o-tl="-1" _o-s="92,2" _o-cl="2" id="6d554962">Inner</code> (default) - only matched rows from left and right dataframes</li>
<li _o="1569" _o-sc="93,2" _o-l="93" _o-e="94,0" _o-tl="-1" _o-s="93,0" _o-cl="0" id="170523bd"><code _o="1571" _o-sc="93,3" _o-l="93" _o-e="93,8" _o-tl="-1" _o-s="93,2" _o-cl="2" id="f21855b0">Left</code> - all rows from left dataframe, mismatches from right dataframe filled with <code _o="1654" _o-sc="93,86" _o-l="93" _o-e="93,91" _o-tl="-1" _o-s="93,85" _o-cl="85" id="db2e4e4e">null</code></li>
<li _o="1661" _o-sc="94,2" _o-l="94" _o-e="95,0" _o-tl="-1" _o-s="94,0" _o-cl="0" id="fcd99daf"><code _o="1663" _o-sc="94,3" _o-l="94" _o-e="94,9" _o-tl="-1" _o-s="94,2" _o-cl="2" id="f501d81">Right</code> - all rows from right dataframe, mismatches from left dataframe filled with <code _o="1747" _o-sc="94,87" _o-l="94" _o-e="94,92" _o-tl="-1" _o-s="94,86" _o-cl="86" id="2dac0767">null</code></li>
<li _o="1754" _o-sc="95,2" _o-l="95" _o-e="96,0" _o-tl="-1" _o-s="95,0" _o-cl="0" id="bc7e4a2b"><code _o="1756" _o-sc="95,3" _o-l="95" _o-e="95,8" _o-tl="-1" _o-s="95,2" _o-cl="2" id="c23a1f89">Full</code> - all rows from left and right dataframes, any mismatches filled with <code _o="1833" _o-sc="95,80" _o-l="95" _o-e="95,85" _o-tl="-1" _o-s="95,79" _o-cl="79" id="c3f71321">null</code></li>
<li _o="1840" _o-sc="96,2" _o-l="96" _o-e="97,0" _o-tl="-1" _o-s="96,0" _o-cl="0" id="f3edffaf"><code _o="1842" _o-sc="96,3" _o-l="96" _o-e="96,11" _o-tl="-1" _o-s="96,2" _o-cl="2" id="e2b15662">Exclude</code> - only mismatched rows from left</li>
</list>
<p _o="1886" _o-sc="98,0" _o-l="98" _o-e="99,0" _o-tl="-1" _o-s="98,0" _o-cl="0" id="6829110c">For every join type there is a shortcut operation:</p>

<tabs id="d34c3fbc">
<tab id="68f9f6c7" title="Properties">
<code _o="1995" _o-sc="105,0" _o-l="104" _o-e="110,3" _o-tl="-1" _o-s="104,0" style="block" _o-cl="0" id="4bbc7d00" lang="kotlin">df.innerJoin(other) { name and city }
df.leftJoin(other) { name and city }
df.rightJoin(other) { name and city }
df.fullJoin(other) { name and city }
df.excludeJoin(other) { name and city }
</code>
</tab>
<tab _o="2200" _o-sc="112,6" _o-l="112" _o-e="114,0" _o-tl="5" _o-s="112,0" _o-cl="0" id="577d0355" title="Accessors">
<code _o="2232" _o-sc="116,0" _o-l="115" _o-e="124,3" _o-tl="61" _o-s="115,0" style="block" _o-cl="0" id="bbccbb0f" lang="kotlin">val name by columnGroup()
val city by column&lt;String>()

df.innerJoin(other) { name and city }
df.leftJoin(other) { name and city }
df.rightJoin(other) { name and city }
df.fullJoin(other) { name and city }
df.excludeJoin(other) { name and city }
</code>
</tab>
<tab _o="2493" _o-sc="126,6" _o-l="126" _o-e="128,0" _o-tl="5" _o-s="126,0" _o-cl="0" id="e5fe0e8a" title="Strings">
<code _o="2523" _o-sc="130,0" _o-l="129" _o-e="135,3" _o-tl="-1" _o-s="129,0" style="block" _o-cl="0" id="76ff543e" lang="kotlin">df.innerJoin(other, "name", "city")
df.leftJoin(other, "name", "city")
df.rightJoin(other, "name", "city")
df.fullJoin(other, "name", "city")
df.excludeJoin(other, "name", "city")
</code>
</tab></tabs>

</chapter></topic>