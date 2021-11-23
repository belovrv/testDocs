<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="aggregateGroupBy" title="Aggregate groupBy" _md-based="true"> 
<p _o="104" _o-sc="4,0" _o-l="4" _o-e="6,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="885d65f5">To compute one or several <a _o="130" _o-sc="4,27" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,53" _o-tl="-1" _o-s="4,26" href="statistics.md" _o-cl="26" id="7c2c9920">statistics</a> per every group of <code _o="177" _o-sc="4,74" _o-l="4" _o-e="4,82" _o-tl="-1" _o-s="4,73" _o-cl="73" id="fde78b4a">GroupBy</code> use <code _o="191" _o-sc="4,88" _o-l="4" _o-e="4,98" _o-tl="-1" _o-s="4,87" _o-cl="87" id="af669879">aggregate</code> function. Its body will be executed for every data group and has a receiver of type <code _o="287" _o-sc="4,184" _o-l="4" _o-e="4,194" _o-tl="-1" _o-s="4,183" _o-cl="183" id="57add1cc">DataFrame</code> that represents current data group being aggregated.
To add new column to the resulting <code _o="387" _o-sc="5,36" _o-l="5" _o-e="5,46" _o-tl="-1" _o-s="5,35" _o-cl="35" id="d14d5278">DataFrame</code>, pass the name of new column to infix function <code _o="446" _o-sc="5,95" _o-l="5" _o-e="5,100" _o-tl="-1" _o-s="5,94" _o-cl="94" id="125d528">into</code>:</p>

<tabs id="c6815400">
<tab id="c8f481db" title="Properties">
<code _o="520" _o-sc="12,0" _o-l="11" _o-e="19,3" _o-tl="82" _o-s="11,0" style="block" _o-cl="0" id="44c0af27" lang="kotlin">df.groupBy { city }.aggregate {
    nrow() into "total"
    count { age > 18 } into "adults"
    median { age } into "median age"
    min { age } into "min age"
    maxBy { age }.name into "oldest"
}
</code>
</tab>
<tab _o="735" _o-sc="21,6" _o-l="21" _o-e="23,0" _o-tl="5" _o-s="21,0" _o-cl="0" id="b0ffe771" title="Accessors">
<code _o="767" _o-sc="25,0" _o-l="24" _o-e="44,3" _o-tl="36" _o-s="24,0" style="block" _o-cl="0" id="58eb051" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val name by columnGroup()

df.groupBy { city }.aggregate {
    nrow() into "total"
    count { age() > 18 } into "adults"
    median { age } into "median age"
    min { age } into "min age"
    maxBy { age() }[name] into "name of oldest"
}
// or
df.groupBy(city).aggregate {
    nrow() into "total"
    count { age > 18 } into "adults"
    median(age) into "median age"
    min(age) into "min age"
    maxBy(age)[name] into "name of oldest"
}
</code>
</tab>
<tab _o="1280" _o-sc="46,6" _o-l="46" _o-e="48,0" _o-tl="5" _o-s="46,0" _o-cl="0" id="bb89c75f" title="Strings">
<code _o="1310" _o-sc="50,0" _o-l="49" _o-e="57,3" _o-tl="86" _o-s="49,0" style="block" _o-cl="0" id="2e29e15" lang="kotlin">df.groupBy("city").aggregate {
    nrow() into "total"
    count { "age"&lt;Int>() > 18 } into "adults"
    median("age") into "median age"
    min("age") into "min age"
    maxBy("age")["name"] into "oldest"
}
</code>
</tab></tabs>

<p _o="1560" _o-sc="62,0" _o-l="62" _o-e="63,0" _o-tl="-1" _o-s="62,0" _o-cl="0" id="87db480f">If only one aggregation function is used, column name can be omitted:</p>

<tabs id="2a4107d8">
<tab id="2f9d469e" title="Properties">
<code _o="1704" _o-sc="69,0" _o-l="68" _o-e="70,3" _o-tl="-1" _o-s="68,0" style="block" _o-cl="0" id="8acfd224" lang="kotlin">df.groupBy { city }.aggregate { maxBy { age }.name }
</code>
</tab>
<tab _o="1772" _o-sc="72,6" _o-l="72" _o-e="74,0" _o-tl="5" _o-s="72,0" _o-cl="0" id="5ff97ce9" title="Accessors">
<code _o="1804" _o-sc="76,0" _o-l="75" _o-e="83,3" _o-tl="36" _o-s="75,0" style="block" _o-cl="0" id="749a4d89" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val name by columnGroup()

