<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="select" title="Select columns" _md-based="true"> 
<p _o="100" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="a5205da7">Two ways to create <code _o="119" _o-sc="4,20" _o-l="4" _o-e="4,30" _o-tl="-1" _o-s="4,19" _o-cl="19" id="6f497974">DataFrame</code> with a subset of columns:</p>
<p _o="158" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="82f5518b"><b _o="158" _o-sc="6,2" _o-l="6" _o-e="6,13" _o-tl="-1" _o-s="6,0" _o-cl="0" id="2e66a22e">indexing:</b></p>

<tabs id="513b25bc">
<tab id="6698aa26" title="Properties">
<code _o="235" _o-sc="13,0" _o-l="12" _o-e="14,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="f4f618a1" lang="kotlin">df[df.age, df.weight]
</code>
</tab>
<tab _o="272" _o-sc="16,6" _o-l="16" _o-e="18,0" _o-tl="5" _o-s="16,0" _o-cl="0" id="29ee4e80" title="Accessors">
<code _o="304" _o-sc="20,0" _o-l="19" _o-e="24,3" _o-tl="31" _o-s="19,0" style="block" _o-cl="0" id="29fd320a" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()

df[age, weight]
</code>
</tab>
<tab _o="390" _o-sc="26,6" _o-l="26" _o-e="28,0" _o-tl="5" _o-s="26,0" _o-cl="0" id="c4bd4fcb" title="Strings">
<code _o="420" _o-sc="30,0" _o-l="29" _o-e="31,3" _o-tl="-1" _o-s="29,0" style="block" _o-cl="0" id="3ab2c227" lang="kotlin">df["age", "weight"]
</code>
</tab></tabs>

<p _o="482" _o-sc="36,0" _o-l="36" _o-e="37,0" _o-tl="-1" _o-s="36,0" _o-cl="0" id="e515faab">See <a _o="486" _o-sc="36,5" LinkStatus="UNKNOWN" _o-l="36" _o-e="36,37" _o-tl="-1" _o-s="36,4" href="indexing.md" _o-cl="4" id="202e6c32">DataFrame indexing</a></p>
<p _o="521" _o-sc="38,0" _o-l="38" _o-e="39,0" _o-tl="-1" _o-s="38,0" _o-cl="0" id="296c153a"><b _o="521" _o-sc="38,2" _o-l="38" _o-e="38,14" _o-tl="-1" _o-s="38,0" _o-cl="0" id="e6af8553">selecting:</b></p>

<tabs id="11d7cf6c">
<tab id="dc52fe46" title="Properties">
<code _o="589" _o-sc="45,0" _o-l="44" _o-e="46,3" _o-tl="-1" _o-s="44,0" style="block" _o-cl="0" id="5a482ef1" lang="kotlin">df.select { age and weight }
</code>
</tab>
<tab _o="633" _o-sc="48,6" _o-l="48" _o-e="50,0" _o-tl="5" _o-s="48,0" _o-cl="0" id="ce3005d9" title="Accessors">
<code _o="665" _o-sc="52,0" _o-l="51" _o-e="57,3" _o-tl="31" _o-s="51,0" style="block" _o-cl="0" id="b409a70e" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.select { age and weight }
df.select(age, weight)
</code>
</tab>
<tab _o="787" _o-sc="59,6" _o-l="59" _o-e="61,0" _o-tl="5" _o-s="59,0" _o-cl="0" id="d0e94eb3" title="Strings">
<code _o="817" _o-sc="63,0" _o-l="62" _o-e="65,3" _o-tl="-1" _o-s="62,0" style="block" _o-cl="0" id="f7728d19" lang="kotlin">df.select { "age" and "weight" }
df.select("age", "weight")
</code>
</tab></tabs>

<p _o="919" _o-sc="70,0" _o-l="70" _o-e="71,0" _o-tl="-1" _o-s="70,0" _o-cl="0" id="758133a1">See <a _o="923" _o-sc="70,5" LinkStatus="UNKNOWN" _o-l="70" _o-e="70,42" _o-tl="-1" _o-s="70,4" href="ColumnSelectors.md" _o-cl="4" id="872378f3">column selectors</a></p>
</topic>