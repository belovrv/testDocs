<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="replace" title="replace" _md-based="true"> 
<p _o="92" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="493a554a">Replaces one or several columns with new columns.</p>
<code _o="143" _o-sc="6,0" _o-l="5" _o-e="10,3" _o-tl="124" _o-s="5,0" style="block" _o-cl="0" id="1b2c3bfa" lang="kotlin">replace { columns }
    .with(newColumns) | .with { columnExpression }

columnExpression: DataFrame.(DataColumn) -> DataColumn
</code>
<p _o="285" _o-sc="12,0" _o-l="12" _o-e="13,0" _o-tl="-1" _o-s="12,0" _o-cl="0" id="ee85992c">See <a _o="289" _o-sc="12,5" LinkStatus="UNKNOWN" _o-l="12" _o-e="12,42" _o-tl="-1" _o-s="12,4" href="ColumnSelectors.md" _o-cl="4" id="53105fd1">column selectors</a></p>

<code _o="350" _o-sc="17,0" _o-l="16" _o-e="20,3" _o-tl="-1" _o-s="16,0" style="block" _o-cl="0" id="562c6bd5" lang="kotlin">df.replace { name }.with { name.firstName }
df.replace { stringCols() }.with { it.lowercase() }
df.replace { age }.with { 2021 - age named "year" }
</code>

<p _o="526" _o-sc="24,0" _o-l="24" _o-e="25,0" _o-tl="-1" _o-s="24,0" _o-cl="0" id="d812bc41">Note: <code _o="532" _o-sc="24,7" _o-l="24" _o-e="24,54" _o-tl="-1" _o-s="24,6" _o-cl="6" id="35eba045">replace { columns }.with { columnExpression } </code> is equivalent to <code _o="598" _o-sc="24,73" _o-l="24" _o-e="24,117" _o-tl="-1" _o-s="24,72" _o-cl="72" id="8cded94a">convert { columns }.to { columnExpression }</code>. See <a _o="649" _o-sc="24,124" LinkStatus="UNKNOWN" _o-l="24" _o-e="24,144" _o-tl="-1" _o-s="24,123" href="convert.md" _o-cl="123" id="17603648">convert</a></p>
</topic>