<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="parse" title="parse" _md-based="true"> 
<p _o="90" _o-sc="3,0" _o-l="3" _o-e="4,0" _o-tl="-1" _o-s="3,0" _o-cl="0" id="cfe71a5d">Returns <code _o="98" _o-sc="3,9" _o-l="3" _o-e="3,19" _o-tl="-1" _o-s="3,8" _o-cl="8" id="706464bb">DataFrame</code> in which given <code _o="125" _o-sc="3,36" _o-l="3" _o-e="3,43" _o-tl="-1" _o-s="3,35" _o-cl="35" id="bba46509">String</code> columns are parsed into other types.</p>
<p _o="172" _o-sc="5,0" _o-l="5" _o-e="6,0" _o-tl="-1" _o-s="5,0" _o-cl="0" id="9cf61d78">Special case of <a _o="188" _o-sc="5,17" LinkStatus="UNKNOWN" _o-l="5" _o-e="5,37" _o-tl="-1" _o-s="5,16" href="convert.md" _o-cl="16" id="5967074a">convert</a> operation.</p>

<code _o="244" _o-sc="10,0" _o-l="9" _o-e="11,3" _o-tl="-1" _o-s="9,0" style="block" _o-cl="0" id="68234325" lang="kotlin">df.parse()
</code>

<p _o="283" _o-sc="15,0" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="403c62e4">To parse only particular columns use <a _o="320" _o-sc="15,38" LinkStatus="UNKNOWN" _o-l="15" _o-e="15,74" _o-tl="-1" _o-s="15,37" href="ColumnSelectors.md" _o-cl="37" id="480292ae">column selector</a>:</p>

<code _o="383" _o-sc="20,0" _o-l="19" _o-e="21,3" _o-tl="-1" _o-s="19,0" style="block" _o-cl="0" id="e4bc33c" lang="kotlin">df.parse { age and weight }
</code>

<p _o="439" _o-sc="25,0" _o-l="25" _o-e="26,0" _o-tl="-1" _o-s="25,0" _o-cl="0" id="85b8cc51"><code _o="439" _o-sc="25,1" _o-l="25" _o-e="25,7" _o-tl="-1" _o-s="25,0" _o-cl="0" id="50c4f0f8">parse</code> tries to parse every<code _o="467" _o-sc="25,29" _o-l="25" _o-e="25,36" _o-tl="-1" _o-s="25,28" _o-cl="28" id="7ef94667">String</code> column into one of supported types in the following order:</p>
<list _o="535" _o-sc="26,0" _o-l="26" _o-e="35,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="a9f8104a">
<li _o="535" _o-sc="26,2" _o-l="26" _o-e="27,0" _o-tl="-1" _o-s="26,0" _o-cl="0" id="71f09620"><code _o="537" _o-sc="26,3" _o-l="26" _o-e="26,7" _o-tl="-1" _o-s="26,2" _o-cl="2" id="1c69266e">Int</code></li>
<li _o="543" _o-sc="27,2" _o-l="27" _o-e="28,0" _o-tl="-1" _o-s="27,0" _o-cl="0" id="5c7cbc55"><code _o="545" _o-sc="27,3" _o-l="27" _o-e="27,8" _o-tl="-1" _o-s="27,2" _o-cl="2" id="2b5616c">Long</code></li>
<li _o="552" _o-sc="28,2" _o-l="28" _o-e="29,0" _o-tl="-1" _o-s="28,0" _o-cl="0" id="b7f22cd"><code _o="554" _o-sc="28,3" _o-l="28" _o-e="28,11" _o-tl="-1" _o-s="28,2" _o-cl="2" id="ae46e2c4">Boolean</code></li>
<li _o="564" _o-sc="29,2" _o-l="29" _o-e="30,0" _o-tl="-1" _o-s="29,0" _o-cl="0" id="bf57ab83"><code _o="566" _o-sc="29,3" _o-l="29" _o-e="29,14" _o-tl="-1" _o-s="29,2" _o-cl="2" id="d973bf0c">BigDecimal</code></li>
<li _o="579" _o-sc="30,2" _o-l="30" _o-e="31,0" _o-tl="-1" _o-s="30,0" _o-cl="0" id="5c17dd93"><code _o="581" _o-sc="30,3" _o-l="30" _o-e="30,13" _o-tl="-1" _o-s="30,2" _o-cl="2" id="98936cf9">LocalDate</code></li>
<li _o="593" _o-sc="31,2" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="248a9354"><code _o="595" _o-sc="31,3" _o-l="31" _o-e="31,17" _o-tl="-1" _o-s="31,2" _o-cl="2" id="704f6c4d">LocalDateTime</code></li>
<li _o="611" _o-sc="32,2" _o-l="32" _o-e="33,0" _o-tl="-1" _o-s="32,0" _o-cl="0" id="1703cb3f"><code _o="613" _o-sc="32,3" _o-l="32" _o-e="32,13" _o-tl="-1" _o-s="32,2" _o-cl="2" id="8de8eb88">LocalTime</code></li>
<li _o="625" _o-sc="33,2" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="9001f0a2"><code _o="627" _o-sc="33,3" _o-l="33" _o-e="33,7" _o-tl="-1" _o-s="33,2" _o-cl="2" id="8cce9e62">URL</code></li>
<li _o="633" _o-sc="34,2" _o-l="34" _o-e="35,0" _o-tl="-1" _o-s="34,0" _o-cl="0" id="e6c819ae"><code _o="635" _o-sc="34,3" _o-l="34" _o-e="34,10" _o-tl="-1" _o-s="34,2" _o-cl="2" id="c4de9a5d">Double</code></li>
</list>
<p _o="645" _o-sc="36,0" _o-l="36" _o-e="37,0" _o-tl="-1" _o-s="36,0" _o-cl="0" id="30ed552c">Available parser options:</p>
<list _o="671" _o-sc="37,0" _o-l="37" _o-e="40,0" _o-tl="137" _o-s="37,0" _o-cl="0" id="c19cbf9a">
<li _o="671" _o-sc="37,2" _o-l="37" _o-e="38,0" _o-tl="-1" _o-s="37,0" _o-cl="0" id="9a09ba6e"><code _o="673" _o-sc="37,3" _o-l="37" _o-e="37,18" _o-tl="-1" _o-s="37,2" _o-cl="2" id="6b5383f8">locale: Locale</code> is used to parse numbers</li>
<li _o="715" _o-sc="38,2" _o-l="38" _o-e="39,0" _o-tl="-1" _o-s="38,0" _o-cl="0" id="90b0b893"><code _o="717" _o-sc="38,3" _o-l="38" _o-e="38,40" _o-tl="-1" _o-s="38,2" _o-cl="2" id="6bfbee3f">dateTimeFormatter: DateTimeFormatter</code> is used to parse date and time</li>
<li _o="787" _o-sc="39,2" _o-l="39" _o-e="40,0" _o-tl="21" _o-s="39,0" _o-cl="0" id="869db24b"><code _o="789" _o-sc="39,3" _o-l="39" _o-e="39,23" _o-tl="19" _o-s="39,2" _o-cl="2" id="a8b857ce">nulls: List&lt;String></code> is used to treat particular strings as <code _o="850" _o-sc="39,64" _o-l="39" _o-e="39,69" _o-tl="-1" _o-s="39,63" _o-cl="63" id="1d653a78">null</code> value. Default <code _o="872" _o-sc="39,86" _o-l="39" _o-e="39,91" _o-tl="-1" _o-s="39,85" _o-cl="85" id="9af5fb89">null</code> strings: <code _o="888" _o-sc="39,102" _o-l="39" _o-e="39,109" _o-tl="-1" _o-s="39,101" _o-cl="101" id="ecc3d6fc">"null"</code> and <code _o="901" _o-sc="39,115" _o-l="39" _o-e="39,122" _o-tl="-1" _o-s="39,114" _o-cl="114" id="ae01888b">"NULL"</code></li>
</list>