df.groupBy { city }.aggregate { maxBy { age() }[name] }
// or
df.groupBy(city).aggregate { maxBy(age)[name] }
</code>
</tab>
<tab _o="2011" _o-sc="85,6" _o-l="85" _o-e="87,0" _o-tl="5" _o-s="85,0" _o-cl="0" id="a7931ca7" title="Strings">
<code _o="2041" _o-sc="89,0" _o-l="88" _o-e="90,3" _o-tl="-1" _o-s="88,0" style="block" _o-cl="0" id="7349f68f" lang="kotlin">df.groupBy("city").aggregate { maxBy("age")["name"] }
</code>
</tab></tabs>

<p _o="2137" _o-sc="95,0" _o-l="95" _o-e="96,0" _o-tl="-1" _o-s="95,0" _o-cl="0" id="5af05a0">Most common aggregation functions can be computed directly at <code _o="2199" _o-sc="95,63" _o-l="95" _o-e="95,71" _o-tl="-1" _o-s="95,62" _o-cl="62" id="55fd819a">GroupBy</code>:</p>

<tabs id="d97abe87">
<tab id="7b5967a" title="Properties">
<code _o="2282" _o-sc="102,0" _o-l="101" _o-e="114,3" _o-tl="-1" _o-s="101,0" style="block" _o-cl="0" id="19a0985d" lang="kotlin">df.groupBy { city }.max() // max for every comparable column
df.groupBy { city }.mean() // mean for every numeric column
df.groupBy { city }.max { age } // max age into column "age"
df.groupBy { city }.sum("total weight") { weight } // sum of weights into column "total weight"
df.groupBy { city }.count() // number of rows into column "count"
df.groupBy { city }
    .max { name.firstName.length() and name.lastName.length() } // maximum length of firstName or lastName into column "max"
df.groupBy { city }
    .medianFor { age and weight } // median age into column "age", median weight into column "weight"
df.groupBy { city }
    .minFor { (age into "min age") and (weight into "min weight") } // min age into column "min age", min weight into column "min weight"
df.groupBy { city }.meanOf("mean ratio") { weight?.div(age) } // mean of weight/age into column "mean ratio"
</code>
</tab>
<tab _o="3175" _o-sc="116,6" _o-l="116" _o-e="118,0" _o-tl="5" _o-s="116,0" _o-cl="0" id="b08a5490" title="Accessors">
<code _o="3207" _o-sc="120,0" _o-l="119" _o-e="139,3" _o-tl="36" _o-s="119,0" style="block" _o-cl="0" id="744bb3f9" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val weight by column&lt;Int?>()
val name by columnGroup()
val firstName by name.column&lt;String>()
val lastName by name.column&lt;String>()

df.groupBy { city }.max() // max for every comparable column
df.groupBy { city }.mean() // mean for every numeric column
df.groupBy { city }.max { age } // max age into column "age"
df.groupBy { city }.sum("total weight") { weight } // sum of weights into column "total weight"
df.groupBy { city }.count() // number of rows into column "count"
df.groupBy { city }
    .max { firstName.length() and lastName.length() } // maximum length of firstName or lastName into column "max"
df.groupBy { city }
    .medianFor { age and weight } // median age into column "age", median weight into column "weight"
df.groupBy { city }
    .minFor { (age into "min age") and (weight into "min weight") } // min age into column "min age", min weight into column "min weight"
df.groupBy { city }.meanOf("mean ratio") { weight()?.div(age()) } // mean of weight/age into column "mean ratio"
</code>
</tab>
<tab _o="4282" _o-sc="141,6" _o-l="141" _o-e="143,0" _o-tl="5" _o-s="141,0" _o-cl="0" id="b3276e0d" title="Strings">
<code _o="4312" _o-sc="145,0" _o-l="144" _o-e="160,3" _o-tl="-1" _o-s="144,0" style="block" _o-cl="0" id="1d12dc0f" lang="kotlin">df.groupBy("city").max() // max for every comparable column
df.groupBy("city").mean() // mean for every numeric column
df.groupBy("city").max("age") // max age into column "age"
df.groupBy("city").sum("weight", name = "total weight") // sum of weights into column "total weight"
df.groupBy("city").count() // number of rows into column "count"
df.groupBy("city").max {
    "name"["firstName"].strings().length() and "name"["lastName"].strings().length()
} // maximum length of firstName or lastName into column "max"
df.groupBy("city")
    .medianFor("age", "weight") // median age into column "age", median weight into column "weight"
df.groupBy("city")
    .minFor { ("age".ints() into "min age") and ("weight".intOrNulls() into "min weight") } // min age into column "min age", min weight into column "min weight"
