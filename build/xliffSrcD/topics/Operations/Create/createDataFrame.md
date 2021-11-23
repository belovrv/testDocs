<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="createDataFrame" title="Create DataFrame" _md-based="true"> 
<p _o="101" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="77dae30a">This section describes ways to create <a _o="139" _o-sc="3,39" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,65" _o-tl="-1" _o-s="3,38" href="DataFrame.md" _o-cl="38" id="b3ba4bd5"><code _o="140" _o-sc="3,40" _o-l="3" _o-e="3,50" _o-tl="-1" _o-s="3,39" _o-cl="39" id="3092cb91">DataFrame</code></a>.</p>
<chapter _o="169" _o-sc="5,4" _o-l="5" _o-e="5,15" _o-tl="-1" _o-s="5,0" _o-cl="0" id="dataframeof" title="dataFrameOf">
<p _o="186" _o-sc="7,0" _o-l="7" _o-e="8,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="1cdc19f9">Returns <a _o="194" _o-sc="7,9" LinkStatus="UNKNOWN" _o-l="7" _o-e="7,35" _o-tl="-1" _o-s="7,8" href="DataFrame.md" _o-cl="8" id="f4b451c4"><code _o="195" _o-sc="7,10" _o-l="7" _o-e="7,20" _o-tl="-1" _o-s="7,9" _o-cl="9" id="ff78534a">DataFrame</code></a> with given column names and values.</p>

<code _o="290" _o-sc="12,0" _o-l="11" _o-e="18,3" _o-tl="-1" _o-s="11,0" style="block" _o-cl="0" id="aa248020" lang="kotlin">// DataFrame with 2 columns and 3 rows
val df = dataFrameOf("name", "age")(
    "Alice", 15,
    "Bob", 20,
    "Mark", 100
)
</code>


<code _o="484" _o-sc="25,0" _o-l="24" _o-e="30,3" _o-tl="-1" _o-s="24,0" style="block" _o-cl="0" id="6280fba7" lang="kotlin">val name by columnOf("Alice", "Bob", "Mark")
val age by columnOf(15, 20, 22)

// DataFrame with 2 columns
val df = dataFrameOf(name, age)
</code>


<code _o="697" _o-sc="37,0" _o-l="36" _o-e="44,3" _o-tl="-1" _o-s="36,0" style="block" _o-cl="0" id="579564a0" lang="kotlin">val names = listOf("name", "age")
val values = listOf(
    "Alice", 15,
    "Bob", 20,
    "Mark", 22
)
val df = dataFrameOf(names, values)
</code>


<code _o="902" _o-sc="51,0" _o-l="50" _o-e="53,3" _o-tl="58" _o-s="50,0" style="block" _o-cl="0" id="20e30453" lang="kotlin">// Multiplication table
dataFrameOf(1..10) { x -> (1..10).map { x * it } }
</code>


<code _o="1044" _o-sc="60,0" _o-l="59" _o-e="63,3" _o-tl="-1" _o-s="59,0" style="block" _o-cl="0" id="9b5f613c" lang="kotlin">// DataFrame with 5 columns filled with 7 random double values:
val names = (1..5).map { "column$it" }
val df = dataFrameOf(names).randomDouble(7)
</code>


<code _o="1260" _o-sc="70,0" _o-l="69" _o-e="74,3" _o-tl="-1" _o-s="69,0" style="block" _o-cl="0" id="6cb42fcd" lang="kotlin">val names = listOf("first", "second", "third")

// DataFrame with 3 columns, fill each column with 15 `true` values
val df = dataFrameOf(names).fill(15, true)
</code>

</chapter><chapter _o="1447" _o-sc="78,4" _o-l="78" _o-e="78,15" _o-tl="-1" _o-s="78,0" _o-cl="0" id="todataframe" title="toDataFrame">
<p _o="1464" _o-sc="80,0" _o-l="80" _o-e="81,0" _o-tl="37" _o-s="80,0" _o-cl="0" id="d7bcdbb7"><code _o="1464" _o-sc="80,1" _o-l="80" _o-e="80,11" _o-tl="-1" _o-s="80,0" _o-cl="0" id="cf77f6ba">DataFrame</code> from <code _o="1481" _o-sc="80,18" _o-l="80" _o-e="80,39" _o-tl="20" _o-s="80,17" _o-cl="17" id="8abf0de8">Iterable&lt;DataColumn></code>:</p>

<code _o="1547" _o-sc="85,0" _o-l="84" _o-e="89,3" _o-tl="-1" _o-s="84,0" style="block" _o-cl="0" id="e7be5d17" lang="kotlin">val name by columnOf("Alice", "Bob", "Mark")
val age by columnOf(15, 20, 22)

listOf(name, age).toDataFrame()
</code>

<p _o="1685" _o-sc="93,0" _o-l="93" _o-e="94,0" _o-tl="36" _o-s="93,0" _o-cl="0" id="57d6883b"><code _o="1685" _o-sc="93,1" _o-l="93" _o-e="93,11" _o-tl="-1" _o-s="93,0" _o-cl="0" id="37e9ac57">DataFrame</code> from <code _o="1702" _o-sc="93,18" _o-l="93" _o-e="93,39" _o-tl="19" _o-s="93,17" _o-cl="17" id="f245b44b">Map&lt;String, List&lt;*>></code>:</p>

