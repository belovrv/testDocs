<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="split" title="split" _md-based="true"> 
<p _o="91" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="a038d705">Splits every value in the given columns into several values. Splitted values can be spread horizontally or vertically or remain inside the original column as <code _o="249" _o-sc="4,159" _o-l="4" _o-e="4,164" _o-tl="-1" _o-s="4,158" _o-cl="158" id="9a224c65">List</code></p>
<p _o="257" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="581d83b5">The following types of columns can be splitted by default:</p>
<list _o="316" _o-sc="7,0" _o-l="7" _o-e="10,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="61e38aef">
<li _o="316" _o-sc="7,2" _o-l="7" _o-e="8,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="65b0e43d"><code _o="318" _o-sc="7,3" _o-l="7" _o-e="7,10" _o-tl="-1" _o-s="7,2" _o-cl="2" id="4ef0ff78">String</code>: split by <code _o="337" _o-sc="7,22" _o-l="7" _o-e="7,24" _o-tl="-1" _o-s="7,21" _o-cl="21" id="ac04e014">,</code> and trim</li>
<li _o="350" _o-sc="8,2" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="a4ccf90e"><code _o="352" _o-sc="8,3" _o-l="8" _o-e="8,8" _o-tl="-1" _o-s="8,2" _o-cl="2" id="af08d5d">List</code>: split into elements</li>
<li _o="380" _o-sc="9,2" _o-l="9" _o-e="10,0" _o-tl="-1" _o-s="9,0" _o-cl="0" id="488d0508"><code _o="382" _o-sc="9,3" _o-l="9" _o-e="9,13" _o-tl="-1" _o-s="9,2" _o-cl="2" id="e4f96c98">DataFrame</code>: split into rows</li>
</list>
<code _o="412" _o-sc="12,0" _o-l="11" _o-e="19,3" _o-tl="357" _o-s="11,0" style="block" _o-cl="0" id="d0c1ae88" lang="kotlin">df.split { columns }
    [.by(delimeters) | .by { splitter } | .match(regex)] // how to split cell value
    [.default(value)] // how to fill nulls
    .into(columnNames) [ { columnNamesGenerator } ] | .inward(columnNames) [ { columnNamesGenerator } | .inplace() | .intoRows() | .intoColumns() ] // where to store results

