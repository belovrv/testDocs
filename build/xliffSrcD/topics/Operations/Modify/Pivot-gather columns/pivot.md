<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="pivot" title="pivot" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="6719f33">Splits the rows of <code _o="111" _o-sc="4,20" _o-l="4" _o-e="4,30" _o-tl="-1" _o-s="4,19" _o-cl="19" id="75e84e67">DataFrame</code> and groups them horizontally into new columns based on values from one or several columns of original <code _o="225" _o-sc="4,134" _o-l="4" _o-e="4,144" _o-tl="-1" _o-s="4,133" _o-cl="133" id="1449222d">DataFrame</code>.</p>
<p _o="239" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="a86d751c">Pass a column to <code _o="256" _o-sc="6,18" _o-l="6" _o-e="6,24" _o-tl="-1" _o-s="6,17" _o-cl="17" id="6fdf2e2d">pivot</code> function to use its values as grouping keys and names for new columns.</p>

<tabs id="6b98bf9d">
<tab id="82e1130f" title="Properties">
<code _o="387" _o-sc="13,0" _o-l="12" _o-e="14,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="c56e75f" lang="kotlin">df.pivot { city }
</code>
</tab>
<tab _o="420" _o-sc="16,6" _o-l="16" _o-e="18,0" _o-tl="5" _o-s="16,0" _o-cl="0" id="eb14d0e5" title="Accessors">
<code _o="452" _o-sc="20,0" _o-l="19" _o-e="23,3" _o-tl="36" _o-s="19,0" style="block" _o-cl="0" id="8aad3d8d" lang="kotlin">val city by column&lt;String?>()

df.pivot { city }
</code>
</tab>
<tab _o="516" _o-sc="25,6" _o-l="25" _o-e="27,0" _o-tl="5" _o-s="25,0" _o-cl="0" id="5eadfa4a" title="Strings">
<code _o="546" _o-sc="29,0" _o-l="28" _o-e="30,3" _o-tl="-1" _o-s="28,0" style="block" _o-cl="0" id="a1ab87f5" lang="kotlin">df.pivot("city")
</code>
</tab></tabs>

<p _o="605" _o-sc="35,0" _o-l="35" _o-e="36,0" _o-tl="-1" _o-s="35,0" _o-cl="0" id="e5cd9f20">Returns <code _o="613" _o-sc="35,9" _o-l="35" _o-e="35,15" _o-tl="-1" _o-s="35,8" _o-cl="8" id="7c5059b4">Pivot</code>: an intermediate object that can be configured for further transformation and aggregation of data.</p>
<p _o="721" _o-sc="37,0" _o-l="37" _o-e="38,0" _o-tl="-1" _o-s="37,0" _o-cl="0" id="b5ab4c8a">See <a _o="725" _o-sc="37,5" LinkStatus="UNKNOWN" _o-l="37" _o-e="37,43" _o-tl="-1" _o-s="37,4" href="aggregatePivot.md" _o-cl="4" id="7b0cee0e">pivot aggregations</a></p>
<p _o="766" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="4ddd9969">By default, pivoted column will be replaced with new columns generated from its values. Instead, you can nest new columns as sub-columns of original column using <code _o="928" _o-sc="39,163" _o-l="39" _o-e="39,170" _o-tl="-1" _o-s="39,162" _o-cl="162" id="4891b837">inward</code> flag:</p>

<tabs id="ea519ad9">
<tab id="4866a69f" title="Properties">
<code _o="1001" _o-sc="46,0" _o-l="45" _o-e="47,3" _o-tl="-1" _o-s="45,0" style="block" _o-cl="0" id="7fc70e0a" lang="kotlin">df.pivot(inward = true) { city }
</code>
</tab>
<tab _o="1049" _o-sc="49,6" _o-l="49" _o-e="51,0" _o-tl="5" _o-s="49,0" _o-cl="0" id="7fbcee58" title="Accessors">
<code _o="1081" _o-sc="53,0" _o-l="52" _o-e="56,3" _o-tl="36" _o-s="52,0" style="block" _o-cl="0" id="8abe8790" lang="kotlin">val city by column&lt;String?>()