df.groupBy("city").meanOf("mean ratio") {
    "weight".intOrNull()?.div("age".int())
} // mean of weight/age into column "mean ratio"
</code>
</tab></tabs>

<p _o="5305" _o-sc="165,0" _o-l="165" _o-e="166,0" _o-tl="-1" _o-s="165,0" _o-cl="0" id="defd0b9c">To get all column values for every group without aggregation use <code _o="5370" _o-sc="165,66" _o-l="165" _o-e="165,73" _o-tl="-1" _o-s="165,65" _o-cl="65" id="2c4856f8">values</code> function:</p>
<list _o="5389" _o-sc="166,0" _o-l="166" _o-e="168,0" _o-tl="113" _o-s="166,0" _o-cl="0" id="7ecff28a">
<li _o="5389" _o-sc="166,2" _o-l="166" _o-e="167,0" _o-tl="113" _o-s="166,0" _o-cl="0" id="3d4db56f">for <a _o="5395" _o-sc="166,7" LinkStatus="UNKNOWN" _o-l="166" _o-e="166,46" _o-tl="-1" _o-s="166,6" href="DataColumn.md#valuecolumn" _o-cl="6" id="89d055f2">ValueColumn</a> of type <code _o="5444" _o-sc="166,56" _o-l="166" _o-e="166,58" _o-tl="-1" _o-s="166,55" _o-cl="55" id="c846b01b">T</code> it will gather group values into lists of type <code _o="5495" _o-sc="166,107" _o-l="166" _o-e="166,115" _o-tl="7" _o-s="166,106" _o-cl="106" id="467f9d71">Many&lt;T></code></li>
<li _o="5505" _o-sc="167,2" _o-l="167" _o-e="168,0" _o-tl="-1" _o-s="167,0" _o-cl="0" id="54ccf0f8">for <a _o="5511" _o-sc="167,7" LinkStatus="UNKNOWN" _o-l="167" _o-e="167,46" _o-tl="-1" _o-s="167,6" href="DataColumn.md#columngroup" _o-cl="6" id="a8b2ef0d">ColumnGroup</a> it will gather group values into <code _o="5585" _o-sc="167,81" _o-l="167" _o-e="167,91" _o-tl="-1" _o-s="167,80" _o-cl="80" id="bffa4ac7">DataFrame</code> and convert <a _o="5609" _o-sc="167,105" LinkStatus="UNKNOWN" _o-l="167" _o-e="167,144" _o-tl="-1" _o-s="167,104" href="DataColumn.md#columngroup" _o-cl="104" id="e43a89c3">ColumnGroup</a> into <a _o="5655" _o-sc="167,151" LinkStatus="UNKNOWN" _o-l="167" _o-e="167,190" _o-tl="-1" _o-s="167,150" href="DataColumn.md#framecolumn" _o-cl="150" id="f9cbd917">FrameColumn</a></li>
</list>

<tabs id="b99068ce">
<tab id="fb0c9259" title="Properties">
<code _o="5768" _o-sc="174,0" _o-l="173" _o-e="177,3" _o-tl="-1" _o-s="173,0" style="block" _o-cl="0" id="79534151" lang="kotlin">df.groupBy { city }.values()
df.groupBy { city }.values { name and age }
df.groupBy { city }.values { weight into "weights" }
</code>
</tab>
<tab _o="5909" _o-sc="179,6" _o-l="179" _o-e="181,0" _o-tl="5" _o-s="179,0" _o-cl="0" id="7921dd52" title="Accessors">
<code _o="5941" _o-sc="183,0" _o-l="182" _o-e="191,3" _o-tl="36" _o-s="182,0" style="block" _o-cl="0" id="cde0910a" lang="kotlin">val city by column&lt;String?>()
val age by column&lt;Int>()
val weight by column&lt;Int?>()
val name by columnGroup()

df.groupBy(city).values()
df.groupBy(city).values(name, age)
df.groupBy(city).values { weight into "weights" }
</code>
</tab>
<tab _o="6178" _o-sc="193,6" _o-l="193" _o-e="195,0" _o-tl="5" _o-s="193,0" _o-cl="0" id="a3e41409" title="Strings">
<code _o="6208" _o-sc="197,0" _o-l="196" _o-e="200,3" _o-tl="-1" _o-s="196,0" style="block" _o-cl="0" id="8c29f644" lang="kotlin">df.groupBy("city").values()
df.groupBy("city").values("name", "age")
df.groupBy("city").values { "weight" into "weights" }
</code>
</tab></tabs>

</topic>