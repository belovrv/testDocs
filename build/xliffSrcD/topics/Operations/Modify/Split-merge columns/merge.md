<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="merge" title="merge" _md-based="true"> 
<p _o="91" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="e15761d5">Merges several columns into a single column.</p>
<p _o="138" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="e898c98b">Reverse operation to <a _o="159" _o-sc="6,22" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,40" _o-tl="-1" _o-s="6,21" href="split.md" _o-cl="21" id="3656e809"><code _o="160" _o-sc="6,23" _o-l="6" _o-e="6,29" _o-tl="-1" _o-s="6,22" _o-cl="22" id="fa96a920">split</code></a></p>
<code _o="180" _o-sc="9,0" _o-l="8" _o-e="15,3" _o-tl="142" _o-s="8,0" style="block" _o-cl="0" id="6acbc392" lang="kotlin">merge { columns }
    [.notNull()]
    .by(delimeter) | .by { merger } 
    [.into(column) | .intoList() ]

merger: (DataRow).List&lt;T> -> Any
</code>

<code _o="355" _o-sc="20,0" _o-l="19" _o-e="22,3" _o-tl="-1" _o-s="19,0" style="block" _o-cl="0" id="4210ffbc" lang="kotlin">// Merge two columns into one column "fullName"
df.merge { name.firstName and name.lastName }.by(" ").into("fullName")
</code>

<p _o="502" _o-sc="26,0" _o-l="26" _o-e="27,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="f8f281da"><code _o="502" _o-sc="26,1" _o-l="26" _o-e="26,8" _o-tl="-1" _o-s="26,0" _o-cl="0" id="a2bff795">merger</code> accepts a <code _o="521" _o-sc="26,20" _o-l="26" _o-e="26,25" _o-tl="-1" _o-s="26,19" _o-cl="19" id="eea0112e">List</code> of collected values for every row typed by their common type:</p>

<code _o="618" _o-sc="31,0" _o-l="30" _o-e="34,3" _o-tl="-1" _o-s="30,0" style="block" _o-cl="0" id="42d0a625" lang="kotlin">df.merge { name.firstName and name.lastName }
    .by { it[0] + " (" + it[1].uppercase() + ")" }
    .into("fullName")
</code>

<p _o="765" _o-sc="38,0" _o-l="38" _o-e="39,0" _o-tl="-1" _o-s="38,0" _o-cl="0" id="b6b2cf7c">When heterogeneous columns are merged, they may need to be cast to valid types in <code _o="847" _o-sc="38,83" _o-l="38" _o-e="38,90" _o-tl="-1" _o-s="38,82" _o-cl="82" id="49ce6d41">merger</code>:</p>

<code _o="890" _o-sc="43,0" _o-l="42" _o-e="46,3" _o-tl="-1" _o-s="42,0" style="block" _o-cl="0" id="f71e7a03" lang="kotlin">df.merge { name.firstName and age and isHappy }
    .by { "${it[0]} aged ${it[1]} is " + (if (it[2] as Boolean) "" else "not ") + "happy" }
    .into("status")
</code>

<p _o="1078" _o-sc="50,0" _o-l="50" _o-e="51,0" _o-tl="-1" _o-s="50,0" _o-cl="0" id="352e9fee">By default, when no <code _o="1098" _o-sc="50,21" _o-l="50" _o-e="50,31" _o-tl="-1" _o-s="50,20" _o-cl="20" id="3efc022c">delimeter</code> or <code _o="1113" _o-sc="50,36" _o-l="50" _o-e="50,43" _o-tl="-1" _o-s="50,35" _o-cl="35" id="3dc9bafe">merger</code> is specified, values will be merged into the <code _o="1167" _o-sc="50,90" _o-l="50" _o-e="50,95" _o-tl="-1" _o-s="50,89" _o-cl="89" id="a8c859ce">List</code>:</p>

<code _o="1202" _o-sc="55,0" _o-l="54" _o-e="56,3" _o-tl="-1" _o-s="54,0" style="block" _o-cl="0" id="5be5b6c3" lang="kotlin">df.merge { numberCols() }.into("data")
</code>

<p _o="1269" _o-sc="60,0" _o-l="60" _o-e="61,0" _o-tl="-1" _o-s="60,0" _o-cl="0" id="13d0bfd7">Merged column values can also be exported to <code _o="1314" _o-sc="60,46" _o-l="60" _o-e="60,51" _o-tl="-1" _o-s="60,45" _o-cl="45" id="b1ec47ea">List</code>:</p>

<code _o="1350" _o-sc="65,0" _o-l="64" _o-e="67,3" _o-tl="57" _o-s="64,0" style="block" _o-cl="0" id="63a2ae9d" lang="kotlin">// Merge data from two columns into List&lt;String>
df.merge { name.firstName and name.lastName }.by(",").intoList()
</code>

</topic>