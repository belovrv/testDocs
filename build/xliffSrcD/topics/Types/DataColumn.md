<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="DataColumn" title="DataColumn" _md-based="true"> 
<p _o="95" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="9957305f"><code _o="95" _o-sc="3,1" _o-l="3" _o-e="3,12" _o-tl="-1" _o-s="3,0" _o-cl="0" id="c4c0f18">DataColumn</code> represents a column of values. It can store objects of primitive or reference types, or other <a _o="202" _o-sc="3,108" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,135" _o-tl="-1" _o-s="3,107" href="DataFrame.md" _o-cl="107" id="2acac0e5"><code _o="203" _o-sc="3,109" _o-l="3" _o-e="3,120" _o-tl="-1" _o-s="3,108" _o-cl="108" id="4bf7605c">DataFrames</code></a>.</p>
<p _o="233" _o-sc="5,0" _o-l="5" _o-e="6,0" _o-tl="-1" _o-s="5,0" _o-cl="0" id="3680858e">See <a _o="237" _o-sc="5,5" LinkStatus="UNKNOWN" _o-l="5" _o-e="5,44" _o-tl="-1" _o-s="5,4" href="createColumn.md" _o-cl="4" id="69e7b1eb">how to create columns</a></p>
<chapter _o="279" _o-sc="7,4" _o-l="7" _o-e="7,14" _o-tl="-1" _o-s="7,0" _o-cl="0" id="properties" title="Properties">
<list _o="294" _o-sc="8,0" _o-l="8" _o-e="13,0" _o-tl="203" _o-s="8,0" _o-cl="0" id="8023b75e">
<li _o="294" _o-sc="8,2" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="74cbab55"><code _o="296" _o-sc="8,3" _o-l="8" _o-e="8,16" _o-tl="-1" _o-s="8,2" _o-cl="2" id="94fdf3b3">name: String</code> - name of the column, should be unique within containing dataframe</li>
<li _o="378" _o-sc="9,2" _o-l="9" _o-e="10,0" _o-tl="-1" _o-s="9,0" _o-cl="0" id="5e2f1f10"><code _o="380" _o-sc="9,3" _o-l="9" _o-e="9,15" _o-tl="-1" _o-s="9,2" _o-cl="2" id="44dd1cfb">type: KType</code> - type of elements in the column</li>
<li _o="427" _o-sc="10,2" _o-l="10" _o-e="11,0" _o-tl="-1" _o-s="10,0" _o-cl="0" id="13b2d141"><code _o="429" _o-sc="10,3" _o-l="10" _o-e="10,13" _o-tl="-1" _o-s="10,2" _o-cl="2" id="8e3874f9">size: Int</code> - number of elements in the column</li>
<li _o="476" _o-sc="11,2" _o-l="11" _o-e="12,0" _o-tl="21" _o-s="11,0" _o-cl="0" id="510ec62f"><code _o="478" _o-sc="11,3" _o-l="11" _o-e="11,23" _o-tl="19" _o-s="11,2" _o-cl="2" id="9d860391">values: Iterable&lt;T></code> - column data</li>
<li _o="514" _o-sc="12,2" _o-l="12" _o-e="13,0" _o-tl="-1" _o-s="12,0" _o-cl="0" id="44293b03"><code _o="516" _o-sc="12,3" _o-l="12" _o-e="12,21" _o-tl="-1" _o-s="12,2" _o-cl="2" id="3e95ea12">hasNulls: Boolean</code> - flag indicating whether column contains <code _o="578" _o-sc="12,65" _o-l="12" _o-e="12,70" _o-tl="-1" _o-s="12,64" _o-cl="64" id="1a60e99">null</code> values</li>
</list>
</chapter><chapter _o="593" _o-sc="14,4" _o-l="14" _o-e="14,16" _o-tl="-1" _o-s="14,0" _o-cl="0" id="column-kinds" title="Column kinds">
<p _o="610" _o-sc="15,0" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="cf444d6b"><code _o="610" _o-sc="15,1" _o-l="15" _o-e="15,12" _o-tl="-1" _o-s="15,0" _o-cl="0" id="fb1cf4f0">DataColumn</code> instances can be one of three subtypes: <code _o="663" _o-sc="15,54" _o-l="15" _o-e="15,66" _o-tl="-1" _o-s="15,53" _o-cl="53" id="aef4933a">ValueColumn</code>, <code _o="678" _o-sc="15,69" _o-l="15" _o-e="15,81" _o-tl="-1" _o-s="15,68" _o-cl="68" id="582e6fe">ColumnGroup</code> or <code _o="695" _o-sc="15,86" _o-l="15" _o-e="15,98" _o-tl="-1" _o-s="15,85" _o-cl="85" id="5f3c13e2">FrameColumn</code></p>
<chapter _o="710" _o-sc="17,5" _o-l="17" _o-e="17,16" _o-tl="-1" _o-s="17,0" _o-cl="0" id="valuecolumn" title="ValueColumn">
<p _o="728" _o-sc="19,0" _o-l="19" _o-e="20,0" _o-tl="-1" _o-s="19,0" _o-cl="0" id="2ed349f1">Represents a sequence of values.</p>
<p _o="763" _o-sc="21,0" _o-l="21" _o-e="22,0" _o-tl="-1" _o-s="21,0" _o-cl="0" id="bff5d401">It can store values of primitive (integers, strings, decimals etc.) or reference types. Currently, it uses <a _o="870" _o-sc="21,108" LinkStatus="UNKNOWN" _o-l="21" _o-e="21,187" _o-tl="-1" _o-s="21,107" href="https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/" _o-cl="107" id="7ee59423"><code _o="871" _o-sc="21,109" _o-l="21" _o-e="21,114" _o-tl="-1" _o-s="21,108" _o-cl="108" id="3f146201">List</code></a> as underlying data storage.</p>
</chapter><chapter _o="980" _o-sc="23,5" _o-l="23" _o-e="23,16" _o-tl="-1" _o-s="23,0" _o-cl="0" id="columngroup" title="ColumnGroup">
<p _o="998" _o-sc="25,0" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="524b9352">Container for nested columns. Is used to create column hierarchy.</p>
</chapter><chapter _o="1066" _o-sc="27,5" _o-l="27" _o-e="27,16" _o-tl="-1" _o-s="27,0" _o-cl="0" id="framecolumn" title="FrameColumn">
<p _o="1084" _o-sc="29,0" _o-l="29" _o-e="30,0" _o-tl="-1" _o-s="29,0" _o-cl="0" id="e9392897">Special case of <a _o="1100" _o-sc="29,17" LinkStatus="UNKNOWN" _o-l="29" _o-e="29,45" anchor="valuecolumn" _o-tl="-1" _o-s="29,16" _o-cl="16" id="93e636d3"><code _o="1101" _o-sc="29,18" _o-l="29" _o-e="29,30" _o-tl="-1" _o-s="29,17" _o-cl="17" id="533a756c">ValueColumn</code></a> that stores other <a _o="1148" _o-sc="29,65" LinkStatus="UNKNOWN" _o-l="29" _o-e="29,92" _o-tl="-1" _o-s="29,64" href="DataFrame.md" _o-cl="64" id="765eb1d9"><code _o="1149" _o-sc="29,66" _o-l="29" _o-e="29,77" _o-tl="-1" _o-s="29,65" _o-cl="65" id="90faab49">DataFrames</code></a> as elements.</p>
<p _o="1192" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="b6983d12"><code _o="1192" _o-sc="31,1" _o-l="31" _o-e="31,12" _o-tl="-1" _o-s="31,0" _o-cl="0" id="759da97d">DataFrames</code> stored in <code _o="1215" _o-sc="31,24" _o-l="31" _o-e="31,36" _o-tl="-1" _o-s="31,23" _o-cl="23" id="4634841a">FrameColumn</code> may have different schemas.</p>
<p _o="1259" _o-sc="33,0" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="ffd5ee4b"><code _o="1259" _o-sc="33,1" _o-l="33" _o-e="33,13" _o-tl="-1" _o-s="33,0" _o-cl="0" id="37573298">FrameColumn</code> may appear after <a _o="1290" _o-sc="33,32" LinkStatus="UNKNOWN" _o-l="33" _o-e="33,49" _o-tl="-1" _o-s="33,31" href="read.md" _o-cl="31" id="869c70af">reading</a> from JSON or other hierarchical data structures, or after grouping operations such as <a _o="1395" _o-sc="33,137" LinkStatus="UNKNOWN" _o-l="33" _o-e="33,157" _o-tl="-1" _o-s="33,136" href="groupBy.md" _o-cl="136" id="c469ee09">groupBy</a> or <a _o="1420" _o-sc="33,162" LinkStatus="UNKNOWN" _o-l="33" _o-e="33,178" _o-tl="-1" _o-s="33,161" href="pivot.md" _o-cl="161" id="69362db8">pivot</a>.</p>
</chapter></chapter><chapter _o="1442" _o-sc="35,3" _o-l="35" _o-e="35,20" _o-tl="-1" _o-s="35,0" _o-cl="0" id="column-conditions" title="Column conditions">
</chapter><chapter _o="1464" _o-sc="37,3" _o-l="37" _o-e="37,19" _o-tl="-1" _o-s="37,0" _o-cl="0" id="column-accessors" title="Column accessors">
<p _o="1485" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="3d2ba47d"><code _o="1485" _o-sc="39,1" _o-l="39" _o-e="39,17" _o-tl="-1" _o-s="39,0" _o-cl="0" id="d67d003f">ColumnAccessors</code> are used for <a _o="1516" _o-sc="39,32" LinkStatus="UNKNOWN" _o-l="39" _o-e="39,73" _o-tl="-1" _o-s="39,31" href="columnAccessorsApi.md" _o-cl="31" id="10d745d0">typed data access</a> in <code _o="1562" _o-sc="39,78" _o-l="39" _o-e="39,88" _o-tl="-1" _o-s="39,77" _o-cl="77" id="92091dd6">DataFrame</code>:</p>

