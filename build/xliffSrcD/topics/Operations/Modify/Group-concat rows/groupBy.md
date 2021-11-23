<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="groupBy" title="groupBy" _md-based="true"> 

<p _o="160" _o-sc="5,0" _o-l="5" _o-e="6,0" _o-tl="-1" _o-s="5,0" _o-cl="0" id="61928438">Splits the rows of <code _o="179" _o-sc="5,20" _o-l="5" _o-e="5,30" _o-tl="-1" _o-s="5,19" _o-cl="19" id="ac2bfb89">DataFrame</code> into groups using one or several columns as grouping keys.</p>
<code _o="251" _o-sc="8,0" _o-l="7" _o-e="11,3" _o-tl="-1" _o-s="7,0" style="block" _o-cl="0" id="6a644861" lang="kotlin">groupBy { columns }
    [transformations]
    [aggregations]
</code>
<p _o="327" _o-sc="13,0" _o-l="13" _o-e="14,0" _o-tl="-1" _o-s="13,0" _o-cl="0" id="450f648f">See <a _o="331" _o-sc="13,5" LinkStatus="UNKNOWN" _o-l="13" _o-e="13,42" _o-tl="-1" _o-s="13,4" href="ColumnSelectors.md" _o-cl="4" id="658a08e7">column selectors</a>, <a _o="371" _o-sc="13,45" LinkStatus="UNKNOWN" _o-l="13" _o-e="13,79" anchor="groupby" _o-tl="-1" _o-s="13,44" _o-cl="44" id="a9d36ac8">groupBy transformations</a> and <a _o="411" _o-sc="13,85" LinkStatus="UNKNOWN" _o-l="13" _o-e="13,127" _o-tl="-1" _o-s="13,84" href="aggregateGroupBy.md" _o-cl="84" id="292b7feb">groupBy aggregations</a></p>

<tabs id="15a92364">
<tab id="2906d84f" title="Properties">
<code _o="509" _o-sc="20,0" _o-l="19" _o-e="24,3" _o-tl="-1" _o-s="19,0" style="block" _o-cl="0" id="93370938" lang="kotlin">df.groupBy { name }
df.groupBy { city and name.lastName }
df.groupBy { age / 10 named "ageDecade" }
df.groupBy { expr { name.firstName.length + name.lastName.length } named "nameLength" }
</code>
</tab>
<tab _o="712" _o-sc="26,6" _o-l="26" _o-e="28,0" _o-tl="5" _o-s="26,0" _o-cl="0" id="4ff2ffe" title="Accessors">
<code _o="744" _o-sc="30,0" _o-l="29" _o-e="47,3" _o-tl="70" _o-s="29,0" style="block" _o-cl="0" id="a0d536fe" lang="kotlin">val name by columnGroup()
val lastName by name.column&lt;String>()
val firstName by name.column&lt;String>()
val age by column&lt;Int>()
val city by column&lt;String?>()

df.groupBy { name }
// or
df.groupBy(name)

df.groupBy { city and lastName }
// or
df.groupBy(city, lastName)

df.groupBy { age / 10 named "ageDecade" }

df.groupBy { expr { firstName().length + lastName().length } named "nameLength" }
</code>
</tab>
<tab _o="1154" _o-sc="49,6" _o-l="49" _o-e="51,0" _o-tl="5" _o-s="49,0" _o-cl="0" id="c86853f5" title="Strings">
<code _o="1184" _o-sc="53,0" _o-l="52" _o-e="57,3" _o-tl="171" _o-s="52,0" style="block" _o-cl="0" id="711b9ebc" lang="kotlin">df.groupBy("name")
df.groupBy { "city" and "name"["lastName"] }
df.groupBy { "age".ints() / 10 named "ageDecade" }
df.groupBy { expr { "name"["firstName"]&lt;String>().length + "name"["lastName"]&lt;String>().length } named "nameLength" }
</code>
</tab></tabs>

