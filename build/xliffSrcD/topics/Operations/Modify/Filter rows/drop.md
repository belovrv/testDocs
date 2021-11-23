<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="drop" title="drop" _md-based="true"> 
<p _o="90" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="5388461e">Removes all rows that satisfy <a _o="120" _o-sc="4,31" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,72" _o-tl="-1" _o-s="4,30" href="DataRow.md#row-conditions" _o-cl="30" id="40053ad2">row condition</a></p>

<tabs id="66d13e53">
<tab id="252a8d3d" title="Properties">
<code _o="219" _o-sc="11,0" _o-l="10" _o-e="12,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="ce29f651" lang="kotlin">df.drop { weight == null || city == null }
</code>
</tab>
<tab _o="277" _o-sc="14,6" _o-l="14" _o-e="16,0" _o-tl="5" _o-s="14,0" _o-cl="0" id="1b7bf25f" title="Accessors">
<code _o="309" _o-sc="18,0" _o-l="17" _o-e="25,3" _o-tl="61" _o-s="17,0" style="block" _o-cl="0" id="2c24d054" lang="kotlin">val name by columnGroup()
val weight by column&lt;Int?>()
val city by column&lt;String?>()

df.drop { weight() == null || city() == null }
// or
df.drop { it[weight] == null || it[city] == null }
</code>
</tab>
<tab _o="514" _o-sc="27,6" _o-l="27" _o-e="29,0" _o-tl="5" _o-s="27,0" _o-cl="0" id="87301ea9" title="Strings">
<code _o="544" _o-sc="31,0" _o-l="30" _o-e="32,3" _o-tl="-1" _o-s="30,0" style="block" _o-cl="0" id="39c19f1b" lang="kotlin">df.drop { it["weight"] == null || it["city"] == null }
</code>
</tab></tabs>

<chapter _o="641" _o-sc="37,3" _o-l="37" _o-e="37,12" _o-tl="-1" _o-s="37,0" _o-cl="0" id="dropnulls" title="dropNulls">
<p _o="655" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="a243fc32">Remove rows with <code _o="672" _o-sc="39,18" _o-l="39" _o-e="39,23" _o-tl="-1" _o-s="39,17" _o-cl="17" id="1eaeeb70">null</code> values</p>

<code _o="710" _o-sc="44,0" _o-l="43" _o-e="49,3" _o-tl="-1" _o-s="43,0" style="block" _o-cl="0" id="daddce3a" lang="kotlin">df.dropNulls() // remove rows with null value in any column
df.dropNulls(whereAllNull = true) // remove rows with null values in all columns
df.dropNulls { city } // remove rows with null value in 'city' column
df.dropNulls { city and weight } // remove rows with null value in 'city' OR 'weight' columns
df.dropNulls(whereAllNull = true) { city and weight } // remove rows with null value in 'city' AND 'weight' columns
</code>

</chapter><chapter _o="1159" _o-sc="53,3" _o-l="53" _o-e="53,9" _o-tl="-1" _o-s="53,0" _o-cl="0" id="dropna" title="dropNA">
<p _o="1170" _o-sc="55,0" _o-l="55" _o-e="56,0" _o-tl="-1" _o-s="55,0" _o-cl="0" id="270b616f">Remove rows with <code _o="1187" _o-sc="55,18" _o-l="55" _o-e="55,23" _o-tl="-1" _o-s="55,17" _o-cl="17" id="142a9cb3">null</code>, <code _o="1195" _o-sc="55,26" _o-l="55" _o-e="55,37" _o-tl="-1" _o-s="55,25" _o-cl="25" id="cfcd970">Double.NaN</code> or <code _o="1211" _o-sc="55,42" _o-l="55" _o-e="55,52" _o-tl="-1" _o-s="55,41" _o-cl="41" id="4b1ea591">Float.NaN</code> values</p>

<code _o="1251" _o-sc="60,0" _o-l="59" _o-e="65,3" _o-tl="-1" _o-s="59,0" style="block" _o-cl="0" id="6d083a24" lang="kotlin">df.dropNA() // remove rows containing null or Double.NaN in any column
df.dropNA(whereAllNA = true) // remove rows with null or Double.NaN in all columns
df.dropNA { weight } // remove rows where 'weight' is null or Double.NaN
df.dropNA { age and weight } // remove rows where either 'age' or 'weight' is null or Double.NaN
df.dropNA(whereAllNA = true) { age and weight } // remove rows where both 'age' and 'weight' are null or Double.NaN
</code>

</chapter></topic>