<code _o="1610" _o-sc="44,0" _o-l="43" _o-e="63,3" _o-tl="31" _o-s="43,0" style="block" _o-cl="0" id="83ee0c30" lang="kotlin">val age by column&lt;Int>()

// Access fourth cell in the "age" column of dataframe `df`.
// This expression returns `Int` because variable `age` has `ColumnAccessor&lt;Int>` type.
// If dataframe `df` has no column "age" or column "age" has type which is incompatible with `Int`,
// runtime exception will be thrown.
df[age][3] + 5

// Access first cell in the "age" column of dataframe `df`.
df[0][age] * 2

// Returns new dataframe sorted by age column (ascending)
df.sortBy(age)

// Returns new dataframe with the column "year of birth" added
df.add("year of birth") { 2021 - age }

// Returns new dataframe containing only rows with age > 30
df.filter { age > 30 }
</code>

<p _o="2302" _o-sc="67,0" _o-l="67" _o-e="68,0" _o-tl="-1" _o-s="67,0" _o-cl="0" id="aa529210">See <a _o="2306" _o-sc="67,5" LinkStatus="UNKNOWN" _o-l="67" _o-e="67,54" _o-tl="-1" _o-s="67,4" href="createAccessor.md" _o-cl="4" id="6d9039e3">how to create column accessor</a></p>
<p _o="2358" _o-sc="69,0" _o-l="69" _o-e="71,0" _o-tl="-1" _o-s="69,0" _o-cl="0" id="4cd9d99d"><code _o="2358" _o-sc="69,1" _o-l="69" _o-e="69,16" _o-tl="-1" _o-s="69,0" _o-cl="0" id="bfb8f5ad">ColumnAccessor</code> stores column <a _o="2389" _o-sc="69,32" LinkStatus="UNKNOWN" _o-l="69" _o-e="69,52" anchor="properties" _o-tl="-1" _o-s="69,31" _o-cl="31" id="71da60ce"><code _o="2390" _o-sc="69,33" _o-l="69" _o-e="69,38" _o-tl="-1" _o-s="69,32" _o-cl="32" id="61b38450">name</code></a> (for top-level columns) or column path (for nested columns), has type argument that corresponds to column <a _o="2517" _o-sc="69,160" LinkStatus="UNKNOWN" _o-l="69" _o-e="69,180" anchor="properties" _o-tl="-1" _o-s="69,159" _o-cl="159" id="10cdb579"><code _o="2518" _o-sc="69,161" _o-l="69" _o-e="69,166" _o-tl="-1" _o-s="69,160" _o-cl="160" id="509ad4ee">type</code></a>, but doesn't contain any data.
To convert <code _o="2581" _o-sc="70,12" _o-l="70" _o-e="70,27" _o-tl="-1" _o-s="70,11" _o-cl="11" id="6ee9c256">ColumnAccessor</code> into <code _o="2603" _o-sc="70,34" _o-l="70" _o-e="70,45" _o-tl="-1" _o-s="70,33" _o-cl="33" id="fb31ff5b">DataColumn</code> just add values:</p>

<code _o="2670" _o-sc="75,0" _o-l="74" _o-e="78,3" _o-tl="31" _o-s="74,0" style="block" _o-cl="0" id="2854fa4e" lang="kotlin">val age by column&lt;Int>()
val ageCol1 = age.withValues(15, 20)
val ageCol2 = age.withValues(1..10)
</code>

</chapter></topic>