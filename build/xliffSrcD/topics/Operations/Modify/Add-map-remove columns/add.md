<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="add" title="add" _md-based="true"> 
<p _o="89" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="860f7172">Returns <code _o="97" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="2678c1b">DataFrame</code> which contains all columns from original <code _o="150" _o-sc="4,62" _o-l="4" _o-e="4,72" _o-tl="-1" _o-s="4,61" _o-cl="61" id="3dfde08">DataFrame</code> followed by newly added columns. Original <code _o="204" _o-sc="4,116" _o-l="4" _o-e="4,126" _o-tl="-1" _o-s="4,115" _o-cl="115" id="d7733cae">DataFrame</code> is not modified.</p>
<p _o="234" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="4c6e84f1"><b _o="234" _o-sc="6,2" _o-l="6" _o-e="6,48" _o-tl="-1" _o-s="6,0" _o-cl="0" id="369e01d4">Create new column and add it to <code _o="268" _o-sc="6,35" _o-l="6" _o-e="6,45" _o-tl="-1" _o-s="6,34" _o-cl="34" id="2c4af026">DataFrame</code>:</b></p>
<code _o="284" _o-sc="9,0" _o-l="8" _o-e="12,3" _o-tl="79" _o-s="8,0" style="block" _o-cl="0" id="9704fffb" lang="kotlin">add(columnName) { rowExpression }

rowExpression: DataRow.(DataRow) -> Value
</code>

<tabs id="bd4dd101">
<tab id="c178ca3c" title="Properties">
<code _o="425" _o-sc="19,0" _o-l="18" _o-e="20,3" _o-tl="-1" _o-s="18,0" style="block" _o-cl="0" id="ed3f1d18" lang="kotlin">df.add("year of birth") { 2021 - age }
</code>
</tab>
<tab _o="479" _o-sc="22,6" _o-l="22" _o-e="24,0" _o-tl="5" _o-s="22,0" _o-cl="0" id="60a0631a" title="Accessors">
<code _o="511" _o-sc="26,0" _o-l="25" _o-e="30,3" _o-tl="31" _o-s="25,0" style="block" _o-cl="0" id="6c6dd931" lang="kotlin">val age by column&lt;Int>()
val yearOfBirth by column&lt;Int>("year of birth")

df.add(yearOfBirth) { 2021 - age }
</code>
</tab>
<tab _o="635" _o-sc="32,6" _o-l="32" _o-e="34,0" _o-tl="5" _o-s="32,0" _o-cl="0" id="fa57412d" title="Strings">
<code _o="665" _o-sc="36,0" _o-l="35" _o-e="37,3" _o-tl="52" _o-s="35,0" style="block" _o-cl="0" id="cca20869" lang="kotlin">df.add("year of birth") { 2021 - "age"&lt;Int>() }
</code>
</tab></tabs>

<p _o="755" _o-sc="42,0" _o-l="42" _o-e="43,0" _o-tl="-1" _o-s="42,0" _o-cl="0" id="a0450c89">See <a _o="759" _o-sc="42,5" LinkStatus="UNKNOWN" _o-l="42" _o-e="42,49" _o-tl="-1" _o-s="42,4" href="DataRow.md#row-expressions" _o-cl="4" id="c2a2297c">row expressions</a></p>
<p _o="806" _o-sc="44,0" _o-l="44" _o-e="45,0" _o-tl="-1" _o-s="44,0" _o-cl="0" id="261c8aa4"><b _o="806" _o-sc="44,2" _o-l="44" _o-e="44,50" _o-tl="-1" _o-s="44,0" _o-cl="0" id="ae81842c">Create and add several columns to <code _o="842" _o-sc="44,37" _o-l="44" _o-e="44,47" _o-tl="-1" _o-s="44,36" _o-cl="36" id="90a11d71">DataFrame</code>:</b></p>
<code _o="858" _o-sc="47,0" _o-l="46" _o-e="54,3" _o-tl="-1" _o-s="46,0" style="block" _o-cl="0" id="de0d9fe7" lang="kotlin">add { 
    columnMapping
    columnMapping
    ...
}

