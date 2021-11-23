<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="write" title="Writing dataframes" _md-based="true"> 
<p _o="102" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="a28a9b24">DataFrames can be saved in CSV or JSON formats.</p>
<chapter _o="151" _o-sc="5,4" _o-l="5" _o-e="5,18" _o-tl="-1" _o-s="5,0" _o-cl="0" id="writing-to-csv" title="Writing to CSV">
<p _o="171" _o-sc="7,0" _o-l="7" _o-e="9,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="9efa6f47">You can write your dataframe in CSV format to file, to string or to <code _o="239" _o-sc="7,69" _o-l="7" _o-e="7,80" _o-tl="-1" _o-s="7,68" _o-cl="68" id="88af9edf">Appendable</code>
(i.e. to <code _o="261" _o-sc="8,10" _o-l="8" _o-e="8,17" _o-tl="-1" _o-s="8,9" _o-cl="9" id="24166f91">Writer</code>).</p>

<code _o="295" _o-sc="13,0" _o-l="12" _o-e="14,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="de6f689a" lang="kotlin">df.writeCSV(file)
</code>


<code _o="366" _o-sc="21,0" _o-l="20" _o-e="22,3" _o-tl="-1" _o-s="20,0" style="block" _o-cl="0" id="87b7d91a" lang="kotlin">val csvStr = df.writeCSVStr(CSVFormat.DEFAULT.withDelimiter(';').withRecordSeparator(System.lineSeparator()))
</code>

</chapter><chapter _o="504" _o-sc="26,4" _o-l="26" _o-e="26,19" _o-tl="-1" _o-s="26,0" _o-cl="0" id="writing-to-json" title="Writing to JSON">
<p _o="525" _o-sc="28,0" _o-l="28" _o-e="30,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="4e709598">You can write your dataframe in JSON format to file, to string or to <code _o="594" _o-sc="28,70" _o-l="28" _o-e="28,81" _o-tl="-1" _o-s="28,69" _o-cl="69" id="2bf71219">Appendable</code>
(i.e. to <code _o="616" _o-sc="29,10" _o-l="29" _o-e="29,17" _o-tl="-1" _o-s="29,9" _o-cl="9" id="d6541658">Writer</code>).</p>

<code _o="651" _o-sc="34,0" _o-l="33" _o-e="35,3" _o-tl="-1" _o-s="33,0" style="block" _o-cl="0" id="b6ae26a7" lang="kotlin">df.writeJson(file)
</code>


<code _o="724" _o-sc="42,0" _o-l="41" _o-e="43,3" _o-tl="-1" _o-s="41,0" style="block" _o-cl="0" id="1eca8eb" lang="kotlin">val jsonStr = df.writeJsonStr(prettyPrint = true)
</code>

</chapter></topic>