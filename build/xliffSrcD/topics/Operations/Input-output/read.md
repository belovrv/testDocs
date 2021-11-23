<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="read" title="Reading dataframes" _md-based="true"> 
<p _o="101" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="b2bae097"><code _o="101" _o-sc="3,1" _o-l="3" _o-e="3,11" _o-tl="-1" _o-s="3,0" _o-cl="0" id="a9138847">DataFrame</code> supports CSV and JSON input formats.</p>
<p _o="151" _o-sc="5,0" _o-l="5" _o-e="6,0" _o-tl="-1" _o-s="5,0" _o-cl="0" id="3a02ce7b"><code _o="151" _o-sc="5,1" _o-l="5" _o-e="5,6" _o-tl="-1" _o-s="5,0" _o-cl="0" id="d99dcd59">read</code> method automatically detects input format based on file extension and content</p>
<code _o="237" _o-sc="8,0" _o-l="7" _o-e="9,3" _o-tl="-1" _o-s="7,0" style="block" _o-cl="0" id="c9c63d6f" lang="kotlin">DataFrame.read("input.csv")
</code>
<p _o="280" _o-sc="11,0" _o-l="11" _o-e="12,0" _o-tl="-1" _o-s="11,0" _o-cl="0" id="bcd9085c">Input string can be a file path or URL.</p>
<chapter _o="321" _o-sc="13,4" _o-l="13" _o-e="13,15" _o-tl="-1" _o-s="13,0" _o-cl="0" id="reading-csv" title="Reading CSV">
<p _o="337" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="fae49bb7">All these calls are valid:</p>
<code _o="365" _o-sc="17,0" _o-l="16" _o-e="23,3" _o-tl="-1" _o-s="16,0" style="block" _o-cl="0" id="b7bc0bdd" lang="kotlin">import java.io.File
import java.net.URL

DataFrame.readCSV("input.csv")
DataFrame.readCSV(File("input.csv"))
DataFrame.readCSV(URL("https://raw.githubusercontent.com/Kotlin/dataframe/master/data/securities.csv"))
</code>
<p _o="593" _o-sc="25,0" _o-l="25" _o-e="28,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="c3f1091">All <code _o="597" _o-sc="25,5" _o-l="25" _o-e="25,13" _o-tl="-1" _o-s="25,4" _o-cl="4" id="3967225f">readCSV</code> overloads support different options.
For example, you can specify custom delimiter if it differs from <code _o="709" _o-sc="26,66" _o-l="26" _o-e="26,68" _o-tl="-1" _o-s="26,65" _o-cl="65" id="29824831">,</code>, charset
and headers names if your CSV is missing them</p>

<code _o="796" _o-sc="32,0" _o-l="31" _o-e="38,3" _o-tl="-1" _o-s="31,0" style="block" _o-cl="0" id="4ab083f" lang="kotlin">val df = DataFrame.readCSV(
    file,
    delimiter = '|',
    headers = listOf("A", "B", "C", "D"),
    parserOptions = ParserOptions(nulls = setOf("not assigned"))
)
</code>

