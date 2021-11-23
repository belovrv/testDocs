<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="aggregatePivot" title="Aggregate pivot" _md-based="true"> 
<p _o="102" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="ef02d7d6">To aggregate data groups in <a _o="130" _o-sc="4,29" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,47" _o-tl="-1" _o-s="4,28" href="pivot.md" _o-cl="28" id="642a2aea"><code _o="131" _o-sc="4,30" _o-l="4" _o-e="4,36" _o-tl="-1" _o-s="4,29" _o-cl="29" id="f7f4753f">Pivot</code></a> or <a _o="153" _o-sc="4,52" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,91" _o-tl="-1" _o-s="4,51" href="pivot.md#pivot-groupby" _o-cl="51" id="411f14ef"><code _o="154" _o-sc="4,53" _o-l="4" _o-e="4,66" _o-tl="-1" _o-s="4,52" _o-cl="52" id="2a6d190c">PivotGroupBy</code></a> with one or several statistics use <code _o="229" _o-sc="4,128" _o-l="4" _o-e="4,138" _o-tl="-1" _o-s="4,127" _o-cl="127" id="1e0020bf">aggregate</code>:</p>

<tabs id="4960aca1">
<tab id="e68f3706" title="Properties">
<code _o="303" _o-sc="11,0" _o-l="10" _o-e="17,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="c2508621" lang="kotlin">df.pivot { city }.aggregate { minBy { age }.name }
df.pivot { city }.groupBy { name.firstName }.aggregate {
    meanFor { age and weight } into "means"
    stdFor { age and weight } into "stds"
    maxByOrNull { weight }?.name?.lastName into "biggest"
}
</code>
</tab>
<tab _o="572" _o-sc="19,6" _o-l="19" _o-e="21,0" _o-tl="5" _o-s="19,0" _o-cl="0" id="b3850acc" title="Accessors">
<code _o="604" _o-sc="23,0" _o-l="22" _o-e="36,3" _o-tl="36" _o-s="22,0" style="block" _o-cl="0" id="1260eeae" lang="kotlin">val city by column&lt;String?>()
val name by columnGroup()
val firstName by name.column&lt;String>()
val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.pivot { city }.aggregate { minBy(age).name }

df.pivot { city }.groupBy { firstName }.aggregate {
    meanFor { age and weight } into "means"
    stdFor { age and weight } into "stds"
    maxByOrNull(weight)?.name?.lastName into "biggest"
}
</code>
</tab>
<tab _o="1013" _o-sc="38,6" _o-l="38" _o-e="40,0" _o-tl="5" _o-s="38,0" _o-cl="0" id="850b7f87" title="Strings">
<code _o="1043" _o-sc="42,0" _o-l="41" _o-e="49,3" _o-tl="-1" _o-s="41,0" style="block" _o-cl="0" id="2b7942d9" lang="kotlin">df.pivot("city").aggregate { minBy("age")["name"] }

df.pivot("city").groupBy { "name"["firstName"] }.aggregate {
    meanFor("age", "weight") into "means"
    stdFor("age", "weight") into "stds"
    maxByOrNull("weight")?.getColumnGroup("name")?.get("lastName") into "biggest"
}
</code>
</tab></tabs>

<p _o="1365" _o-sc="54,0" _o-l="54" _o-e="55,0" _o-tl="-1" _o-s="54,0" _o-cl="0" id="f0a4105b">Shortcuts for common aggregation functions are also available:</p>

<tabs id="eac9ab1c">
<tab id="40c83c6f" title="Properties">
<code _o="1498" _o-sc="61,0" _o-l="60" _o-e="63,3" _o-tl="-1" _o-s="60,0" style="block" _o-cl="0" id="c9c4cc9" lang="kotlin">df.pivot { city }.maxFor { age and weight }
df.groupBy { name }.pivot { city }.median { age }
</code>
</tab>
<tab _o="1607" _o-sc="65,6" _o-l="65" _o-e="67,0" _o-tl="5" _o-s="65,0" _o-cl="0" id="ba7e4df5" title="Accessors">
<code _o="1639" _o-sc="69,0" _o-l="68" _o-e="76,3" _o-tl="36" _o-s="68,0" style="block" _o-cl="0" id="6c1de49d" lang="kotlin">val city by column&lt;String?>()
val name by columnGroup()
val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.pivot { city }.maxFor { age and weight }
df.groupBy { name }.pivot { city }.median { age }
</code>
</tab>
<tab _o="1859" _o-sc="78,6" _o-l="78" _o-e="80,0" _o-tl="5" _o-s="78,0" _o-cl="0" id="9f8ed9fd" title="Strings">
<code _o="1889" _o-sc="82,0" _o-l="81" _o-e="84,3" _o-tl="-1" _o-s="81,0" style="block" _o-cl="0" id="2751e612" lang="kotlin">df.pivot("city").maxFor("age", "weight")
df.groupBy("name").pivot("city").median("age")
</code>
</tab></tabs>