splitter = DataRow.(T) -> Iterable&lt;Any>
columnNamesGenerator = DataColumn.(columnIndex: Int) -> String
</code>
<p _o="853" _o-sc="21,0" _o-l="21" _o-e="22,0" _o-tl="-1" _o-s="21,0" _o-cl="0" id="9e4046f8">Storage options:</p>
<list _o="870" _o-sc="22,0" _o-l="22" _o-e="27,0" _o-tl="-1" _o-s="22,0" _o-cl="0" id="4ad8e901">
<li _o="870" _o-sc="22,2" _o-l="22" _o-e="23,0" _o-tl="-1" _o-s="22,0" _o-cl="0" id="84bb4fbf"><code _o="872" _o-sc="22,3" _o-l="22" _o-e="22,26" _o-tl="-1" _o-s="22,2" _o-cl="2" id="7bd61cd6">into(col1, col2, ... )</code> - store splitted values in new top-level columns</li>
<li _o="946" _o-sc="23,2" _o-l="23" _o-e="24,0" _o-tl="-1" _o-s="23,0" _o-cl="0" id="1688961c"><code _o="948" _o-sc="23,3" _o-l="23" _o-e="23,27" _o-tl="-1" _o-s="23,2" _o-cl="2" id="b06e0305">inward(col1, col2, ...)</code> - store splitted values in new columns nested inside original column</li>
<li _o="1043" _o-sc="24,2" _o-l="24" _o-e="25,0" _o-tl="-1" _o-s="24,0" _o-cl="0" id="10b838e1"><code _o="1045" _o-sc="24,3" _o-l="24" _o-e="24,11" _o-tl="-1" _o-s="24,2" _o-cl="2" id="d699b28c">inplace</code> - store splitted values in original column as <code _o="1101" _o-sc="24,59" _o-l="24" _o-e="24,64" _o-tl="-1" _o-s="24,58" _o-cl="58" id="c16098c6">List</code></li>
<li _o="1108" _o-sc="25,2" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="3fe01d6f"><code _o="1110" _o-sc="25,3" _o-l="25" _o-e="25,12" _o-tl="-1" _o-s="25,2" _o-cl="2" id="65764a8d">intoRows</code> - spread splitted values vertically into new rows</li>
<li _o="1171" _o-sc="26,2" _o-l="26" _o-e="27,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="380ca25a"><code _o="1173" _o-sc="26,3" _o-l="26" _o-e="26,15" _o-tl="-1" _o-s="26,2" _o-cl="2" id="cdd91d4b">intoColumns</code> - split <code _o="1195" _o-sc="26,25" _o-l="26" _o-e="26,37" _o-tl="-1" _o-s="26,24" _o-cl="24" id="37c3393c">FrameColumn</code> into <code _o="1214" _o-sc="26,44" _o-l="26" _o-e="26,56" _o-tl="-1" _o-s="26,43" _o-cl="43" id="3cb66a63">ColumnGroup</code> storing in every cell a <code _o="1252" _o-sc="26,82" _o-l="26" _o-e="26,87" _o-tl="-1" _o-s="26,81" _o-cl="81" id="93e0d359">List</code> of original values per every column</li>
</list>
<p _o="1296" _o-sc="28,0" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="ed0eff30"><code _o="1296" _o-sc="28,1" _o-l="28" _o-e="28,22" _o-tl="-1" _o-s="28,0" _o-cl="0" id="3da80618">columnNamesGenerator</code> is used to generate names for additional columns when the list of explicitly specified <code _o="1406" _o-sc="28,111" _o-l="28" _o-e="28,123" _o-tl="-1" _o-s="28,110" _o-cl="110" id="b7ff9206">columnNames</code> was not long enough. <code _o="1441" _o-sc="28,146" _o-l="28" _o-e="28,158" _o-tl="-1" _o-s="28,145" _o-cl="145" id="6956389a">columnIndex</code> starts with <code _o="1467" _o-sc="28,172" _o-l="28" _o-e="28,174" _o-tl="-1" _o-s="28,171" _o-cl="171" id="89704f62">1</code> for the first additional column name.</p>
<p _o="1512" _o-sc="30,0" _o-l="30" _o-e="31,0" _o-tl="-1" _o-s="30,0" _o-cl="0" id="ca733d64">Default <code _o="1520" _o-sc="30,9" _o-l="30" _o-e="30,30" _o-tl="-1" _o-s="30,8" _o-cl="8" id="390dbaf6">columnNamesGenerator</code> generates column names <code _o="1566" _o-sc="30,55" _o-l="30" _o-e="30,65" _o-tl="-1" _o-s="30,54" _o-cl="54" id="ee726c6">splitted1</code>, <code _o="1579" _o-sc="30,68" _o-l="30" _o-e="30,78" _o-tl="-1" _o-s="30,67" _o-cl="67" id="21719858">splitted2</code>...</p>
<chapter _o="1595" _o-sc="32,3" _o-l="32" _o-e="32,21" _o-tl="-1" _o-s="32,0" _o-cl="0" id="split-horizontally" title="Split horizontally">
<p _o="1617" _o-sc="33,0" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="99efc6d0">Reverse operation to <a _o="1638" _o-sc="33,22" LinkStatus="UNKNOWN" _o-l="33" _o-e="33,40" _o-tl="-1" _o-s="33,21" href="merge.md" _o-cl="21" id="f5695b7c"><code _o="1639" _o-sc="33,23" _o-l="33" _o-e="33,29" _o-tl="-1" _o-s="33,22" _o-cl="22" id="26936d2e">merge</code></a></p>

<tabs id="d6a3e944">
<tab id="425f0c8a" title="Properties">
<code _o="1710" _o-sc="40,0" _o-l="39" _o-e="45,3" _o-tl="-1" _o-s="39,0" style="block" _o-cl="0" id="9bb924c5" lang="kotlin">df.split { name.firstName }.by { it.chars().toList() }.inplace()