<code _o="1763" _o-sc="98,0" _o-l="97" _o-e="102,3" _o-tl="-1" _o-s="97,0" style="block" _o-cl="0" id="b9b8ae1d" lang="kotlin">val map = mapOf("name" to listOf("Alice", "Bob", "Mark"), "age" to listOf(15, 20, 22))

// DataFrame with 2 columns
map.toDataFrame()
</code>

</chapter><chapter _o="1925" _o-sc="106,4" _o-l="106" _o-e="106,19" _o-tl="-1" _o-s="106,0" _o-cl="0" id="createdataframe" title="createDataFrame">
<p _o="1946" _o-sc="108,0" _o-l="108" _o-e="109,0" _o-tl="-1" _o-s="108,0" _o-cl="0" id="8ee5bba">Creates <code _o="1954" _o-sc="108,9" _o-l="108" _o-e="108,19" _o-tl="-1" _o-s="108,8" _o-cl="8" id="15501ca3">DataFrame</code> from <code _o="1971" _o-sc="108,26" _o-l="108" _o-e="108,35" _o-tl="-1" _o-s="108,25" _o-cl="25" id="9afe77b3">Iterable</code> of any objects .</p>

<code _o="2039" _o-sc="113,0" _o-l="112" _o-e="117,3" _o-tl="-1" _o-s="112,0" style="block" _o-cl="0" id="a469d91b" lang="kotlin">data class Person(val name: String, val age: Int)
val persons = listOf(Person("Alice", 15), Person("Bob", 20), Person("Mark", 22))

val df = persons.createDataFrame()
</code>

<p _o="2234" _o-sc="121,0" _o-l="121" _o-e="122,0" _o-tl="-1" _o-s="121,0" _o-cl="0" id="1c6867c3">Scans object properties using reflection and creates <a _o="2287" _o-sc="121,54" LinkStatus="UNKNOWN" _o-l="121" _o-e="121,93" _o-tl="-1" _o-s="121,53" href="DataColumn.md#valuecolumn" _o-cl="53" id="2a9de58b">ValueColumn</a> for every property. Scope of properties for scanning is defined at compile-time by formal types of objects in <code _o="2438" _o-sc="121,205" _o-l="121" _o-e="121,214" _o-tl="-1" _o-s="121,204" _o-cl="204" id="7931b2dd">Iterable</code>, so properties of implementation classes will not be scanned.</p>
<p _o="2512" _o-sc="123,0" _o-l="123" _o-e="124,0" _o-tl="-1" _o-s="123,0" _o-cl="0" id="9bf6ee7">Specify <code _o="2520" _o-sc="123,9" _o-l="123" _o-e="123,15" _o-tl="-1" _o-s="123,8" _o-cl="8" id="c986b3ce">depth</code> parameter to perform deep object graph traversal and convert nested objects into <a _o="2609" _o-sc="123,98" LinkStatus="UNKNOWN" _o-l="123" _o-e="123,138" _o-tl="-1" _o-s="123,97" href="DataColumn.md#columngroup" _o-cl="97" id="c0f73586">ColumnGroups</a> and <a _o="2655" _o-sc="123,144" LinkStatus="UNKNOWN" _o-l="123" _o-e="123,184" _o-tl="-1" _o-s="123,143" href="DataColumn.md#framecolumn" _o-cl="143" id="b0249a73">FrameColumns</a>:</p>

<code _o="2742" _o-sc="128,0" _o-l="127" _o-e="138,3" _o-tl="196" _o-s="127,0" style="block" _o-cl="0" id="fa18a51f" lang="kotlin">data class Name(val firstName: String, val lastName: String)
data class Score(val subject: String, val value: Int)
data class Student(val name: Name, val age: Int, val scores: List&lt;Score>)

val students = listOf(
    Student(Name("Alice", "Cooper"), 15, listOf(Score("math", 4), Score("biology", 3))),
    Student(Name("Bob", "Marley"), 20, listOf(Score("music", 5)))
)

val df = students.createDataFrame(depth = 2)
</code>

<p _o="3186" _o-sc="142,0" _o-l="142" _o-e="143,0" _o-tl="-1" _o-s="142,0" _o-cl="0" id="14dc0d5d">For detailed control over object graph transformation use configuration DSL. It allows you to exclude particular properties or classes from object graph traversal, compute additional columns and configure column grouping.</p>

<code _o="3463" _o-sc="147,0" _o-l="146" _o-e="163,3" _o-tl="288" _o-s="146,0" style="block" _o-cl="0" id="d3c4c2e9" lang="kotlin">val df = students.createDataFrame {
    // add value column
    "year of birth" from { 2021 - it.age }

    // scan all properties
    properties(depth = 2) {
        exclude(Score::subject) // `subject` property will be skipped from object graph traversal
        preserve&lt;Name>() // `Name` objects will be stored as-is without transformation into DataFrame
    }

    // add column group
    "summary" {
        "max score" from { it.scores.maxOf { it.value } }
        "min score" from { it.scores.minOf { it.value } }
    }
}
</code>

</chapter></topic>