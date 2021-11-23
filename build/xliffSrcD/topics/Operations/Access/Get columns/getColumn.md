<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="getColumn" title="getColumn" _md-based="true"> 
<p _o="95" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="a557345c">Return column by column name or <a _o="127" _o-sc="4,33" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,69" _o-tl="-1" _o-s="4,32" href="ColumnSelectors.md" _o-cl="32" id="c734c69a">column selector</a> as <a _o="168" _o-sc="4,74" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,102" _o-tl="-1" _o-s="4,73" href="DataColumn.md" _o-cl="73" id="366fb992"><code _o="169" _o-sc="4,75" _o-l="4" _o-e="4,86" _o-tl="-1" _o-s="4,74" _o-cl="74" id="50e2861a">DataColumn</code></a>. Throws exception if requested column doesn't exist.</p>

<tabs id="3e4f746">
<tab id="5779cc33" title="Properties">
<code _o="307" _o-sc="11,0" _o-l="10" _o-e="12,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="43b23d36" lang="kotlin">df.getColumn { age }
</code>
</tab>
<tab _o="343" _o-sc="14,6" _o-l="14" _o-e="16,0" _o-tl="5" _o-s="14,0" _o-cl="0" id="75a6e39a" title="Accessors">
<code _o="375" _o-sc="18,0" _o-l="17" _o-e="21,3" _o-tl="31" _o-s="17,0" style="block" _o-cl="0" id="b82fd2d" lang="kotlin">val age by column&lt;Int>()

df.getColumn { age }
</code>
</tab>
<tab _o="437" _o-sc="23,6" _o-l="23" _o-e="25,0" _o-tl="5" _o-s="23,0" _o-cl="0" id="19d1814e" title="Strings">
<code _o="467" _o-sc="27,0" _o-l="26" _o-e="28,3" _o-tl="-1" _o-s="26,0" style="block" _o-cl="0" id="d7681385" lang="kotlin">df.getColumn("age")
</code>
</tab></tabs>

<chapter _o="529" _o-sc="33,3" _o-l="33" _o-e="33,18" _o-tl="-1" _o-s="33,0" _o-cl="0" id="getcolumnornull" title="getColumnOrNull">
<p _o="549" _o-sc="35,0" _o-l="35" _o-e="36,0" _o-tl="-1" _o-s="35,0" _o-cl="0" id="e4daf692">Return top-level column by column name or <a _o="591" _o-sc="35,43" LinkStatus="UNKNOWN" _o-l="35" _o-e="35,79" _o-tl="-1" _o-s="35,42" href="ColumnSelectors.md" _o-cl="42" id="8ea3a941">column selector</a> as <a _o="632" _o-sc="35,84" LinkStatus="UNKNOWN" _o-l="35" _o-e="35,112" _o-tl="-1" _o-s="35,83" href="DataColumn.md" _o-cl="83" id="989eb5c4"><code _o="633" _o-sc="35,85" _o-l="35" _o-e="35,96" _o-tl="-1" _o-s="35,84" _o-cl="84" id="12b66bcf">DataColumn</code></a> or null if requested column doesn't exist.</p>

<tabs id="cb083059">
<tab id="3650efe3" title="Properties">
<code _o="767" _o-sc="42,0" _o-l="41" _o-e="43,3" _o-tl="-1" _o-s="41,0" style="block" _o-cl="0" id="4e330037" lang="kotlin">df.getColumnOrNull { age }
</code>
</tab>
<tab _o="809" _o-sc="45,6" _o-l="45" _o-e="47,0" _o-tl="5" _o-s="45,0" _o-cl="0" id="b5fdebd3" title="Accessors">
<code _o="841" _o-sc="49,0" _o-l="48" _o-e="52,3" _o-tl="31" _o-s="48,0" style="block" _o-cl="0" id="73151f3a" lang="kotlin">val age by column&lt;Int>()

df.getColumnOrNull(age)
</code>
</tab>
<tab _o="906" _o-sc="54,6" _o-l="54" _o-e="56,0" _o-tl="5" _o-s="54,0" _o-cl="0" id="d0e7b637" title="Strings">
<code _o="936" _o-sc="58,0" _o-l="57" _o-e="59,3" _o-tl="-1" _o-s="57,0" style="block" _o-cl="0" id="bcb72e2c" lang="kotlin">df.getColumnOrNull("age")
</code>
</tab></tabs>

