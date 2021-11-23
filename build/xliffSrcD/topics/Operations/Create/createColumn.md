<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="createColumn" title="Create DataColumn" _md-based="true"> 
<p _o="102" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="83686f82">This section describes ways to create <a _o="140" _o-sc="3,39" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,67" _o-tl="-1" _o-s="3,38" href="DataColumn.md" _o-cl="38" id="69afcfc9"><code _o="141" _o-sc="3,40" _o-l="3" _o-e="3,51" _o-tl="-1" _o-s="3,39" _o-cl="39" id="a09cac0a">DataColumn</code></a>.</p>
<chapter _o="172" _o-sc="5,4" _o-l="5" _o-e="5,12" _o-tl="-1" _o-s="5,0" _o-cl="0" id="columnof" title="columnOf">
<p _o="186" _o-sc="7,0" _o-l="7" _o-e="8,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="2967f68e">Returns new column with given elements. Column <a _o="233" _o-sc="7,48" LinkStatus="UNKNOWN" _o-l="7" _o-e="7,81" _o-tl="-1" _o-s="7,47" href="DataColumn.md#properties" _o-cl="47" id="3ad1472c"><code _o="234" _o-sc="7,49" _o-l="7" _o-e="7,54" _o-tl="-1" _o-s="7,48" _o-cl="48" id="5336fc3d">type</code></a> is deduced from compile-time type of elements, column <a _o="322" _o-sc="7,137" LinkStatus="UNKNOWN" _o-l="7" _o-e="7,170" _o-tl="-1" _o-s="7,136" href="DataColumn.md#properties" _o-cl="136" id="3b2adfde"><code _o="323" _o-sc="7,138" _o-l="7" _o-e="7,143" _o-tl="-1" _o-s="7,137" _o-cl="137" id="e6d5125c">name</code></a> is taken from the name of the variable.</p>

<code _o="433" _o-sc="12,0" _o-l="11" _o-e="14,3" _o-tl="-1" _o-s="11,0" style="block" _o-cl="0" id="3759c5d4" lang="kotlin">// Create ValueColumn with name 'student' and two elements of type String
val student by columnOf("Alice", "Bob")
</code>

<p _o="575" _o-sc="18,0" _o-l="18" _o-e="19,0" _o-tl="-1" _o-s="18,0" _o-cl="0" id="209cf1f8">To assign column name explicitly, use <code _o="613" _o-sc="18,39" _o-l="18" _o-e="18,45" _o-tl="-1" _o-s="18,38" _o-cl="38" id="36f312da">named</code> infix function and replace <code _o="648" _o-sc="18,74" _o-l="18" _o-e="18,77" _o-tl="-1" _o-s="18,73" _o-cl="73" id="5f69ba6a">by</code> with <code _o="658" _o-sc="18,84" _o-l="18" _o-e="18,86" _o-tl="-1" _o-s="18,83" _o-cl="83" id="1aad52ae">=</code>.</p>

<code _o="697" _o-sc="23,0" _o-l="22" _o-e="24,3" _o-tl="-1" _o-s="22,0" style="block" _o-cl="0" id="d2f6ee9f" lang="kotlin">val column = columnOf("Alice", "Bob") named "student"
</code>

<p _o="779" _o-sc="28,0" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="c30ba771">When column elements are columns themselves, it returns <a _o="835" _o-sc="28,57" LinkStatus="UNKNOWN" _o-l="28" _o-e="28,98" _o-tl="-1" _o-s="28,56" href="DataColumn.md#columngroup" _o-cl="56" id="72b028e9"><code _o="836" _o-sc="28,58" _o-l="28" _o-e="28,70" _o-tl="-1" _o-s="28,57" _o-cl="57" id="fc98562b">ColumnGroup</code></a>:</p>

<code _o="911" _o-sc="33,0" _o-l="32" _o-e="38,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="a05430b1" lang="kotlin">val firstName by columnOf("Alice", "Bob")
val lastName by columnOf("Cooper", "Marley")

// Create ColumnGroup with two nested columns
val fullName by columnOf(firstName, lastName)
</code>