<p _o="2019" _o-sc="89,0" _o-l="89" _o-e="91,0" _o-tl="436" _o-s="89,0" _o-cl="0" id="94ca9695">By default, when aggregation function produces several values for data group, column hierarchy in resulting <code _o="2127" _o-sc="89,109" _o-l="89" _o-e="89,119" _o-tl="-1" _o-s="89,108" _o-cl="108" id="ff98503">DataFrame</code> will be indexed first by pivot keys and then by the names of aggregated values.
To reverse this order so that resulting columns will be indexed first by names of aggregated values and then by pivot keys, use <code _o="2347" _o-sc="90,129" _o-l="90" _o-e="90,143" _o-tl="-1" _o-s="90,128" _o-cl="128" id="f3a3359f">separate=true</code> flag that is available in multi-result aggregation operations, such as <code _o="2434" _o-sc="90,216" _o-l="90" _o-e="90,226" _o-tl="-1" _o-s="90,215" _o-cl="215" id="b785572f">aggregate</code> or <code _o="2449" _o-sc="90,231" _o-l="90" _o-e="90,241" _o-tl="6" _o-s="90,230" _o-cl="230" id="78542b85">&lt;stat>For</code>:</p>

<tabs id="3c0f25e1">
<tab id="a9655b97" title="Properties">
<code _o="2522" _o-sc="97,0" _o-l="96" _o-e="102,3" _o-tl="-1" _o-s="96,0" style="block" _o-cl="0" id="ff14e566" lang="kotlin">df.pivot { city }.maxFor(separate = true) { age and weight }
df.pivot { city }.aggregate(separate = true) {
    min { age } into "min age"
    maxOrNull { weight } into "max weight"
}
</code>
</tab>
<tab _o="2721" _o-sc="104,6" _o-l="104" _o-e="106,0" _o-tl="5" _o-s="104,0" _o-cl="0" id="edc2b144" title="Accessors">
<code _o="2753" _o-sc="108,0" _o-l="107" _o-e="117,3" _o-tl="36" _o-s="107,0" style="block" _o-cl="0" id="c7b6d35b" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.pivot { city }.maxFor(separate = true) { age and weight }
df.pivot { city }.aggregate(separate = true) {
    min { age } into "min age"
    maxOrNull { weight } into "max weight"
}
</code>
</tab>
<tab _o="3037" _o-sc="119,6" _o-l="119" _o-e="121,0" _o-tl="5" _o-s="119,0" _o-cl="0" id="87b3a4bd" title="Strings">
<code _o="3067" _o-sc="123,0" _o-l="122" _o-e="128,3" _o-tl="-1" _o-s="122,0" style="block" _o-cl="0" id="c89063ac" lang="kotlin">df.pivot("city").maxFor("age", "weight", separate = true)
df.pivot("city").aggregate(separate = true) {
    min("age") into "min age"
    maxOrNull("weight") into "max weight"
}
</code>
</tab></tabs>

<p _o="3287" _o-sc="133,0" _o-l="133" _o-e="136,0" _o-tl="-1" _o-s="133,0" _o-cl="0" id="7ef8a8ba">By default, any aggregation function will result in <code _o="3339" _o-sc="133,53" _o-l="133" _o-e="133,58" _o-tl="-1" _o-s="133,52" _o-cl="52" id="d8207a15">null</code> value for those matrix cells, where intersection of column and row keys produced an empty data group.
You can specify default value for any aggregation by <code _o="3501" _o-sc="134,54" _o-l="134" _o-e="134,62" _o-tl="-1" _o-s="134,53" _o-cl="53" id="94af888d">default</code> infix function. This value will replace all <code _o="3555" _o-sc="134,108" _o-l="134" _o-e="134,113" _o-tl="-1" _o-s="134,107" _o-cl="107" id="bfeb22de">null</code> results of aggregation function over non-empty data groups as well.
To use one default value for all aggregation functions, use <code _o="3690" _o-sc="135,61" _o-l="135" _o-e="135,71" _o-tl="-1" _o-s="135,60" _o-cl="60" id="efc8058a">default()</code> before aggregation.</p>