df.pivot(inward = true) { city }
</code>
</tab>
<tab _o="1160" _o-sc="58,6" _o-l="58" _o-e="60,0" _o-tl="5" _o-s="58,0" _o-cl="0" id="7e79f907" title="Strings">
<code _o="1190" _o-sc="62,0" _o-l="61" _o-e="63,3" _o-tl="-1" _o-s="61,0" style="block" _o-cl="0" id="bcc9e6ee" lang="kotlin">df.pivot("city", inward = true)
</code>
</tab></tabs>

<p _o="1264" _o-sc="68,0" _o-l="68" _o-e="69,0" _o-tl="-1" _o-s="68,0" _o-cl="0" id="361be8c6">To pivot several columns in one operation you can combine them using <code _o="1333" _o-sc="68,70" _o-l="68" _o-e="68,74" _o-tl="-1" _o-s="68,69" _o-cl="69" id="2ebef8d5">and</code> or <code _o="1342" _o-sc="68,79" _o-l="68" _o-e="68,84" _o-tl="-1" _o-s="68,78" _o-cl="78" id="a03c5d70">then</code> infix function:</p>
<list _o="1365" _o-sc="69,0" _o-l="69" _o-e="71,0" _o-tl="-1" _o-s="69,0" _o-cl="0" id="ff4aa1e5">
<li _o="1365" _o-sc="69,2" _o-l="69" _o-e="70,0" _o-tl="-1" _o-s="69,0" _o-cl="0" id="bfe48936"><code _o="1367" _o-sc="69,3" _o-l="69" _o-e="69,7" _o-tl="-1" _o-s="69,2" _o-cl="2" id="66d2dd56">and</code> will pivot columns independently</li>
<li _o="1406" _o-sc="70,2" _o-l="70" _o-e="71,0" _o-tl="-1" _o-s="70,0" _o-cl="0" id="edafe771"><code _o="1408" _o-sc="70,3" _o-l="70" _o-e="70,8" _o-tl="-1" _o-s="70,2" _o-cl="2" id="c4db6bbc">then</code> will create column hierarchy based on possible combinations of column values</li>
</list>

<tabs id="3193bf9c">
<tab id="8d1878ee" title="Properties">
<code _o="1545" _o-sc="77,0" _o-l="76" _o-e="79,3" _o-tl="-1" _o-s="76,0" style="block" _o-cl="0" id="1c94f3b8" lang="kotlin">df.pivot { city and name.firstName }
df.pivot { city then name.firstName }
</code>
</tab>
<tab _o="1635" _o-sc="81,6" _o-l="81" _o-e="83,0" _o-tl="5" _o-s="81,0" _o-cl="0" id="20a6bfa1" title="Accessors">
<code _o="1667" _o-sc="85,0" _o-l="84" _o-e="91,3" _o-tl="36" _o-s="84,0" style="block" _o-cl="0" id="daa7d6e1" lang="kotlin">val city by column&lt;String?>()
val name by columnGroup()
val firstName by name.column&lt;String>()

df.pivot { city and firstName }
df.pivot { city then firstName }
</code>
</tab>
<tab _o="1843" _o-sc="93,6" _o-l="93" _o-e="95,0" _o-tl="5" _o-s="93,0" _o-cl="0" id="ac6f1756" title="Strings">
<code _o="1873" _o-sc="97,0" _o-l="96" _o-e="99,3" _o-tl="-1" _o-s="96,0" style="block" _o-cl="0" id="3d0ac4e0" lang="kotlin">df.pivot { "city" and "name"["firstName"] }
df.pivot { "city" then "name"["firstName"] }
</code>
</tab></tabs>

<chapter _o="2004" _o-sc="104,3" _o-l="104" _o-e="104,18" _o-tl="-1" _o-s="104,0" _o-cl="0" id="pivot-groupby" title="pivot + groupBy">
<p _o="2024" _o-sc="106,0" _o-l="106" _o-e="107,0" _o-tl="-1" _o-s="106,0" _o-cl="0" id="f929faa7">To create matrix table that is expanded both horizontally and vertically, apply <code _o="2104" _o-sc="106,81" _o-l="106" _o-e="106,89" _o-tl="-1" _o-s="106,80" _o-cl="80" id="7df692bf">groupBy</code> function at <code _o="2126" _o-sc="106,103" _o-l="106" _o-e="106,109" _o-tl="-1" _o-s="106,102" _o-cl="102" id="8b162cdc">Pivot</code> passing the columns for vertical grouping. Reversed order of <code _o="2195" _o-sc="106,172" _o-l="106" _o-e="106,178" _o-tl="-1" _o-s="106,171" _o-cl="171" id="cdeac04">pivot</code> and <code _o="2207" _o-sc="106,184" _o-l="106" _o-e="106,192" _o-tl="-1" _o-s="106,183" _o-cl="183" id="41fa8e13">groupBy</code> operations will produce the same result.</p>

