<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="indexing" title="Indexing" _md-based="true"> 

<tabs id="2e8bc042">
<tab id="40c15ce8" title="Properties">
<code _o="147" _o-sc="9,0" _o-l="8" _o-e="11,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="6d7130d5" lang="kotlin">df.age[1]
df[1].age
</code>
</tab>
<tab _o="182" _o-sc="13,6" _o-l="13" _o-e="15,0" _o-tl="5" _o-s="13,0" _o-cl="0" id="5eae1674" title="Accessors">
<code _o="214" _o-sc="17,0" _o-l="16" _o-e="21,3" _o-tl="34" _o-s="16,0" style="block" _o-cl="0" id="1bc5898f" lang="kotlin">val age by column&lt;String>()

df[age][1]
df[1][age]
</code>
</tab>
<tab _o="280" _o-sc="23,6" _o-l="23" _o-e="25,0" _o-tl="5" _o-s="23,0" _o-cl="0" id="c0ba3b2d" title="Strings">
<code _o="310" _o-sc="27,0" _o-l="26" _o-e="29,3" _o-tl="-1" _o-s="26,0" style="block" _o-cl="0" id="5fdd2754" lang="kotlin">df["age"][1]
df[1]["age"]
</code>
</tab></tabs>

</topic>