<tabs id="b252c5fa">
<tab id="5a00067" title="Properties">
<code _o="3781" _o-sc="142,0" _o-l="141" _o-e="148,3" _o-tl="-1" _o-s="141,0" style="block" _o-cl="0" id="50538e96" lang="kotlin">df.pivot { city }.groupBy { name }.aggregate { min { age } default 0 }
df.pivot { city }.groupBy { name }.aggregate {
    median { age } into "median age" default 0
    minOrNull { weight } into "min weight" default 100
}
df.pivot { city }.groupBy { name }.default(0).min()
</code>
</tab>
<tab _o="4070" _o-sc="150,6" _o-l="150" _o-e="152,0" _o-tl="5" _o-s="150,0" _o-cl="0" id="cfb85a30" title="Accessors">
<code _o="4102" _o-sc="154,0" _o-l="153" _o-e="165,3" _o-tl="36" _o-s="153,0" style="block" _o-cl="0" id="33b0d8d2" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val weight by column&lt;Int?>()
val name by columnGroup()

df.pivot { city }.groupBy { name }.aggregate { min { age } default 0 }
df.pivot { city }.groupBy { name }.aggregate {
    median { age } into "median age" default 0
    minOrNull { weight } into "min weight" default 100
}
df.pivot { city }.groupBy { name }.default(0).min()
</code>
</tab>
<tab _o="4502" _o-sc="167,6" _o-l="167" _o-e="169,0" _o-tl="5" _o-s="167,0" _o-cl="0" id="d1892980" title="Strings">
<code _o="4532" _o-sc="171,0" _o-l="170" _o-e="177,3" _o-tl="-1" _o-s="170,0" style="block" _o-cl="0" id="e5a55d7d" lang="kotlin">df.pivot("city").groupBy("name").aggregate { min("age") default 0 }
df.pivot("city").groupBy("name").aggregate {
    median("age") into "median age" default 0
    minOrNull("weight") into "min weight" default 100
}
df.pivot("city").groupBy("name").default(0).min()
</code>
</tab></tabs>

<chapter _o="4839" _o-sc="182,3" _o-l="182" _o-e="182,25" _o-tl="-1" _o-s="182,0" _o-cl="0" id="pivot-inside-aggregate" title="Pivot inside aggregate">
<p _o="4866" _o-sc="184,0" _o-l="184" _o-e="185,0" _o-tl="-1" _o-s="184,0" _o-cl="0" id="11149670"><a _o="4866" _o-sc="184,1" LinkStatus="UNKNOWN" _o-l="184" _o-e="184,17" _o-tl="-1" _o-s="184,0" href="pivot.md" _o-cl="0" id="19afc9bb">pivot</a> operation can also be used inside <code _o="4918" _o-sc="184,53" _o-l="184" _o-e="184,63" _o-tl="-1" _o-s="184,52" _o-cl="52" id="ca4cffc">aggregate</code> body of <code _o="4938" _o-sc="184,73" _o-l="184" _o-e="184,81" _o-tl="-1" _o-s="184,72" _o-cl="72" id="7c117a12">GroupBy</code>. This allows to combine column pivoting with other aggregation functions:</p>

<tabs id="a6b17cf">
<tab id="7cc0fec3" title="Properties">
<code _o="5085" _o-sc="191,0" _o-l="190" _o-e="198,3" _o-tl="-1" _o-s="190,0" style="block" _o-cl="0" id="bbbdbbe0" lang="kotlin">df.groupBy { name.firstName }.aggregate {
    pivot { city }.aggregate(separate = true) {
        mean { age } into "mean age"
        count() into "count"
    }
    count() into "total"
}
</code>
</tab>
<tab _o="5289" _o-sc="200,6" _o-l="200" _o-e="202,0" _o-tl="5" _o-s="200,0" _o-cl="0" id="7daa0e77" title="Accessors">
<code _o="5321" _o-sc="204,0" _o-l="203" _o-e="216,3" _o-tl="36" _o-s="203,0" style="block" _o-cl="0" id="b2af9b29" lang="kotlin">val city by column&lt;String?>()
val name by columnGroup()
val firstName by name.column&lt;String>()
val age by column&lt;Int>()

df.groupBy { firstName }.aggregate {
    pivot { city }.aggregate(separate = true) {
        mean { age } into "mean age"
        count() into "count"
    }
    count() into "total"
}
</code>
</tab>
<tab _o="5641" _o-sc="218,6" _o-l="218" _o-e="220,0" _o-tl="5" _o-s="218,0" _o-cl="0" id="715e8ed1" title="Strings">
<code _o="5671" _o-sc="222,0" _o-l="221" _o-e="229,3" _o-tl="-1" _o-s="221,0" style="block" _o-cl="0" id="89b087ef" lang="kotlin">df.groupBy { "name"["firstName"] }.aggregate {
    pivot("city").aggregate(separate = true) {
        mean("age") into "mean age"
        count() into "count"
    }
    count() into "total"
}
</code>
</tab></tabs>

</chapter></topic>