columnMapping = column into columnName | columnName from column | columnName from { rowExpression }
</code>

<tabs id="3b9440bb">
<tab id="8aedb49" title="Properties">
<code _o="1080" _o-sc="61,0" _o-l="60" _o-e="67,3" _o-tl="-1" _o-s="60,0" style="block" _o-cl="0" id="47d50da" lang="kotlin">df.add {
    "year of birth" from 2021 - age
    age gt 18 into "is adult"
    name.lastName.length() into "last name length"
    "full name" from { name.firstName + " " + name.lastName }
}
</code>
</tab>
<tab _o="1285" _o-sc="69,6" _o-l="69" _o-e="71,0" _o-tl="5" _o-s="69,0" _o-cl="0" id="efac6cb1" title="Accessors">
<code _o="1317" _o-sc="73,0" _o-l="72" _o-e="88,3" _o-tl="30" _o-s="72,0" style="block" _o-cl="0" id="f53af72d" lang="kotlin">val yob = column&lt;Int>("year of birth")
val lastNameLength = column&lt;Int>("last name length")
val age by column&lt;Int>()
val isAdult = column&lt;Boolean>("is adult")
val fullName = column&lt;String>("full name")
val name by columnGroup()
val firstName by name.column&lt;String>()
val lastName by name.column&lt;String>()

df.add {
    yob from 2021 - age
    age gt 18 into isAdult
    lastName.length() into lastNameLength
    fullName from { firstName() + " " + lastName() }
}
</code>
</tab>
<tab _o="1795" _o-sc="90,6" _o-l="90" _o-e="92,0" _o-tl="5" _o-s="90,0" _o-cl="0" id="7279c248" title="Strings">
<code _o="1825" _o-sc="94,0" _o-l="93" _o-e="100,3" _o-tl="60" _o-s="93,0" style="block" _o-cl="0" id="50c737c0" lang="kotlin">df.add {
    "year of birth" from 2021 - "age"&lt;Int>()
    "age"&lt;Int>() gt 18 into "is adult"
    "name"["lastName"]&lt;String>().length() into "last name length"
    "full name" from { "name"["firstName"]&lt;String>() + " " + "name"["lastName"]&lt;String>() }
}
</code>
</tab></tabs>

<p _o="2120" _o-sc="105,0" _o-l="105" _o-e="106,0" _o-tl="-1" _o-s="105,0" _o-cl="0" id="d244701d"><b _o="2120" _o-sc="105,2" _o-l="105" _o-e="105,39" _o-tl="-1" _o-s="105,0" _o-cl="0" id="9f60656">Add existing column to <code _o="2145" _o-sc="105,26" _o-l="105" _o-e="105,36" _o-tl="-1" _o-s="105,25" _o-cl="25" id="3e9784db">DataFrame</code>:</b></p>

<code _o="2186" _o-sc="110,0" _o-l="109" _o-e="114,3" _o-tl="-1" _o-s="109,0" style="block" _o-cl="0" id="dc85beb7" lang="kotlin">val score by columnOf(4, 3, 5, 2, 1, 3, 5)

df.add(score)
df + score
</code>

<p _o="2283" _o-sc="118,0" _o-l="118" _o-e="119,0" _o-tl="-1" _o-s="118,0" _o-cl="0" id="42ad2020"><b _o="2283" _o-sc="118,2" _o-l="118" _o-e="118,45" _o-tl="-1" _o-s="118,0" _o-cl="0" id="4d048557">Add all columns from another <code _o="2314" _o-sc="118,32" _o-l="118" _o-e="118,42" _o-tl="-1" _o-s="118,31" _o-cl="31" id="e326f7c7">DataFrame</code>:</b></p>

<code _o="2350" _o-sc="123,0" _o-l="122" _o-e="124,3" _o-tl="-1" _o-s="122,0" style="block" _o-cl="0" id="fd34cdc3" lang="kotlin">df.add(df1, df2)
</code>

</topic>