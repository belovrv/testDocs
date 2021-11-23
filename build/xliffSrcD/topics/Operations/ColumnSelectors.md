<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="ColumnSelectors" title="Column selectors" _md-based="true"> 
<p _o="102" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="26dfcdda"><code _o="102" _o-sc="4,1" _o-l="4" _o-e="4,11" _o-tl="-1" _o-s="4,0" _o-cl="0" id="8491de44">DataFrame</code> provides DSL for selecting arbitrary set of columns.</p>
<p _o="168" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="2b1e2a86">Column selectors are used in many operations:</p>

<code _o="250" _o-sc="11,0" _o-l="10" _o-e="17,3" _o-tl="63" _o-s="10,0" style="block" _o-cl="0" id="4aec0399" lang="kotlin">df.select { age and name }
df.fillNaNs { dfsOf&lt;Double>() }.withZero()
df.remove { cols { it.hasNulls() } }
df.update { city }.notNull { it.lowercase() }
df.gather { numberCols() }.into("key", "value")
df.move { name.firstName and name.lastName }.after { city }
</code>

<p _o="539" _o-sc="21,0" _o-l="21" _o-e="22,0" _o-tl="-1" _o-s="21,0" _o-cl="0" id="dedb6db1"><b _o="539" _o-sc="21,2" _o-l="21" _o-e="21,27" _o-tl="-1" _o-s="21,0" _o-cl="0" id="9c1adfe6">Select columns by name:</b></p>

<tabs id="93fe6ebb">
<tab id="b9d4a9d0" title="Properties">
<code _o="629" _o-sc="28,0" _o-l="27" _o-e="55,3" _o-tl="-1" _o-s="27,0" style="block" _o-cl="0" id="e6788c17" lang="kotlin">// by column name
df.select { it.name }
df.select { name }

// by column path
df.select { name.firstName }

// with a new name
df.select { name named "Full Name" }

// converted
df.select { name.firstName.map { it.lowercase() } }

// column arithmetics
df.select { 2021 - age }

// two columns
df.select { name and age }

// range of columns
df.select { name..age }

// all children of ColumnGroup
df.select { name.all() }

// dfs traversal of children columns
df.select { name.dfs() }
</code>
</tab>
<tab _o="1130" _o-sc="57,6" _o-l="57" _o-e="59,0" _o-tl="5" _o-s="57,0" _o-cl="0" id="864c2082" title="Accessors">
<code _o="1162" _o-sc="61,0" _o-l="60" _o-e="91,3" _o-tl="150" _o-s="60,0" style="block" _o-cl="0" id="669425ce" lang="kotlin">// by column name
val name by columnGroup()
df.select { it[name] }
df.select { name }

// by column path
val firstName by name.column&lt;String>()
df.select { firstName }

// with a new name
df.select { name named "First Name" }

// converted
df.select { firstName.map { it.lowercase() } }

// column arithmetics
val age by column&lt;Int>()
df.select { 2021 - age }

// two columns
df.select { name and age }

// range of columns
df.select { name..age }

// all children of ColumnGroup
df.select { name.all() }

// dfs traversal of children columns
df.select { name.dfs() }
</code>
</tab>
<tab _o="1745" _o-sc="93,6" _o-l="93" _o-e="95,0" _o-tl="5" _o-s="93,0" _o-cl="0" id="8b59d614" title="Strings">
<code _o="1775" _o-sc="97,0" _o-l="96" _o-e="124,3" _o-tl="256" _o-s="96,0" style="block" _o-cl="0" id="553d411a" lang="kotlin">// by column name
df.select { it["name"] }

// by column path
df.select { it["name"]["firstName"] }
df.select { "name"["firstName"] }

// with a new name
df.select { "name" named "First Name" }

// converted
df.select { "name"["firstName"]&lt;String>().map { it.uppercase() } }

// column arithmetics
df.select { 2021 - "age"() }

// two columns
df.select { "name" and "age" }

// by range of names
df.select { "name".."age" }

// all children of ColumnGroup
df.select { "name".all() }

// dfs traversal of children columns
df.select { "name".dfs() }
</code>
</tab></tabs>

<p _o="2365" _o-sc="129,0" _o-l="129" _o-e="130,0" _o-tl="-1" _o-s="129,0" _o-cl="0" id="f9bfd2c0"><b _o="2365" _o-sc="129,2" _o-l="129" _o-e="129,35" _o-tl="-1" _o-s="129,0" _o-cl="0" id="2ec19bc5">Select columns by column index:</b></p>

<code _o="2440" _o-sc="134,0" _o-l="133" _o-e="142,3" _o-tl="-1" _o-s="133,0" style="block" _o-cl="0" id="e4571d3a" lang="kotlin">// by index
df.select { col(2) }

// by several indices
df.select { cols(0, 1, 3) }

// by range of indices
df.select { cols(1..4) }
</code>

<p _o="2601" _o-sc="146,0" _o-l="146" _o-e="147,0" _o-tl="-1" _o-s="146,0" _o-cl="0" id="4741a535"><b _o="2601" _o-sc="146,2" _o-l="146" _o-e="146,27" _o-tl="-1" _o-s="146,0" _o-cl="0" id="fe620f">Other column selectors:</b></p>

<code _o="2663" _o-sc="151,0" _o-l="150" _o-e="187,3" _o-tl="113" _o-s="150,0" style="block" _o-cl="0" id="a086c622" lang="kotlin">// by condition
df.select { cols { it.name.startsWith("year") } }

// by type
df.select { colsOf&lt;String>() }
df.select { stringCols() }

// by type with condition
df.select { colsOf&lt;String> { !it.hasNulls() } }
df.select { stringCols { !it.hasNulls() } }

// all top-level columns
df.select { all() }

// first/last n columns
df.select { take(2) }
df.select { takeLast(2) }

// all except first/last n columns
df.select { drop(2) }
df.select { dropLast(2) }

// dfs traversal of columns
df.select { dfs() }

// dfs traversal with condition
df.select { dfs { it.name.contains(":") } }

// columns of given type in dfs traversal
df.select { dfsOf&lt;String>() }

// all columns except given column set
df.select { except { colsOf&lt;String>() } }

// union of column sets
df.select { take(2) and col(3) }
</code>

<p _o="3488" _o-sc="191,0" _o-l="191" _o-e="192,0" _o-tl="-1" _o-s="191,0" _o-cl="0" id="fb607198"><b _o="3488" _o-sc="191,2" _o-l="191" _o-e="191,39" _o-tl="-1" _o-s="191,0" _o-cl="0" id="f77b2b57">Modify the set of selected columns:</b></p>

<code _o="3567" _o-sc="196,0" _o-l="195" _o-e="209,3" _o-tl="-1" _o-s="195,0" style="block" _o-cl="0" id="e4599791" lang="kotlin">// first/last n columns in column set
df.select { dfs().take(3) }
df.select { dfs().takeLast(3) }

// all except first/last n columns in column set
df.select { dfs().drop(3) }
df.select { dfs().dropLast(3) }

// filter column set by condition
df.select { dfs().filter { it.name.startsWith("year") } }

// exclude columns from column set
df.select { dfs().except { age } }
</code>

</topic>