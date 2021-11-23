<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="map" title="map" _md-based="true"> 
<p _o="89" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="8924ab9">Creates <code _o="97" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="16a43742">DataFrame</code> or <code _o="112" _o-sc="4,24" _o-l="4" _o-e="4,35" _o-tl="-1" _o-s="4,23" _o-cl="23" id="5f15c44d">DataColumn</code> with values computed from rows of original <code _o="168" _o-sc="4,80" _o-l="4" _o-e="4,90" _o-tl="-1" _o-s="4,79" _o-cl="79" id="53df967a">DataFrame</code>.</p>
<p _o="182" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="2e021983"><b _o="182" _o-sc="6,2" _o-l="6" _o-e="6,26" _o-tl="-1" _o-s="6,0" _o-cl="0" id="340e603b">Map into <code _o="193" _o-sc="6,12" _o-l="6" _o-e="6,23" _o-tl="-1" _o-s="6,11" _o-cl="11" id="845d6802">DataColumn</code>:</b></p>
<code _o="210" _o-sc="9,0" _o-l="8" _o-e="12,3" _o-tl="91" _o-s="8,0" style="block" _o-cl="0" id="bc53f829" lang="kotlin">map(columnName) { rowExpression }: DataColumn

rowExpression: DataRow.(DataRow) -> Value
</code>
<p _o="314" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="2ce55545">See <a _o="318" _o-sc="14,5" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,49" _o-tl="-1" _o-s="14,4" href="DataRow.md#row-expressions" _o-cl="4" id="9b2a2ff0">row expressions</a></p>
<p _o="365" _o-sc="16,0" _o-l="16" _o-e="17,0" _o-tl="-1" _o-s="16,0" _o-cl="0" id="731a3d4e"><b _o="365" _o-sc="16,2" _o-l="16" _o-e="16,25" _o-tl="-1" _o-s="16,0" _o-cl="0" id="2340d7ba">Map into <code _o="376" _o-sc="16,12" _o-l="16" _o-e="16,22" _o-tl="-1" _o-s="16,11" _o-cl="11" id="d53576fe">DataFrame</code>:</b></p>
<code _o="392" _o-sc="19,0" _o-l="18" _o-e="26,3" _o-tl="-1" _o-s="18,0" style="block" _o-cl="0" id="4a368cd9" lang="kotlin">map { 
    columnMapping
    columnMapping
    ...
} : DataFrame

columnMapping = column into columnName | columnName from column | columnName from { rowExpression } | +column  
</code>

<tabs id="6cdc145d">
<tab id="77bb3c9d" title="Properties">
<code _o="638" _o-sc="33,0" _o-l="32" _o-e="40,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="708f8455" lang="kotlin">df.map {
    "year of birth" from 2021 - age
    age gt 18 into "is adult"
    name.lastName.length() into "last name length"
    "full name" from { name.firstName + " " + name.lastName }
    +city
}
</code>
</tab>
<tab _o="853" _o-sc="42,6" _o-l="42" _o-e="44,0" _o-tl="5" _o-s="42,0" _o-cl="0" id="6ec4c5f" title="Accessors">
<code _o="885" _o-sc="46,0" _o-l="45" _o-e="63,3" _o-tl="30" _o-s="45,0" style="block" _o-cl="0" id="dd2a3ab" lang="kotlin">val yob = column&lt;Int>("year of birth")
val lastNameLength = column&lt;Int>("last name length")
val age by column&lt;Int>()
val isAdult = column&lt;Boolean>("is adult")
val fullName = column&lt;String>("full name")
val name by columnGroup()
val firstName by name.column&lt;String>()
val lastName by name.column&lt;String>()
val city by column&lt;String?>()

df.map {
    yob from 2021 - age
    age gt 18 into isAdult
    lastName.length() into lastNameLength
    fullName from { firstName() + " " + lastName() }
    +city
}
</code>
</tab>
<tab _o="1403" _o-sc="65,6" _o-l="65" _o-e="67,0" _o-tl="5" _o-s="65,0" _o-cl="0" id="c3274ae5" title="Strings">
<code _o="1433" _o-sc="69,0" _o-l="68" _o-e="76,3" _o-tl="60" _o-s="68,0" style="block" _o-cl="0" id="587fd9ed" lang="kotlin">df.map {
    "year of birth" from 2021 - "age"&lt;Int>()
    "age"&lt;Int>() gt 18 into "is adult"
    "name"["lastName"]&lt;String>().length() into "last name length"
    "full name" from { "name"["firstName"]&lt;String>() + " " + "name"["lastName"]&lt;String>() }
    +"city"
}
</code>
</tab></tabs>

</topic>