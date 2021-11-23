<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="update" title="update" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="6b4085b7">Returns <code _o="100" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="42427912">DataFrame</code> with changed values in some cells. Column types can not be changed.</p>
<code _o="181" _o-sc="7,0" _o-l="6" _o-e="16,3" _o-tl="288" _o-s="6,0" style="block" _o-cl="0" id="5128a256" lang="kotlin">update { columns }
    [.where { rowCondition } ]
    [.at(rowIndices) ] 
     .with { rowExpression } | .notNull { rowExpression } | .perCol { colExpression } | .perRowCol { rowColExpression } | .withValue(value) | .withNull() | .withZero() 

rowCondition: DataRow.(OldValue) -> Boolean
rowExpression: DataRow.(OldValue) -> NewValue
colExpression: DataColumn.(DataColumn) -> NewValue
rowColExpression: DataRow.(DataColumn) -> NewValue
</code>
<p _o="632" _o-sc="18,0" _o-l="18" _o-e="19,0" _o-tl="-1" _o-s="18,0" _o-cl="0" id="ab26a57a">See <a _o="636" _o-sc="18,5" LinkStatus="UNKNOWN" _o-l="18" _o-e="18,42" _o-tl="-1" _o-s="18,4" href="ColumnSelectors.md" _o-cl="4" id="b0354f24">column selectors</a> and <a _o="679" _o-sc="18,48" LinkStatus="UNKNOWN" _o-l="18" _o-e="18,92" _o-tl="-1" _o-s="18,47" href="DataRow.md#row-expressions" _o-cl="47" id="fb20c9bf">row expressions</a></p>

<code _o="746" _o-sc="23,0" _o-l="22" _o-e="27,3" _o-tl="68" _o-s="22,0" style="block" _o-cl="0" id="ddf22b29" lang="kotlin">df.update { age }.with { it * 2 }
df.update { dfsOf&lt;String>() }.with { it.uppercase() }
df.update { weight }.at(1..4).notNull { it / 2 }
df.update { name.lastName and age }.at(1, 3, 4).withNull()
</code>

<p _o="970" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="70d9c1ce">Update with constant value:</p>

<code _o="1028" _o-sc="36,0" _o-l="35" _o-e="37,3" _o-tl="-1" _o-s="35,0" style="block" _o-cl="0" id="844d729b" lang="kotlin">df.update { city }.where { name.firstName == "Alice" }.withValue("Paris")
</code>

<p _o="1130" _o-sc="41,0" _o-l="41" _o-e="42,0" _o-tl="-1" _o-s="41,0" _o-cl="0" id="d9b6ae4a">Update with value depending on row:</p>

<code _o="1191" _o-sc="46,0" _o-l="45" _o-e="47,3" _o-tl="-1" _o-s="45,0" style="block" _o-cl="0" id="e88a959d" lang="kotlin">df.update { city }.with { name.firstName + " from " + it }
</code>

<p _o="1278" _o-sc="51,0" _o-l="51" _o-e="52,0" _o-tl="-1" _o-s="51,0" _o-cl="0" id="1d99c965">Update with value depending on column:</p>

<code _o="1347" _o-sc="56,0" _o-l="55" _o-e="57,3" _o-tl="-1" _o-s="55,0" style="block" _o-cl="0" id="c1b2ce1d" lang="kotlin">df.update { numberCols() }.perCol { mean(skipNA = true) }
</code>

<p _o="1433" _o-sc="61,0" _o-l="61" _o-e="62,0" _o-tl="-1" _o-s="61,0" _o-cl="0" id="9d4baae2">Update with value depending on row and column:</p>

<code _o="1510" _o-sc="66,0" _o-l="65" _o-e="67,3" _o-tl="59" _o-s="65,0" style="block" _o-cl="0" id="14178ef1" lang="kotlin">df.update { stringCols() }.perRowCol { row, col -> col.name() + ": " + row.index() }
</code>

</topic>