<code _o="941" _o-sc="44,0" _o-l="43" _o-e="45,3" _o-tl="-1" _o-s="43,0" style="block" _o-cl="0" id="e2735861" lang="kotlin">df.parse(options = ParserOptions(locale = Locale.CHINA, dateTimeFormatter = DateTimeFormatter.ISO_WEEK_DATE))
</code>

<p _o="1079" _o-sc="49,0" _o-l="49" _o-e="50,0" _o-tl="-1" _o-s="49,0" _o-cl="0" id="83241045">You can also set global parser options that will be used by default in <a _o="1150" _o-sc="49,72" LinkStatus="UNKNOWN" _o-l="49" _o-e="49,88" _o-tl="-1" _o-s="49,71" href="read.md" _o-cl="71" id="52fc4202"><code _o="1151" _o-sc="49,73" _o-l="49" _o-e="49,78" _o-tl="-1" _o-s="49,72" _o-cl="72" id="73d01420">read</code></a>, <a _o="1169" _o-sc="49,91" LinkStatus="UNKNOWN" _o-l="49" _o-e="49,113" _o-tl="-1" _o-s="49,90" href="convert.md" _o-cl="90" id="5448dd5c"><code _o="1170" _o-sc="49,92" _o-l="49" _o-e="49,100" _o-tl="-1" _o-s="49,91" _o-cl="91" id="586a09cb">convert</code></a> and <code _o="1197" _o-sc="49,119" _o-l="49" _o-e="49,125" _o-tl="-1" _o-s="49,118" _o-cl="118" id="6981ff78">parse</code> operations:</p>

<code _o="1251" _o-sc="54,0" _o-l="53" _o-e="56,3" _o-tl="-1" _o-s="53,0" style="block" _o-cl="0" id="8e6bd48" lang="kotlin">DataFrame.parser.locale = Locale.FRANCE
DataFrame.parser.addDateTimeFormat("dd.MM.uuuu HH:mm:ss")
</code>

</topic>