<p _o="992" _o-sc="42,0" _o-l="42" _o-e="44,0" _o-tl="-1" _o-s="42,0" _o-cl="0" id="ae6ee3de">Column types will be inferred from the actual CSV data. Suppose that CSV from the previous
example had the following content:</p>
<table _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="1f925334">
<tr _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="623b90d2"><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="7f13968e">A</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="5700bfea">B</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="daa1bc7c">C</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="b4e01c9f">D</td></tr>
<tr _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="beb99a51"><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="2585d5f8">12</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="8afa6eef">tuv</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="cc953d95">0.12</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="79bdb2ae">true</td></tr>
<tr _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="a6d83406"><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="6d76b283">41</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="6f3a1f01">xyz</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="51546c30">3.6</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="6e810d41">not assigned</td></tr>
<tr _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="73fb17c9"><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="22b0050e">89</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="f184acb">abc</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="9b5695bb">7.1</td><td _o="1119" _o-sc="45,7" _o-l="45" _o-e="51,0" _o-tl="6" _o-s="45,0" _o-cl="0" id="3200bb96">false</td></tr>
</table>
<p _o="1371" _o-sc="52,0" _o-l="52" _o-e="53,0" _o-tl="-1" _o-s="52,0" _o-cl="0" id="afae719f">Dataframe schema we get is:</p>
<code _o="1400" _o-sc="55,0" _o-l="54" _o-e="59,3" _o-tl="-1" _o-s="54,0" style="block" _o-cl="0" id="bde3f01c" lang="text">A: Int
B: String
C: Double
D: Boolean?
</code>
</chapter><chapter _o="1452" _o-sc="61,4" _o-l="61" _o-e="61,16" _o-tl="-1" _o-s="61,0" _o-cl="0" id="reading-json" title="Reading JSON">
<p _o="1469" _o-sc="62,0" _o-l="62" _o-e="63,0" _o-tl="-1" _o-s="62,0" _o-cl="0" id="a96f655a">Basics for reading JSONs are the same: you can read from file or from remote URL.</p>
<code _o="1552" _o-sc="65,0" _o-l="64" _o-e="66,3" _o-tl="-1" _o-s="64,0" style="block" _o-cl="0" id="bd0da0e6" lang="kotlin">DataFrame.readJson("https://covid.ourworldindata.org/data/owid-covid-data.json")
</code>
<p _o="1648" _o-sc="68,0" _o-l="68" _o-e="70,0" _o-tl="-1" _o-s="68,0" _o-cl="0" id="6bf4425e">Note that after reading a JSON with a complex structure, you can get hierarchical
dataframe: dataframe with <code _o="1756" _o-sc="69,27" _o-l="69" _o-e="69,39" _o-tl="-1" _o-s="69,26" _o-cl="26" id="7431e1f4">GroupColumn</code>s and <code _o="1775" _o-sc="69,46" _o-l="69" _o-e="69,58" _o-tl="-1" _o-s="69,45" _o-cl="45" id="22f49613">FrameColumn</code>s.</p>
<p _o="1792" _o-sc="71,0" _o-l="71" _o-e="74,0" _o-tl="-1" _o-s="71,0" _o-cl="0" id="ad3e44fe">Also note that type inferring process for JSON is much simpler than for CSV.
JSON string literals are always supposed to have String type, number literals
take different <code _o="1962" _o-sc="73,16" _o-l="73" _o-e="73,23" _o-tl="-1" _o-s="73,15" _o-cl="15" id="d9241c15">Number</code> kinds, boolean literals are converted to <code _o="2012" _o-sc="73,66" _o-l="73" _o-e="73,74" _o-tl="-1" _o-s="73,65" _o-cl="65" id="c9d3b517">Boolean</code>.</p>
<p _o="2024" _o-sc="75,0" _o-l="75" _o-e="76,0" _o-tl="-1" _o-s="75,0" _o-cl="0" id="b43b1158">Let's take a look at the following JSON:</p>
<code _o="2066" _o-sc="78,0" _o-l="77" _o-e="84,3" _o-tl="-1" _o-s="77,0" style="block" _o-cl="0" id="6691d1d0" lang="json">[
  { "A": "1", "B": 1, "C": 1.0, "D": true },
  { "A": "2", "B": 2, "C": 1.1, "D": null },
  { "A": "3", "B": 3, "C": 1, "D": false },
  { "A": "4", "B": 4, "C": 1.3, "D": true }
]
</code>
<p _o="2261" _o-sc="86,0" _o-l="86" _o-e="87,0" _o-tl="-1" _o-s="86,0" _o-cl="0" id="7babb73c">We can read it from file</p>

<code _o="2309" _o-sc="91,0" _o-l="90" _o-e="92,3" _o-tl="-1" _o-s="90,0" style="block" _o-cl="0" id="17aaa040" lang="kotlin">val df = DataFrame.readJson(file)
</code>

<p _o="2371" _o-sc="96,0" _o-l="96" _o-e="97,0" _o-tl="-1" _o-s="96,0" _o-cl="0" id="211fc0ce">Corresponding dataframe schema will be</p>
<code _o="2411" _o-sc="99,0" _o-l="98" _o-e="103,3" _o-tl="-1" _o-s="98,0" style="block" _o-cl="0" id="62dc92a2" lang="text">A: String
B: Int
C: Number
D: Boolean?
</code>
<p _o="2463" _o-sc="105,0" _o-l="105" _o-e="106,0" _o-tl="-1" _o-s="105,0" _o-cl="0" id="eafae1d2">Column A has <code _o="2476" _o-sc="105,14" _o-l="105" _o-e="105,21" _o-tl="-1" _o-s="105,13" _o-cl="13" id="5227bb68">String</code> type because all values are string literals, no implicit conversion is performed. Column C has <code _o="2580" _o-sc="105,118" _o-l="105" _o-e="105,125" _o-tl="-1" _o-s="105,117" _o-cl="117" id="d1299643">Number</code> type because it's the least common type for <code _o="2633" _o-sc="105,171" _o-l="105" _o-e="105,175" _o-tl="-1" _o-s="105,170" _o-cl="170" id="5c5a8ef0">Int</code> and <code _o="2643" _o-sc="105,181" _o-l="105" _o-e="105,188" _o-tl="-1" _o-s="105,180" _o-cl="180" id="2b484a70">Double</code>.</p>
</chapter></topic>