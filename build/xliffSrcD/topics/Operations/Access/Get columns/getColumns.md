<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="getColumns" title="Get columns" _md-based="true"> 
<p _o="97" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="2a157f1f">Get single column by column name:</p>

<tabs id="1fa35c1d">
<tab id="6ad0a0ea" title="Properties">
<code _o="193" _o-sc="11,0" _o-l="10" _o-e="13,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="d9cea999" lang="kotlin">df.age
df.name.lastName
</code>
</tab>
<tab _o="232" _o-sc="15,6" _o-l="15" _o-e="17,0" _o-tl="5" _o-s="15,0" _o-cl="0" id="3eaac42" title="Accessors">
<code _o="264" _o-sc="19,0" _o-l="18" _o-e="25,3" _o-tl="31" _o-s="18,0" style="block" _o-cl="0" id="2bb80af4" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()
val lastName by name.column&lt;String>()

df[age]
df[lastName]
</code>
</tab>
<tab _o="390" _o-sc="27,6" _o-l="27" _o-e="29,0" _o-tl="5" _o-s="27,0" _o-cl="0" id="56271009" title="Strings">
<code _o="420" _o-sc="31,0" _o-l="30" _o-e="33,3" _o-tl="-1" _o-s="30,0" style="block" _o-cl="0" id="f63fb8c2" lang="kotlin">df["age"]
df["name"]["firstName"]
</code>
</tab></tabs>

<p _o="496" _o-sc="38,0" _o-l="38" _o-e="39,0" _o-tl="-1" _o-s="38,0" _o-cl="0" id="54ed0c3e">Get single column by index (starting from 0):</p>

<code _o="573" _o-sc="43,0" _o-l="42" _o-e="45,3" _o-tl="-1" _o-s="42,0" style="block" _o-cl="0" id="2b408e6a" lang="kotlin">df.getColumn(2)
df.getColumnGroup(0).getColumn(1)
</code>

</topic>