df.split { name }.by { it.values() }.into("nameParts")

df.split { name.lastName }.by(" ").default("").inward { "word$it" }
</code>
</tab>
<tab _o="1915" _o-sc="47,6" _o-l="47" _o-e="49,0" _o-tl="5" _o-s="47,0" _o-cl="0" id="dee05755" title="Accessors">
<code _o="1947" _o-sc="51,0" _o-l="50" _o-e="60,3" _o-tl="71" _o-s="50,0" style="block" _o-cl="0" id="782ac658" lang="kotlin">val name by columnGroup()
val firstName by name.column&lt;String>()
val lastName by name.column&lt;String>()

df.split { firstName }.by { it.chars().toList() }.inplace()

df.split { name }.by { it.values() }.into("nameParts")

df.split { lastName }.by(" ").default("").inward { "word$it" }
</code>
</tab>
<tab _o="2246" _o-sc="62,6" _o-l="62" _o-e="64,0" _o-tl="5" _o-s="62,0" _o-cl="0" id="1f36ce40" title="Strings">
<code _o="2276" _o-sc="66,0" _o-l="65" _o-e="71,3" _o-tl="47" _o-s="65,0" style="block" _o-cl="0" id="63cefe63" lang="kotlin">df.split { "name"["firstName"]&lt;String>() }.by { it.chars().toList() }.inplace()

df.split { name }.by { it.values() }.into("nameParts")

df.split { "name"["lastName"] }.by(" ").default("").inward { "word$it" }
</code>
</tab></tabs>

<p _o="2528" _o-sc="76,0" _o-l="76" _o-e="77,0" _o-tl="-1" _o-s="76,0" _o-cl="0" id="625f8f99"><code _o="2528" _o-sc="76,1" _o-l="76" _o-e="76,8" _o-tl="-1" _o-s="76,0" _o-cl="0" id="14755dfb">String</code> columns can also be splitted into group matches of <a _o="2588" _o-sc="76,61" LinkStatus="UNKNOWN" _o-l="76" _o-e="76,135" _o-tl="-1" _o-s="76,60" href="https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/" _o-cl="60" id="a030cf3"><code _o="2589" _o-sc="76,62" _o-l="76" _o-e="76,68" _o-tl="-1" _o-s="76,61" _o-cl="61" id="890c6293">Regex</code></a> pattern:</p>

<code _o="2698" _o-sc="81,0" _o-l="80" _o-e="84,3" _o-tl="-1" _o-s="80,0" style="block" _o-cl="0" id="54e90ec0" lang="kotlin">merged.split { name }
    .match("""(.*) \((.*)\)""")
    .inward("firstName", "lastName")
</code>

<p _o="2817" _o-sc="88,0" _o-l="88" _o-e="89,0" _o-tl="-1" _o-s="88,0" _o-cl="0" id="34c8b74e"><code _o="2817" _o-sc="88,1" _o-l="88" _o-e="88,13" _o-tl="-1" _o-s="88,0" _o-cl="0" id="760e19bb">FrameColumn</code> can be splitted into columns:</p>

<code _o="2892" _o-sc="93,0" _o-l="92" _o-e="107,3" _o-tl="-1" _o-s="92,0" style="block" _o-cl="0" id="5af815b1" lang="kotlin">val df1 = dataFrameOf("a", "b", "c")(
    1, 2, 3,
    4, 5, 6
)
val df2 = dataFrameOf("a", "b")(
    5, 6,
    7, 8,
    9, 10
)
val group by columnOf(df1, df2)
val id by columnOf("x", "y")
val df = dataFrameOf(id, group)

df.split { group }.intoColumns()
</code>

