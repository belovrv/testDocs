<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="gather" title="gather" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="d0bc54c1">Converts several columns into two columns <code _o="134" _o-sc="4,43" _o-l="4" _o-e="4,47" _o-tl="-1" _o-s="4,42" _o-cl="42" id="2ed0ee74">key</code> and <code _o="144" _o-sc="4,53" _o-l="4" _o-e="4,59" _o-tl="-1" _o-s="4,52" _o-cl="52" id="5cc5089b">value</code>. <code _o="153" _o-sc="4,62" _o-l="4" _o-e="4,66" _o-tl="-1" _o-s="4,61" _o-cl="61" id="6a1b0721">key</code> column will contain names of original columns, <code _o="206" _o-sc="4,115" _o-l="4" _o-e="4,121" _o-tl="-1" _o-s="4,114" _o-cl="114" id="f25ab124">value</code> column will contain values from original columns.</p>
<p _o="265" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="17e2f47a">This operation is reverse to <a _o="294" _o-sc="6,30" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,46" _o-tl="-1" _o-s="6,29" href="pivot.md" _o-cl="29" id="fdc98a0f">pivot</a></p>
<code _o="313" _o-sc="9,0" _o-l="8" _o-e="21,3" _o-tl="66" _o-s="8,0" style="block" _o-cl="0" id="62e09a58" lang="kotlin">gather { columns }
    [.explodeLists()]
    [.cast&lt;Type>()]
    [.notNull()]
    [.where { valueFilter }]
    [.mapKeys { keyTransform }]
    [.mapValues { valueTransform }]
    .into(keyColumn, valueColumn) | .keysInto(keyColumn) | .valuesInto(valueColumn)

