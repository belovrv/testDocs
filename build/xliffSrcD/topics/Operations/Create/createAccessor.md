<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="createAccessor" title="Create ColumnAccessor" _md-based="true"> 
<p _o="106" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="b40978c7"><a _o="106" _o-sc="3,1" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,50" _o-tl="-1" _o-s="3,0" href="DataColumn.md#column-accessors" _o-cl="0" id="39d203d5">Column accessors</a> are created by <a _o="172" _o-sc="3,67" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,140" _o-tl="-1" _o-s="3,66" href="https://kotlinlang.org/docs/delegated-properties.html" _o-cl="66" id="d5370fa1">property delegate</a> <code _o="247" _o-sc="3,142" _o-l="3" _o-e="3,149" _o-tl="-1" _o-s="3,141" _o-cl="141" id="2c59365e">column</code>. Column <a _o="264" _o-sc="3,159" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,192" _o-tl="-1" _o-s="3,158" href="DataColumn.md#properties" _o-cl="158" id="962e6479"><code _o="265" _o-sc="3,160" _o-l="3" _o-e="3,165" _o-tl="-1" _o-s="3,159" _o-cl="159" id="e1a2541c">type</code></a> should be passed as type argument, column <a _o="341" _o-sc="3,236" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,269" _o-tl="-1" _o-s="3,235" href="DataColumn.md#properties" _o-cl="235" id="1afcfd40"><code _o="342" _o-sc="3,237" _o-l="3" _o-e="3,242" _o-tl="-1" _o-s="3,236" _o-cl="236" id="dd9415d3">name</code></a> will be taken from the variable name.</p>

<code _o="449" _o-sc="8,0" _o-l="7" _o-e="9,3" _o-tl="35" _o-s="7,0" style="block" _o-cl="0" id="d8065d40" lang="kotlin">val name by column&lt;String>()
</code>

<p _o="506" _o-sc="13,0" _o-l="13" _o-e="14,0" _o-tl="-1" _o-s="13,0" _o-cl="0" id="53b46a74">To assign column name explicitly, pass it as an argument.</p>

<code _o="606" _o-sc="18,0" _o-l="17" _o-e="19,3" _o-tl="39" _o-s="17,0" style="block" _o-cl="0" id="b517d9b0" lang="kotlin">val accessor by column&lt;String>("complex column name")
</code>

<p _o="688" _o-sc="23,0" _o-l="23" _o-e="24,0" _o-tl="-1" _o-s="23,0" _o-cl="0" id="ea61cf3c">You can also create column accessors for <a _o="729" _o-sc="23,42" LinkStatus="UNKNOWN" _o-l="23" _o-e="23,82" _o-tl="-1" _o-s="23,41" href="DataColumn.md#columngroup" _o-cl="41" id="d44e1f41">ColumnGroups</a> and <a _o="775" _o-sc="23,88" LinkStatus="UNKNOWN" _o-l="23" _o-e="23,128" _o-tl="-1" _o-s="23,87" href="DataColumn.md#framecolumn" _o-cl="87" id="1d04db5b">FrameColumns</a></p>

<code _o="864" _o-sc="28,0" _o-l="27" _o-e="30,3" _o-tl="-1" _o-s="27,0" style="block" _o-cl="0" id="5ee9da72" lang="kotlin">val columns by columnGroup()
val frames by frameColumn()
</code>

<chapter _o="949" _o-sc="34,4" _o-l="34" _o-e="34,25" _o-tl="-1" _o-s="34,0" _o-cl="0" id="deep-column-accessors" title="Deep column accessors">
<p _o="976" _o-sc="36,0" _o-l="36" _o-e="37,0" _o-tl="-1" _o-s="36,0" _o-cl="0" id="87686bb3">Deep column accessor references nested columns inside <a _o="1030" _o-sc="36,55" LinkStatus="UNKNOWN" _o-l="36" _o-e="36,95" _o-tl="-1" _o-s="36,54" href="DataColumn.md#columngroup" _o-cl="54" id="73beceb4">ColumnGroups</a>.</p>

<code _o="1112" _o-sc="41,0" _o-l="40" _o-e="43,3" _o-tl="71" _o-s="40,0" style="block" _o-cl="0" id="4625bda6" lang="kotlin">val name by columnGroup()
val firstName by name.column&lt;String>()
</code>

</chapter><chapter _o="1205" _o-sc="47,4" _o-l="47" _o-e="47,29" _o-tl="-1" _o-s="47,0" _o-cl="0" id="computed-column-accessors" title="Computed column accessors">
<p _o="1236" _o-sc="49,0" _o-l="49" _o-e="50,0" _o-tl="-1" _o-s="49,0" _o-cl="0" id="a22d2027">Computed column accessor evaluates custom expression on every data access.</p>

<tabs id="68b4c6d0">
<tab id="11bee113" title="Properties">
<code _o="1380" _o-sc="56,0" _o-l="55" _o-e="59,3" _o-tl="-1" _o-s="55,0" style="block" _o-cl="0" id="786e43b8" lang="kotlin">val fullName by df.column { name.firstName + " " + name.lastName }

df[fullName]
</code>
</tab>
<tab _o="1476" _o-sc="61,6" _o-l="61" _o-e="63,0" _o-tl="5" _o-s="61,0" _o-cl="0" id="5adf59" title="Accessors">
<code _o="1508" _o-sc="65,0" _o-l="64" _o-e="72,3" _o-tl="71" _o-s="64,0" style="block" _o-cl="0" id="e67ce6fa" lang="kotlin">val name by columnGroup()
val firstName by name.column&lt;String>()
val lastName by name.column&lt;String>()

val fullName by column { firstName() + " " + lastName() }

df[fullName]
</code>
</tab>
<tab _o="1699" _o-sc="74,6" _o-l="74" _o-e="76,0" _o-tl="5" _o-s="74,0" _o-cl="0" id="b132b981" title="Strings">
<code _o="1729" _o-sc="78,0" _o-l="77" _o-e="81,3" _o-tl="61" _o-s="77,0" style="block" _o-cl="0" id="48f9d4ca" lang="kotlin">val fullName by column { "name"["firstName"]&lt;String>() + " " + "name"["lastName"]&lt;String>() }

df[fullName]
</code>
</tab></tabs>

<p _o="1879" _o-sc="86,0" _o-l="86" _o-e="87,0" _o-tl="-1" _o-s="86,0" _o-cl="0" id="863bc411">When expression depends only on one column, use <code _o="1927" _o-sc="86,49" _o-l="86" _o-e="86,53" _o-tl="-1" _o-s="86,48" _o-cl="48" id="5a02d8">map</code>:</p>

<code _o="1966" _o-sc="91,0" _o-l="90" _o-e="95,3" _o-tl="31" _o-s="90,0" style="block" _o-cl="0" id="433652b0" lang="kotlin">val age by column&lt;Int>()
val year by age.map { 2021 - it }

df.filter { year > 2000 }
</code>

</chapter></topic>