<tabs id="862e9ae4">
<tab id="c32ba156" title="Properties">
<code _o="2317" _o-sc="113,0" _o-l="112" _o-e="116,3" _o-tl="-1" _o-s="112,0" style="block" _o-cl="0" id="8a4da15" lang="kotlin">df.pivot { city }.groupBy { name }
// same as
df.groupBy { name }.pivot { city }
</code>
</tab>
<tab _o="2413" _o-sc="118,6" _o-l="118" _o-e="120,0" _o-tl="5" _o-s="118,0" _o-cl="0" id="1268788c" title="Accessors">
<code _o="2445" _o-sc="122,0" _o-l="121" _o-e="128,3" _o-tl="36" _o-s="121,0" style="block" _o-cl="0" id="13f0f9fd" lang="kotlin">val city by column&lt;String?>()
val name by columnGroup()

df.pivot { city }.groupBy { name }
// same as
df.groupBy { name }.pivot { city }
</code>
</tab>
<tab _o="2598" _o-sc="130,6" _o-l="130" _o-e="132,0" _o-tl="5" _o-s="130,0" _o-cl="0" id="906ae06a" title="Strings">
<code _o="2628" _o-sc="134,0" _o-l="133" _o-e="137,3" _o-tl="-1" _o-s="133,0" style="block" _o-cl="0" id="9f10ec57" lang="kotlin">df.pivot("city").groupBy("name")
// same as
df.groupBy("name").pivot("city")
</code>
</tab></tabs>

<p _o="2747" _o-sc="142,0" _o-l="142" _o-e="143,0" _o-tl="-1" _o-s="142,0" _o-cl="0" id="64dcd6d0">Combination of <code _o="2762" _o-sc="142,16" _o-l="142" _o-e="142,22" _o-tl="-1" _o-s="142,15" _o-cl="15" id="90755488">pivot</code> and <code _o="2774" _o-sc="142,28" _o-l="142" _o-e="142,36" _o-tl="-1" _o-s="142,27" _o-cl="27" id="a521a030">groupBy</code> operations returns <code _o="2803" _o-sc="142,57" _o-l="142" _o-e="142,70" _o-tl="-1" _o-s="142,56" _o-cl="56" id="1ed5d833">PivotGroupBy</code> that can be used for further aggregation of data groups within matrix cells.</p>
<p _o="2897" _o-sc="144,0" _o-l="144" _o-e="145,0" _o-tl="-1" _o-s="144,0" _o-cl="0" id="cc81c4f8">See <a _o="2901" _o-sc="144,5" LinkStatus="UNKNOWN" _o-l="144" _o-e="144,43" _o-tl="-1" _o-s="144,4" href="aggregatePivot.md" _o-cl="4" id="7d17eace">pivot aggregations</a></p>
<p _o="2942" _o-sc="146,0" _o-l="146" _o-e="147,0" _o-tl="-1" _o-s="146,0" _o-cl="0" id="8457ee15">To group by all columns except pivoted use <code _o="2985" _o-sc="146,44" _o-l="146" _o-e="146,57" _o-tl="-1" _o-s="146,43" _o-cl="43" id="af78404b">groupByOther</code>:</p>

<code _o="3033" _o-sc="151,0" _o-l="150" _o-e="152,3" _o-tl="-1" _o-s="150,0" style="block" _o-cl="0" id="25b09000" lang="kotlin">df.pivot { city }.groupByOther()
</code>