<p _o="1459" _o-sc="62,0" _o-l="62" _o-e="63,0" _o-tl="-1" _o-s="62,0" _o-cl="0" id="fd9a8866">Returns <code _o="1467" _o-sc="62,9" _o-l="62" _o-e="62,17" _o-tl="-1" _o-s="62,8" _o-cl="8" id="71a137a9">GroupBy</code> object.</p>
<chapter _o="1486" _o-sc="64,4" _o-l="64" _o-e="64,11" _o-tl="-1" _o-s="64,0" _o-cl="0" id="groupby" title="GroupBy">
<p _o="1499" _o-sc="66,0" _o-l="66" _o-e="67,0" _o-tl="-1" _o-s="66,0" _o-cl="0" id="a8969be5"><code _o="1499" _o-sc="66,1" _o-l="66" _o-e="66,9" _o-tl="-1" _o-s="66,0" _o-cl="0" id="b191b4c6">GroupBy</code> is a <code _o="1514" _o-sc="66,16" _o-l="66" _o-e="66,26" _o-tl="-1" _o-s="66,15" _o-cl="15" id="1630f693">DataFrame</code> with one chosen <a _o="1542" _o-sc="66,44" LinkStatus="UNKNOWN" _o-l="66" _o-e="66,85" _o-tl="-1" _o-s="66,43" href="DataColumn.md#framecolumn" _o-cl="43" id="ed8bc0cd"><code _o="1543" _o-sc="66,45" _o-l="66" _o-e="66,57" _o-tl="-1" _o-s="66,44" _o-cl="44" id="3565eef5">FrameColumn</code></a> containing data groups.</p>
<p _o="1610" _o-sc="68,0" _o-l="68" _o-e="69,0" _o-tl="-1" _o-s="68,0" _o-cl="0" id="bfe8892">It supports the following operations:</p>
<list _o="1648" _o-sc="69,0" _o-l="69" _o-e="73,0" _o-tl="-1" _o-s="69,0" _o-cl="0" id="a9c64f88">
<li _o="1648" _o-sc="69,2" _o-l="69" _o-e="70,0" _o-tl="-1" _o-s="69,0" _o-cl="0" id="c9b9f00"><a _o="1650" _o-sc="69,3" LinkStatus="UNKNOWN" _o-l="69" _o-e="69,17" _o-tl="-1" _o-s="69,2" href="add.md" _o-cl="2" id="ecaf4b6f"><code _o="1651" _o-sc="69,4" _o-l="69" _o-e="69,8" _o-tl="-1" _o-s="69,3" _o-cl="3" id="1666eed5">add</code></a></li>
<li _o="1666" _o-sc="70,2" _o-l="70" _o-e="71,0" _o-tl="-1" _o-s="70,0" _o-cl="0" id="cf46e35e"><a _o="1668" _o-sc="70,3" LinkStatus="UNKNOWN" _o-l="70" _o-e="70,23" _o-tl="-1" _o-s="70,2" href="sortBy.md" _o-cl="2" id="9d0e0b2d"><code _o="1669" _o-sc="70,4" _o-l="70" _o-e="70,11" _o-tl="-1" _o-s="70,3" _o-cl="3" id="a31ea2f3">sortBy</code></a></li>
<li _o="1690" _o-sc="71,2" _o-l="71" _o-e="72,0" _o-tl="-1" _o-s="71,0" _o-cl="0" id="199e118"><a _o="1692" _o-sc="71,3" LinkStatus="UNKNOWN" _o-l="71" _o-e="71,17" _o-tl="-1" _o-s="71,2" href="map.md" _o-cl="2" id="66649170"><code _o="1693" _o-sc="71,4" _o-l="71" _o-e="71,8" _o-tl="-1" _o-s="71,3" _o-cl="3" id="675c3c94">map</code></a></li>
<li _o="1708" _o-sc="72,2" _o-l="72" _o-e="73,0" _o-tl="-1" _o-s="72,0" _o-cl="0" id="e0497c36"><a _o="1710" _o-sc="72,3" LinkStatus="UNKNOWN" _o-l="72" _o-e="72,35" _o-tl="-1" _o-s="72,2" href="pivot.md#pivot-groupby" _o-cl="2" id="67091d97"><code _o="1711" _o-sc="72,4" _o-l="72" _o-e="72,10" _o-tl="-1" _o-s="72,3" _o-cl="3" id="40aa1e78">pivot</code></a></li>
</list>
<p _o="1745" _o-sc="74,0" _o-l="74" _o-e="75,0" _o-tl="-1" _o-s="74,0" _o-cl="0" id="92490e14">Any <code _o="1749" _o-sc="74,5" _o-l="74" _o-e="74,15" _o-tl="-1" _o-s="74,4" _o-cl="4" id="da968f2">DataFrame</code> with <code _o="1766" _o-sc="74,22" _o-l="74" _o-e="74,34" _o-tl="-1" _o-s="74,21" _o-cl="21" id="a4569823">FrameColumn</code> can be reinterpreted as <code _o="1804" _o-sc="74,60" _o-l="74" _o-e="74,68" _o-tl="-1" _o-s="74,59" _o-cl="59" id="fa511dae">GroupBy</code>:</p>

