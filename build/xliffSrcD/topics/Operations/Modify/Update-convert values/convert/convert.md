<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="convert" title="convert" _md-based="true"> 
<p _o="92" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="c3785567">Returns <code _o="100" _o-sc="3,9" _o-l="3" _o-e="3,19" _o-tl="-1" _o-s="3,8" _o-cl="8" id="55802e44">DataFrame</code> with changed values in some columns. Allows to change column types.</p>
<code _o="181" _o-sc="6,0" _o-l="5" _o-e="12,3" _o-tl="130" _o-s="5,0" style="block" _o-cl="0" id="87581f48" lang="kotlin">convert { columnsSelector }
    .with { rowExpression } | .perRowCol { rowColExpression } | .withValue(value)  | to&lt;Type>() | to { colExpression }

rowExpression = DataRow.(OldValue) -> NewValue
rowColExpression = DataRow.(DataColumn) -> NewValue
colExpression = DataFrame.(DataColumn) -> DataColumn
</code>
<p _o="496" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="a270f089">See <a _o="500" _o-sc="14,5" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,42" _o-tl="-1" _o-s="14,4" href="ColumnSelectors.md" _o-cl="4" id="4a38eac7">column selectors</a> and <a _o="543" _o-sc="14,48" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,92" _o-tl="-1" _o-s="14,47" href="DataRow.md#row-expressions" _o-cl="47" id="8cabe95e">row expressions</a></p>

<code _o="611" _o-sc="19,0" _o-l="18" _o-e="21,3" _o-tl="77" _o-s="18,0" style="block" _o-cl="0" id="b01aceec" lang="kotlin">df.convert { age }.with { it.toDouble() }
df.convert { dfsOf&lt;String>() }.with { it.toCharArray().toList() }
</code>

<p _o="747" _o-sc="25,0" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="95999e90"><code _o="747" _o-sc="25,1" _o-l="25" _o-e="25,9" _o-tl="-1" _o-s="25,0" _o-cl="0" id="603f649a">convert</code> supports automatic type conversions between the following types:</p>
<list _o="822" _o-sc="26,0" _o-l="26" _o-e="36,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="63a98409">
<li _o="822" _o-sc="26,2" _o-l="26" _o-e="27,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="d42f9df3"><code _o="824" _o-sc="26,3" _o-l="26" _o-e="26,7" _o-tl="-1" _o-s="26,2" _o-cl="2" id="3f9d9850">Int</code></li>
<li _o="830" _o-sc="27,2" _o-l="27" _o-e="28,0" _o-tl="-1" _o-s="27,0" _o-cl="0" id="dd399dc3"><code _o="832" _o-sc="27,3" _o-l="27" _o-e="27,10" _o-tl="-1" _o-s="27,2" _o-cl="2" id="5c38161f">String</code></li>
<li _o="841" _o-sc="28,2" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="68d6650e"><code _o="843" _o-sc="28,3" _o-l="28" _o-e="28,10" _o-tl="-1" _o-s="28,2" _o-cl="2" id="517ed0af">Double</code></li>
<li _o="852" _o-sc="29,2" _o-l="29" _o-e="30,0" _o-tl="-1" _o-s="29,0" _o-cl="0" id="5b60489c"><code _o="854" _o-sc="29,3" _o-l="29" _o-e="29,8" _o-tl="-1" _o-s="29,2" _o-cl="2" id="5bd103b">Long</code></li>
<li _o="861" _o-sc="30,2" _o-l="30" _o-e="31,0" _o-tl="-1" _o-s="30,0" _o-cl="0" id="3756572e"><code _o="863" _o-sc="30,3" _o-l="30" _o-e="30,9" _o-tl="-1" _o-s="30,2" _o-cl="2" id="7ef6bfc">Short</code></li>
<li _o="871" _o-sc="31,2" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="81e917b3"><code _o="873" _o-sc="31,3" _o-l="31" _o-e="31,9" _o-tl="-1" _o-s="31,2" _o-cl="2" id="abb15b2e">Float</code></li>
<li _o="881" _o-sc="32,2" _o-l="32" _o-e="33,0" _o-tl="-1" _o-s="32,0" _o-cl="0" id="3d1eaff2"><code _o="883" _o-sc="32,3" _o-l="32" _o-e="32,14" _o-tl="-1" _o-s="32,2" _o-cl="2" id="a4a3c42b">BigDecimal</code></li>
<li _o="896" _o-sc="33,2" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="c5854b89"><code _o="898" _o-sc="33,3" _o-l="33" _o-e="33,17" _o-tl="-1" _o-s="33,2" _o-cl="2" id="5340e775">LocalDateTime</code></li>
<li _o="914" _o-sc="34,2" _o-l="34" _o-e="35,0" _o-tl="-1" _o-s="34,0" _o-cl="0" id="c921616b"><code _o="916" _o-sc="34,3" _o-l="34" _o-e="34,13" _o-tl="-1" _o-s="34,2" _o-cl="2" id="9701eda1">LocalDate</code></li>
<li _o="928" _o-sc="35,2" _o-l="35" _o-e="36,0" _o-tl="-1" _o-s="35,0" _o-cl="0" id="12fb4654"><code _o="930" _o-sc="35,3" _o-l="35" _o-e="35,13" _o-tl="-1" _o-s="35,2" _o-cl="2" id="3c3d8a82">LocalTime</code></li>
</list>

<code _o="966" _o-sc="40,0" _o-l="39" _o-e="44,3" _o-tl="38" _o-s="39,0" style="block" _o-cl="0" id="e0559b2b" lang="kotlin">df.convert { age }.to&lt;Double>()
df.convert { numberCols() }.to&lt;String>()
df.convert { name.firstName and name.lastName }.to { it.length() }
df.convert { weight }.toFloat()
</code>

</topic>