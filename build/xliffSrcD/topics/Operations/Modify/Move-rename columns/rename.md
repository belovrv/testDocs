<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="rename" title="rename" _md-based="true"> <p _o="25" _o-sc="2,0" _o-l="2" _o-e="3,0" _o-tl="-1" _o-s="2,0" _o-cl="0" id="cd531465">Renames one or several columns without changing its location in <code _o="89" _o-sc="2,65" _o-l="2" _o-e="2,75" _o-tl="-1" _o-s="2,64" _o-cl="64" id="af893989">DataFrame</code></p>
<code _o="102" _o-sc="5,0" _o-l="4" _o-e="9,3" _o-tl="121" _o-s="4,0" style="block" _o-cl="0" id="276a8caa" lang="kotlin">df.rename { columns }.into(name)
df.rename { columns }.into { nameExpression }

nameExpression = (DataColumn) -> String
</code>
</topic>