<p _o="3094" _o-sc="156,0" _o-l="156" _o-e="157,0" _o-tl="-1" _o-s="156,0" _o-cl="0" id="b0714610">Pivot operation can be performed without any data aggregation:</p>
<list _o="3157" _o-sc="157,0" _o-l="157" _o-e="159,0" _o-tl="-1" _o-s="157,0" _o-cl="0" id="8e71a602">
<li _o="3157" _o-sc="157,2" _o-l="157" _o-e="158,0" _o-tl="-1" _o-s="157,0" _o-cl="0" id="d04886cf"><code _o="3159" _o-sc="157,3" _o-l="157" _o-e="157,9" _o-tl="-1" _o-s="157,2" _o-cl="2" id="1052fb87">Pivot</code> object can be converted to <code _o="3194" _o-sc="157,38" _o-l="157" _o-e="157,46" _o-tl="-1" _o-s="157,37" _o-cl="37" id="1f1f0500">DataRow</code> or <code _o="3207" _o-sc="157,51" _o-l="157" _o-e="157,61" _o-tl="-1" _o-s="157,50" _o-cl="50" id="f94db7bc">DataFrame</code>.</li>
<li _o="3220" _o-sc="158,2" _o-l="158" _o-e="159,0" _o-tl="-1" _o-s="158,0" _o-cl="0" id="c63b310e"><code _o="3222" _o-sc="158,3" _o-l="158" _o-e="158,16" _o-tl="-1" _o-s="158,2" _o-cl="2" id="42ec9fd2">GroupedPivot</code> object can be converted to <code _o="3264" _o-sc="158,45" _o-l="158" _o-e="158,55" _o-tl="-1" _o-s="158,44" _o-cl="44" id="c4e87b72">DataFrame</code>.</li>
</list>
<p _o="3278" _o-sc="160,0" _o-l="160" _o-e="161,0" _o-tl="-1" _o-s="160,0" _o-cl="0" id="4e49de8d">Generated columns will have type <a _o="3311" _o-sc="160,34" LinkStatus="UNKNOWN" _o-l="160" _o-e="160,75" _o-tl="-1" _o-s="160,33" href="DataColumn.md#framecolumn" _o-cl="33" id="1dab704f"><code _o="3312" _o-sc="160,35" _o-l="160" _o-e="160,47" _o-tl="-1" _o-s="160,34" _o-cl="34" id="8ccda416">FrameColumn</code></a> and will contain data groups.</p>

<code _o="3420" _o-sc="165,0" _o-l="164" _o-e="167,3" _o-tl="-1" _o-s="164,0" style="block" _o-cl="0" id="d6611953" lang="kotlin">df.pivot { city }.toDataRow()
df.pivot { city }.groupBy { name }.toDataFrame()
</code>

</chapter><chapter _o="3527" _o-sc="171,3" _o-l="171" _o-e="171,13" _o-tl="-1" _o-s="171,0" _o-cl="0" id="pivotcount" title="pivotCount">
<p _o="3542" _o-sc="173,0" _o-l="173" _o-e="174,0" _o-tl="-1" _o-s="173,0" _o-cl="0" id="f5d7af24">Pivots with <code _o="3554" _o-sc="173,13" _o-l="173" _o-e="173,17" _o-tl="-1" _o-s="173,12" _o-cl="12" id="897ce3e2">Int</code> count statistics one or several columns preserving all other columns of <code _o="3632" _o-sc="173,91" _o-l="173" _o-e="173,101" _o-tl="-1" _o-s="173,90" _o-cl="90" id="6e4058f6">DataFrame</code>.</p>

<code _o="3670" _o-sc="178,0" _o-l="177" _o-e="181,3" _o-tl="-1" _o-s="177,0" style="block" _o-cl="0" id="6ed5ccd9" lang="kotlin">df.pivotCount { city }
// same as
df.pivot(inward = true) { city }.groupByOther().count()
</code>

</chapter><chapter _o="3788" _o-sc="185,3" _o-l="185" _o-e="185,15" _o-tl="-1" _o-s="185,0" _o-cl="0" id="pivotmatches" title="pivotMatches">
<p _o="3805" _o-sc="187,0" _o-l="187" _o-e="188,0" _o-tl="-1" _o-s="187,0" _o-cl="0" id="2bba1fb9">Pivots with <code _o="3817" _o-sc="187,13" _o-l="187" _o-e="187,21" _o-tl="-1" _o-s="187,12" _o-cl="12" id="e2cee871">Boolean</code> statistics one or several columns preserving all other columns of <code _o="3893" _o-sc="187,89" _o-l="187" _o-e="187,99" _o-tl="-1" _o-s="187,88" _o-cl="88" id="a97774a">DataFrame</code>.</p>

<code _o="3933" _o-sc="192,0" _o-l="191" _o-e="195,3" _o-tl="-1" _o-s="191,0" style="block" _o-cl="0" id="4171d3fc" lang="kotlin">df.pivotMatches { city }
// same as
df.pivot(inward = true) { city }.groupByOther().matches()
</code>

</chapter></topic>