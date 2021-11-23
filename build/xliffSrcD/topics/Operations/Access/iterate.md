<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="iterate" title="Iterating" _md-based="true"> 
<p _o="95" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="f88ad5fd">Iterate over rows:</p>

<tabs id="950ca09a">
<tab id="75663193" title="Properties">
<code _o="168" _o-sc="11,0" _o-l="10" _o-e="22,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="104dff47" lang="kotlin">for (row in df) {
    println(row.age)
}

df.forEachRow {
    println(it.age)
}

df.rows().forEach {
    println(it.age)
}
</code>
</tab>
<tab _o="306" _o-sc="24,6" _o-l="24" _o-e="26,0" _o-tl="5" _o-s="24,0" _o-cl="0" id="6ea2a2d1" title="Accessors">
<code _o="338" _o-sc="28,0" _o-l="27" _o-e="41,3" _o-tl="31" _o-s="27,0" style="block" _o-cl="0" id="26e9c6cc" lang="kotlin">val age by column&lt;Int>()

for (row in df) {
    println(row[age])
}

df.forEachRow {
    println(it[age])
}

df.rows().forEach {
    println(it[age])
}
</code>
</tab>
<tab _o="505" _o-sc="43,6" _o-l="43" _o-e="45,0" _o-tl="5" _o-s="43,0" _o-cl="0" id="74616f58" title="Strings">
<code _o="535" _o-sc="47,0" _o-l="46" _o-e="58,3" _o-tl="-1" _o-s="46,0" style="block" _o-cl="0" id="92c7cb14" lang="kotlin">for (row in df) {
    println(row["age"])
}

df.forEachRow {
    println(it["age"])
}

df.rows().forEach {
    println(it["age"])
}
</code>
</tab></tabs>

<p _o="709" _o-sc="63,0" _o-l="63" _o-e="64,0" _o-tl="-1" _o-s="63,0" _o-cl="0" id="3b627a79">Iterate over columns:</p>

<code _o="755" _o-sc="68,0" _o-l="67" _o-e="75,3" _o-tl="-1" _o-s="67,0" style="block" _o-cl="0" id="e6e506a5" lang="kotlin">df.forEachColumn {
    println(it.name())
}

df.columns().forEach {
    println(it.name())
}
</code>

<p _o="876" _o-sc="79,0" _o-l="79" _o-e="80,0" _o-tl="-1" _o-s="79,0" _o-cl="0" id="738f2bff">Iterate over cells:</p>

<code _o="919" _o-sc="84,0" _o-l="83" _o-e="93,3" _o-tl="-1" _o-s="83,0" style="block" _o-cl="0" id="6a4ed631" lang="kotlin">// from top to bottom, then from left to right
df.values().forEach {
    println(it)
}

// from left to right, then from top to bottom
df.values(byRow = true).forEach {
    println(it)
}
</code>

</topic>