</chapter><chapter _o="3177" _o-sc="111,3" _o-l="111" _o-e="111,19" _o-tl="-1" _o-s="111,0" _o-cl="0" id="split-vertically" title="Split vertically">
<p _o="3197" _o-sc="112,0" _o-l="112" _o-e="113,0" _o-tl="-1" _o-s="112,0" _o-cl="0" id="1d1c7060">Returns <code _o="3205" _o-sc="112,9" _o-l="112" _o-e="112,19" _o-tl="-1" _o-s="112,8" _o-cl="8" id="df5278c6">DataFrame</code> with duplicated rows for every splitted value.</p>
<p _o="3266" _o-sc="114,0" _o-l="114" _o-e="115,0" _o-tl="-1" _o-s="114,0" _o-cl="0" id="99381ac4">Reverse operation to <a _o="3287" _o-sc="114,22" LinkStatus="UNKNOWN" _o-l="114" _o-e="114,44" _o-tl="-1" _o-s="114,21" href="implode.md" _o-cl="21" id="5a3360ee"><code _o="3288" _o-sc="114,23" _o-l="114" _o-e="114,31" _o-tl="-1" _o-s="114,22" _o-cl="22" id="c178a981">implode</code></a>.</p>
<p _o="3313" _o-sc="116,0" _o-l="116" _o-e="117,0" _o-tl="-1" _o-s="116,0" _o-cl="0" id="9f8903fa">Use <code _o="3317" _o-sc="116,5" _o-l="116" _o-e="116,17" _o-tl="-1" _o-s="116,4" _o-cl="4" id="d5535c99">.intoRows()</code> terminal operation in <code _o="3353" _o-sc="116,41" _o-l="116" _o-e="116,47" _o-tl="-1" _o-s="116,40" _o-cl="40" id="e87bc43f">split</code> configuration to spread splitted values vertically:</p>

<tabs id="3e60580">
<tab id="1350fabd" title="Properties">
<code _o="3473" _o-sc="123,0" _o-l="122" _o-e="126,3" _o-tl="-1" _o-s="122,0" style="block" _o-cl="0" id="8d1df3a4" lang="kotlin">df.split { name.firstName }.by { it.chars().toList() }.intoRows()

df.split { name }.by { it.values() }.intoRows()
</code>
</tab>
<tab _o="3603" _o-sc="128,6" _o-l="128" _o-e="130,0" _o-tl="5" _o-s="128,0" _o-cl="0" id="9bc15398" title="Accessors">
<code _o="3635" _o-sc="132,0" _o-l="131" _o-e="138,3" _o-tl="71" _o-s="131,0" style="block" _o-cl="0" id="dde88d35" lang="kotlin">val name by columnGroup()
val firstName by name.column&lt;String>()

df.split { firstName }.by { it.chars().toList() }.intoRows()

df.split { name }.by { it.values() }.intoRows()
</code>
</tab>
<tab _o="3826" _o-sc="140,6" _o-l="140" _o-e="142,0" _o-tl="5" _o-s="140,0" _o-cl="0" id="624d816f" title="Strings">
<code _o="3856" _o-sc="144,0" _o-l="143" _o-e="147,3" _o-tl="47" _o-s="143,0" style="block" _o-cl="0" id="a7571f5" lang="kotlin">df.split { "name"["firstName"]&lt;String>() }.by { it.chars().toList() }.intoRows()

df.split { group("name") }.by { it.values() }.intoRows()
</code>
</tab></tabs>

<p _o="4037" _o-sc="152,0" _o-l="152" _o-e="153,0" _o-tl="-1" _o-s="152,0" _o-cl="0" id="4029335a">Equals to <code _o="4047" _o-sc="152,11" _o-l="152" _o-e="152,59" _o-tl="-1" _o-s="152,10" _o-cl="10" id="ea6f3c58">split { column }...inplace().explode { column }</code>. See <a _o="4102" _o-sc="152,66" LinkStatus="UNKNOWN" _o-l="152" _o-e="152,88" _o-tl="-1" _o-s="152,65" href="explode.md" _o-cl="65" id="6541d290"><code _o="4103" _o-sc="152,67" _o-l="152" _o-e="152,75" _o-tl="-1" _o-s="152,66" _o-cl="66" id="51e9b542">explode</code></a> for details.</p>
</chapter></topic>