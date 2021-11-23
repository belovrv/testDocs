<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="getRow" title="Get rows" _md-based="true"> 
<p _o="94" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="336c3f10">Get single <a _o="105" _o-sc="4,12" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,34" _o-tl="-1" _o-s="4,11" href="DataRow.md" _o-cl="11" id="99c9d593"><code _o="106" _o-sc="4,13" _o-l="4" _o-e="4,21" _o-tl="-1" _o-s="4,12" _o-cl="12" id="93f2988e">DataRow</code></a> by <a _o="132" _o-sc="4,39" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,58" _o-tl="-1" _o-s="4,38" href="indexing.md" _o-cl="38" id="80f85564">index</a>:</p>

<code _o="182" _o-sc="9,0" _o-l="8" _o-e="10,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="19a23e94" lang="kotlin">df[2]
</code>

<p _o="216" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="eea08655">Get single <a _o="227" _o-sc="14,12" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,34" _o-tl="-1" _o-s="14,11" href="DataRow.md" _o-cl="11" id="6d3c00de"><code _o="228" _o-sc="14,13" _o-l="14" _o-e="14,21" _o-tl="-1" _o-s="14,12" _o-cl="12" id="340f57de">DataRow</code></a> by <a _o="254" _o-sc="14,39" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,80" _o-tl="-1" _o-s="14,38" href="DataRow.md#row-conditions" _o-cl="38" id="ea0ed790">row condition</a>:</p>

<tabs id="8b2c750a">
<tab id="69656983" title="Properties">
<code _o="362" _o-sc="21,0" _o-l="20" _o-e="26,3" _o-tl="-1" _o-s="20,0" style="block" _o-cl="0" id="82b05c0b" lang="kotlin">df.single { age == 45 }
df.first { weight != null }
df.minBy { age }
df.maxBy { name.firstName.length }
df.maxByOrNull { weight }
</code>
</tab>
<tab _o="507" _o-sc="28,6" _o-l="28" _o-e="30,0" _o-tl="5" _o-s="28,0" _o-cl="0" id="b16d6bc2" title="Accessors">
<code _o="539" _o-sc="32,0" _o-l="31" _o-e="42,3" _o-tl="31" _o-s="31,0" style="block" _o-cl="0" id="e273e9d5" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()
val name by columnGroup()
val firstName by name.column&lt;String>()

df.single { age() == 45 }
df.first { weight() != null }
df.minBy(age)
df.maxBy { firstName().length }
df.maxByOrNull { weight() }
</code>
</tab>
<tab _o="804" _o-sc="44,6" _o-l="44" _o-e="46,0" _o-tl="5" _o-s="44,0" _o-cl="0" id="36de3c7" title="Strings">
<code _o="834" _o-sc="48,0" _o-l="47" _o-e="53,3" _o-tl="31" _o-s="47,0" style="block" _o-cl="0" id="a96d50b3" lang="kotlin">df.single { "age"&lt;Int>() == 45 }
df.first { it["weight"] != null }
df.minBy("weight")
df.maxBy { "name"["firstName"]&lt;String>().length }
df.maxByOrNull("weight")
</code>
</tab></tabs>

</topic>