valueFilter: (value) -> Boolean
keyTransform: (columnName: String) -> K
valueTransform: (value) -> R 
</code>
<p _o="690" _o-sc="23,0" _o-l="23" _o-e="24,0" _o-tl="-1" _o-s="23,0" _o-cl="0" id="eed9c473">See <a _o="694" _o-sc="23,5" LinkStatus="UNKNOWN" _o-l="23" _o-e="23,42" _o-tl="-1" _o-s="23,4" href="ColumnSelectors.md" _o-cl="4" id="7c0d62c3">column selectors</a></p>
<p _o="734" _o-sc="25,0" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="734439cf">Configuration options:</p>
<list _o="757" _o-sc="26,0" _o-l="26" _o-e="32,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="58052e92">
<li _o="757" _o-sc="26,2" _o-l="26" _o-e="27,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="552e3309"><code _o="759" _o-sc="26,3" _o-l="26" _o-e="26,16" _o-tl="-1" _o-s="26,2" _o-cl="2" id="1c4a3723">explodeLists</code> - gathered values of type <code _o="800" _o-sc="26,44" _o-l="26" _o-e="26,49" _o-tl="-1" _o-s="26,43" _o-cl="43" id="bd6360b9">List</code> will be exploded into their elements, so <code _o="848" _o-sc="26,92" _o-l="26" _o-e="26,98" _o-tl="-1" _o-s="26,91" _o-cl="91" id="73071824">where</code>, <code _o="857" _o-sc="26,101" _o-l="26" _o-e="26,106" _o-tl="-1" _o-s="26,100" _o-cl="100" id="d6e88b8d">cast</code>, <code _o="865" _o-sc="26,109" _o-l="26" _o-e="26,117" _o-tl="-1" _o-s="26,108" _o-cl="108" id="5428e064">notNull</code> and <code _o="879" _o-sc="26,123" _o-l="26" _o-e="26,133" _o-tl="-1" _o-s="26,122" _o-cl="122" id="676fb93d">mapValues</code> will be applied to list elements instead of lists themselves</li>
<li _o="952" _o-sc="27,2" _o-l="27" _o-e="28,0" _o-tl="-1" _o-s="27,0" _o-cl="0" id="e6f81928"><code _o="954" _o-sc="27,3" _o-l="27" _o-e="27,8" _o-tl="-1" _o-s="27,2" _o-cl="2" id="c0017efe">cast</code> - inform compiler about the expected type of gathered elements. This type will be passed to <code _o="1053" _o-sc="27,102" _o-l="27" _o-e="27,108" _o-tl="-1" _o-s="27,101" _o-cl="101" id="d599e565">where</code> and <code _o="1065" _o-sc="27,114" _o-l="27" _o-e="27,122" _o-tl="-1" _o-s="27,113" _o-cl="113" id="69937a63">mapKeys</code> lambdas</li>
<li _o="1083" _o-sc="28,2" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="29e2e2fa"><code _o="1085" _o-sc="28,3" _o-l="28" _o-e="28,11" _o-tl="-1" _o-s="28,2" _o-cl="2" id="6b950976">notNull</code> - skip gathered <code _o="1111" _o-sc="28,29" _o-l="28" _o-e="28,34" _o-tl="-1" _o-s="28,28" _o-cl="28" id="bc8dc662">null</code> values</li>
<li _o="1125" _o-sc="29,2" _o-l="29" _o-e="30,0" _o-tl="-1" _o-s="29,0" _o-cl="0" id="da538496"><code _o="1127" _o-sc="29,3" _o-l="29" _o-e="29,9" _o-tl="-1" _o-s="29,2" _o-cl="2" id="c4820259">where</code> - filter gathered values</li>
<li _o="1160" _o-sc="30,2" _o-l="30" _o-e="31,0" _o-tl="-1" _o-s="30,0" _o-cl="0" id="ea34e119"><code _o="1162" _o-sc="30,3" _o-l="30" _o-e="30,11" _o-tl="-1" _o-s="30,2" _o-cl="2" id="90073c52">mapKeys</code> - transform gathered column names (keys)</li>
<li _o="1213" _o-sc="31,2" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="385a81c6"><code _o="1215" _o-sc="31,3" _o-l="31" _o-e="31,13" _o-tl="-1" _o-s="31,2" _o-cl="2" id="fdf86faf">mapValues</code> - transform gathered column values</li>
</list>
<p _o="1264" _o-sc="33,0" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="4fcdd2e1">Storage options:</p>
<list _o="1281" _o-sc="34,0" _o-l="34" _o-e="37,0" _o-tl="-1" _o-s="34,0" _o-cl="0" id="6f4ceae8">
<li _o="1281" _o-sc="34,2" _o-l="34" _o-e="35,0" _o-tl="-1" _o-s="34,0" _o-cl="0" id="7529a29e"><code _o="1283" _o-sc="34,3" _o-l="34" _o-e="34,32" _o-tl="-1" _o-s="34,2" _o-cl="2" id="6489c516">into(keyColumn, valueColumn)</code> - store gathered key-value pairs in two new columns with names <code _o="1377" _o-sc="34,97" _o-l="34" _o-e="34,107" _o-tl="-1" _o-s="34,96" _o-cl="96" id="bd714f8f">keyColumn</code> and <code _o="1393" _o-sc="34,113" _o-l="34" _o-e="34,125" _o-tl="-1" _o-s="34,112" _o-cl="112" id="70231861">valueColumn</code></li>
<li _o="1407" _o-sc="35,2" _o-l="35" _o-e="36,0" _o-tl="-1" _o-s="35,0" _o-cl="0" id="47fbc20d"><code _o="1409" _o-sc="35,3" _o-l="35" _o-e="35,23" _o-tl="-1" _o-s="35,2" _o-cl="2" id="70683ef0">keysInto(keyColumn)</code> - store only gathered keys (column names) in a new column <code _o="1489" _o-sc="35,83" _o-l="35" _o-e="35,93" _o-tl="-1" _o-s="35,82" _o-cl="82" id="a91679b">keyColumn</code></li>
<li _o="1501" _o-sc="36,2" _o-l="36" _o-e="37,0" _o-tl="-1" _o-s="36,0" _o-cl="0" id="c9692968"><code _o="1503" _o-sc="36,3" _o-l="36" _o-e="36,27" _o-tl="-1" _o-s="36,2" _o-cl="2" id="619443c9">valuesInto(valueColumn)</code> - store only gathered values in a new column <code _o="1574" _o-sc="36,74" _o-l="36" _o-e="36,86" _o-tl="-1" _o-s="36,73" _o-cl="73" id="b49d4731">valueColumn</code></li>
</list>

<code _o="1609" _o-sc="41,0" _o-l="40" _o-e="42,3" _o-tl="-1" _o-s="40,0" style="block" _o-cl="0" id="ba9260f" lang="kotlin">pivoted.gather { "London".."Tokyo" }.into("city", "population")
</code>


<code _o="1732" _o-sc="49,0" _o-l="48" _o-e="55,3" _o-tl="60" _o-s="48,0" style="block" _o-cl="0" id="8d905702" lang="kotlin">pivoted.gather { "London".."Tokyo" }
    .cast&lt;Int>()
    .where { it > 10 }
    .mapKeys { it.lowercase() }
    .mapValues { 1.0 / it }
    .into("city", "density")
</code>

</topic>