<p _o="1119" _o-sc="42,0" _o-l="42" _o-e="43,0" _o-tl="-1" _o-s="42,0" _o-cl="0" id="656158f3">When column elements are <a _o="1144" _o-sc="42,26" LinkStatus="UNKNOWN" _o-l="42" _o-e="42,54" _o-tl="-1" _o-s="42,25" href="DataColumn.md" _o-cl="25" id="f9fd8277"><code _o="1145" _o-sc="42,27" _o-l="42" _o-e="42,38" _o-tl="-1" _o-s="42,26" _o-cl="26" id="b92230bf">DataFrames</code></a> it returns <a _o="1185" _o-sc="42,67" LinkStatus="UNKNOWN" _o-l="42" _o-e="42,108" _o-tl="-1" _o-s="42,66" href="DataColumn.md#framecolumn" _o-cl="66" id="da1e6200"><code _o="1186" _o-sc="42,68" _o-l="42" _o-e="42,80" _o-tl="-1" _o-s="42,67" _o-cl="67" id="6c58c6eb">FrameColumn</code></a>:</p>

<code _o="1261" _o-sc="47,0" _o-l="46" _o-e="52,3" _o-tl="-1" _o-s="46,0" style="block" _o-cl="0" id="85a607b1" lang="kotlin">val df1 = dataFrameOf("name", "age")("Alice", 20, "Bob", 25)
val df2 = dataFrameOf("name", "temp")("Mark", 36.6)

// Create FrameColumn with two elements of type DataFrame
val frames by columnOf(df1, df2)
</code>

</chapter><chapter _o="1494" _o-sc="56,4" _o-l="56" _o-e="56,12" _o-tl="-1" _o-s="56,0" _o-cl="0" id="tocolumn" title="toColumn">
<p _o="1508" _o-sc="58,0" _o-l="58" _o-e="59,0" _o-tl="-1" _o-s="58,0" _o-cl="0" id="70c14ee8">Converts <code _o="1517" _o-sc="58,10" _o-l="58" _o-e="58,19" _o-tl="-1" _o-s="58,9" _o-cl="9" id="38f1b55d">Iterable</code> of values into column.</p>

<code _o="1587" _o-sc="63,0" _o-l="62" _o-e="64,3" _o-tl="-1" _o-s="62,0" style="block" _o-cl="0" id="de72d2c7" lang="kotlin">listOf("Alice", "Bob").toColumn("name")
</code>

<p _o="1655" _o-sc="68,0" _o-l="68" _o-e="69,0" _o-tl="-1" _o-s="68,0" _o-cl="0" id="9d4a4c0c">To compute column type at runtime by scanning through actual values, set <code _o="1728" _o-sc="68,74" _o-l="68" _o-e="68,85" _o-tl="-1" _o-s="68,73" _o-cl="73" id="abedf96f">Infer.Type</code> option.</p>
<p _o="1751" _o-sc="70,0" _o-l="70" _o-e="71,0" _o-tl="-1" _o-s="70,0" _o-cl="0" id="dfecab92">To inspect values only for nullability set <code _o="1794" _o-sc="70,44" _o-l="70" _o-e="70,56" _o-tl="-1" _o-s="70,43" _o-cl="43" id="b726b3be">Infer.Nulls</code> option.</p>

<code _o="1856" _o-sc="75,0" _o-l="74" _o-e="80,3" _o-tl="31" _o-s="74,0" style="block" _o-cl="0" id="a4c085e5" lang="kotlin">val values: List&lt;Any?> = listOf(1, 2.5)

values.toColumn("data") // type: Any?
values.toColumn("data", Infer.Type) // type: Number
values.toColumn("data", Infer.Nulls) // type: Any
</code>

</chapter><chapter _o="2065" _o-sc="84,4" _o-l="84" _o-e="84,14" _o-tl="-1" _o-s="84,0" _o-cl="0" id="tocolumnof" title="toColumnOf">
<p _o="2081" _o-sc="86,0" _o-l="86" _o-e="87,0" _o-tl="-1" _o-s="86,0" _o-cl="0" id="9adb65ee">Converts <code _o="2090" _o-sc="86,10" _o-l="86" _o-e="86,19" _o-tl="-1" _o-s="86,9" _o-cl="9" id="7502b394">Iterable</code> of values into column of given type</p>

<code _o="2175" _o-sc="91,0" _o-l="90" _o-e="94,3" _o-tl="31" _o-s="90,0" style="block" _o-cl="0" id="45eee4ee" lang="kotlin">val values: List&lt;Any?> = listOf(1, 2.5)

values.toColumnOf&lt;Number?>("data") // type: Number?
</code>

</chapter></topic>