</chapter><chapter _o="1004" _o-sc="64,3" _o-l="64" _o-e="64,17" _o-tl="-1" _o-s="64,0" _o-cl="0" id="getcolumngroup" title="getColumnGroup">
<p _o="1023" _o-sc="66,0" _o-l="66" _o-e="67,0" _o-tl="-1" _o-s="66,0" _o-cl="0" id="bb5776d7">Return top-level column by column name or <a _o="1065" _o-sc="66,43" LinkStatus="UNKNOWN" _o-l="66" _o-e="66,79" _o-tl="-1" _o-s="66,42" href="ColumnSelectors.md" _o-cl="42" id="42aad471">column selector</a> as <a _o="1106" _o-sc="66,84" LinkStatus="UNKNOWN" _o-l="66" _o-e="66,125" _o-tl="-1" _o-s="66,83" href="DataColumn.md#columngroup" _o-cl="83" id="a0357b2c"><code _o="1107" _o-sc="66,85" _o-l="66" _o-e="66,97" _o-tl="-1" _o-s="66,84" _o-cl="84" id="512436">ColumnGroup</code></a>. Throws exception if requested column doesn't exist or is not a <code _o="1213" _o-sc="66,191" _o-l="66" _o-e="66,203" _o-tl="-1" _o-s="66,190" _o-cl="190" id="7144f500">ColumnGroup</code>.</p>

<tabs id="83ff3aed">
<tab id="34360f1" title="Properties">
<code _o="1289" _o-sc="73,0" _o-l="72" _o-e="74,3" _o-tl="-1" _o-s="72,0" style="block" _o-cl="0" id="d4051c53" lang="kotlin">df.getColumnGroup { name }
</code>
</tab>
<tab _o="1331" _o-sc="76,6" _o-l="76" _o-e="78,0" _o-tl="5" _o-s="76,0" _o-cl="0" id="28d6bbe3" title="Accessors">
<code _o="1363" _o-sc="80,0" _o-l="79" _o-e="83,3" _o-tl="-1" _o-s="79,0" style="block" _o-cl="0" id="e8279656" lang="kotlin">val name by columnGroup()

df.getColumnGroup(name)
</code>
</tab>
<tab _o="1429" _o-sc="85,6" _o-l="85" _o-e="87,0" _o-tl="5" _o-s="85,0" _o-cl="0" id="a143d9a7" title="Strings">
<code _o="1459" _o-sc="89,0" _o-l="88" _o-e="90,3" _o-tl="-1" _o-s="88,0" style="block" _o-cl="0" id="b001e695" lang="kotlin">df.getColumnGroup("name")
</code>
</tab></tabs>

</chapter><chapter _o="1527" _o-sc="95,3" _o-l="95" _o-e="95,13" _o-tl="-1" _o-s="95,0" _o-cl="0" id="getcolumns" title="getColumns">
<p _o="1542" _o-sc="97,0" _o-l="97" _o-e="98,0" _o-tl="-1" _o-s="97,0" _o-cl="0" id="6d666c5b">Return list of selected columns.</p>

<tabs id="7c656e50">
<tab id="d161eb57" title="Properties">
<code _o="1632" _o-sc="104,0" _o-l="103" _o-e="105,3" _o-tl="-1" _o-s="103,0" style="block" _o-cl="0" id="70de1004" lang="kotlin">df.getColumns { age and name }
</code>
</tab>
<tab _o="1678" _o-sc="107,6" _o-l="107" _o-e="109,0" _o-tl="5" _o-s="107,0" _o-cl="0" id="bcc1599c" title="Accessors">
<code _o="1710" _o-sc="111,0" _o-l="110" _o-e="115,3" _o-tl="31" _o-s="110,0" style="block" _o-cl="0" id="8b406a01" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()

df.getColumns { age and name }
</code>
</tab>
<tab _o="1808" _o-sc="117,6" _o-l="117" _o-e="119,0" _o-tl="5" _o-s="117,0" _o-cl="0" id="83ac3f25" title="Strings">
<code _o="1838" _o-sc="121,0" _o-l="120" _o-e="122,3" _o-tl="-1" _o-s="120,0" style="block" _o-cl="0" id="cf4613c2" lang="kotlin">df.getColumns("age", "name")
</code>
</tab></tabs>

</chapter></topic>