<code _o="1848" _o-sc="79,0" _o-l="78" _o-e="84,3" _o-tl="-1" _o-s="78,0" style="block" _o-cl="0" id="5bcd33ac" lang="kotlin">val key by columnOf(1, 2) // create int column with name "key"
val data by columnOf(df[0..3], df[4..6]) // create frame column with name "data"
val df = dataFrameOf(key, data) // create dataframe with two columns

df.asGroupBy { data } // convert dataframe to GroupBy by interpreting 'data' column as groups
</code>

<p _o="2184" _o-sc="88,0" _o-l="88" _o-e="89,0" _o-tl="-1" _o-s="88,0" _o-cl="0" id="38f3671e">And any <code _o="2192" _o-sc="88,9" _o-l="88" _o-e="88,17" _o-tl="-1" _o-s="88,8" _o-cl="8" id="cfcd9549">GroupBy</code> can be reinterpreted as <code _o="2226" _o-sc="88,43" _o-l="88" _o-e="88,53" _o-tl="-1" _o-s="88,42" _o-cl="42" id="1d64d714">DataFrame</code> with <code _o="2243" _o-sc="88,60" _o-l="88" _o-e="88,72" _o-tl="-1" _o-s="88,59" _o-cl="59" id="9752c43f">FrameColumn</code>:</p>

<code _o="2287" _o-sc="93,0" _o-l="92" _o-e="94,3" _o-tl="-1" _o-s="92,0" style="block" _o-cl="0" id="49e7a15f" lang="kotlin">df.groupBy { city }.toDataFrame()
</code>

<p _o="2349" _o-sc="98,0" _o-l="98" _o-e="99,0" _o-tl="-1" _o-s="98,0" _o-cl="0" id="4bafd3b4">Use <a _o="2353" _o-sc="98,5" LinkStatus="UNKNOWN" _o-l="98" _o-e="98,25" _o-tl="-1" _o-s="98,4" href="concat.md" _o-cl="4" id="cfcbf10"><code _o="2354" _o-sc="98,6" _o-l="98" _o-e="98,13" _o-tl="-1" _o-s="98,5" _o-cl="5" id="f1791b97">concat</code></a> to union all data groups of <code _o="2403" _o-sc="98,55" _o-l="98" _o-e="98,63" _o-tl="-1" _o-s="98,54" _o-cl="54" id="ad7842bd">GroupBy</code> into original <code _o="2427" _o-sc="98,79" _o-l="98" _o-e="98,89" _o-tl="-1" _o-s="98,78" _o-cl="78" id="c9e167cf">DataFrame</code> preserving new order of rows produced by grouping:</p>

<code _o="2518" _o-sc="103,0" _o-l="102" _o-e="104,3" _o-tl="-1" _o-s="102,0" style="block" _o-cl="0" id="afee533a" lang="kotlin">df.groupBy { name }.concat()
</code>

<p _o="2575" _o-sc="108,0" _o-l="108" _o-e="109,0" _o-tl="-1" _o-s="108,0" _o-cl="0" id="d5a658ab">To compute one or several aggregation statistics over <code _o="2629" _o-sc="108,55" _o-l="108" _o-e="108,63" _o-tl="-1" _o-s="108,54" _o-cl="54" id="2add5199">GroupBy</code> see <a _o="2643" _o-sc="108,69" LinkStatus="UNKNOWN" _o-l="108" _o-e="108,110" _o-tl="-1" _o-s="108,68" href="aggregateGroupBy.md" _o-cl="68" id="4d042dae">GroupBy aggregation</a></p>
</chapter></topic>