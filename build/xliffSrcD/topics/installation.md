<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="installation" title="Installation" _md-based="true"> <p _o="31" _o-sc="2,0" _o-l="2" _o-e="4,0" _o-tl="-1" _o-s="2,0" _o-cl="0" id="182a6869">You can use DataFrame in different environments - as any other JVM library.
The following sections will show how to use DataFrame in <a _o="164" _o-sc="3,58" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,85" anchor="jupyter-notebook" _o-tl="-1" _o-s="3,57" _o-cl="57" id="4812f12b">Jupyter</a>, <a _o="194" _o-sc="3,88" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,108" anchor="datalore" _o-tl="-1" _o-s="3,87" _o-cl="87" id="25674574">Datalore</a> and in a <a _o="225" _o-sc="3,119" LinkStatus="UNKNOWN" _o-l="3" _o-e="3,143" anchor="gradle" _o-tl="-1" _o-s="3,118" _o-cl="118" id="4ea38884">Gradle project</a>.</p>
<chapter _o="253" _o-sc="5,3" _o-l="5" _o-e="5,19" _o-tl="-1" _o-s="5,0" _o-cl="0" id="jupyter-notebook" title="Jupyter Notebook">
<p _o="274" _o-sc="7,0" _o-l="7" _o-e="10,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="66c34795">You can use DataFrame in Jupyter Notebook and in Jupyter Lab.
To start, install the latest version of <a _o="376" _o-sc="8,41" LinkStatus="UNKNOWN" _o-l="8" _o-e="8,110" _o-tl="-1" _o-s="8,40" href="https://github.com/Kotlin/kotlin-jupyter#installation" _o-cl="40" id="aa2b30bc">Kotlin kernel</a> and start your favorite Jupyter client from
the command line, for example:</p>
<code _o="523" _o-sc="12,0" _o-l="11" _o-e="13,3" _o-tl="-1" _o-s="11,0" style="block" _o-cl="0" id="9e862bd4" lang="shell">jupyter notebook
</code>
<p _o="554" _o-sc="15,0" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="2f5ca2e0">In the notebook you only have to write single line to start using dataframe:</p>
<code _o="632" _o-sc="18,0" _o-l="17" _o-e="19,3" _o-tl="-1" _o-s="17,0" style="block" _o-cl="0" id="5c878f38" lang="text">%use dataframe
</code>
<p _o="660" _o-sc="21,0" _o-l="21" _o-e="23,0" _o-tl="-1" _o-s="21,0" _o-cl="0" id="f4170a01">In this case the version which is bundled with the kernel, will be used.
If you want to always use the latest version, add another magic before <code _o="804" _o-sc="22,72" _o-l="22" _o-e="22,87" _o-tl="-1" _o-s="22,71" _o-cl="71" id="6c621acb">%use dataframe</code>:</p>
<code _o="823" _o-sc="25,0" _o-l="24" _o-e="27,3" _o-tl="-1" _o-s="24,0" style="block" _o-cl="0" id="d3ffd3fd" lang="text">%useLatestDescriptors
%use dataframe
</code>
<p _o="873" _o-sc="29,0" _o-l="29" _o-e="30,0" _o-tl="-1" _o-s="29,0" _o-cl="0" id="1829e8f4">If you want to use specific version of DataFrame, you can specify it in brackets:</p>
<code _o="956" _o-sc="32,0" _o-l="31" _o-e="33,3" _o-tl="-1" _o-s="31,0" style="block" _o-cl="0" id="7a4d7820" lang="text">%use dataframe(0.9)
</code>
<p _o="989" _o-sc="35,0" _o-l="35" _o-e="36,0" _o-tl="-1" _o-s="35,0" _o-cl="0" id="7ccdc11d">After loading, all essential types will be already imported, so you can start using DataFrame. Enjoy!</p>
</chapter><chapter _o="1092" _o-sc="37,3" _o-l="37" _o-e="37,11" _o-tl="-1" _o-s="37,0" _o-cl="0" id="datalore" title="Datalore">
<p _o="1105" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="472110d7">To start with DataFrame in Datalore, create a Kotlin notebook first:</p>
<img _o-sc="41,2" LinkStatus="UNKNOWN" _o-l="41" _o-e="41,43" src="datalore-1.png" alt="Installation to Datalore" _o-cl="0" _o="1175" _o-tl="-1" _o-s="41,0" id="7949114f"/>
<p _o="1220" _o-sc="43,0" _o-l="43" _o-e="44,0" _o-tl="-1" _o-s="43,0" _o-cl="0" id="c2935afc">As the Notebook you've created is actually a Jupyter notebook, you can follow the instructions in the <a _o="1322" _o-sc="43,103" LinkStatus="UNKNOWN" _o-l="43" _o-e="43,139" anchor="jupyter-notebook" _o-tl="-1" _o-s="43,102" _o-cl="102" id="f33f399e">previous section</a> to turn DataFrame on. The simplest way of doing this is shown on screenshot:</p>
<img _o-sc="45,2" LinkStatus="UNKNOWN" _o-l="45" _o-e="45,36" src="datalore-2.png" alt="Datalore notebook" _o-cl="0" _o="1438" _o-tl="-1" _o-s="45,0" id="af2e848c"/>
</chapter><chapter _o="1476" _o-sc="47,3" _o-l="47" _o-e="47,9" _o-tl="-1" _o-s="47,0" _o-cl="0" id="gradle" title="Gradle">
<p _o="1487" _o-sc="49,0" _o-l="49" _o-e="51,0" _o-tl="-1" _o-s="49,0" _o-cl="0" id="865be39f">DataFrame is published to Maven Central, so you can simply add the following line to your Kotlin DSL
buildscript to depend on it:</p>
<code _o="1618" _o-sc="53,0" _o-l="52" _o-e="56,3" _o-tl="85" _o-s="52,0" style="block" _o-cl="0" id="8a02fdc8" lang="kotlin">dependencies {
    implementation("org.jetbrains.kotlinx:dataframe:&lt;version>")
}
</code>
<p _o="1714" _o-sc="58,0" _o-l="58" _o-e="59,0" _o-tl="-1" _o-s="58,0" _o-cl="0" id="e55d503d">In Groovy DSL buildscript setup is very similar:</p>
<code _o="1763" _o-sc="60,0" _o-l="59" _o-e="63,3" _o-tl="85" _o-s="59,0" style="block" _o-cl="0" id="9a488b0b" lang="groovy">dependencies {
    implementation 'org.jetbrains.kotlinx:dataframe:&lt;version>'
}
</code>
<chapter _o="1858" _o-sc="65,4" _o-l="65" _o-e="65,31" _o-tl="-1" _o-s="65,0" _o-cl="0" id="gradle-plugin-configuration" title="Gradle plugin configuration">
<p _o="1891" _o-sc="67,0" _o-l="67" _o-e="70,0" _o-tl="-1" _o-s="67,0" _o-cl="0" id="f8d4d0ab">We provide a Gradle plugin that generates interfaces by your data.
To use it in your project, pick up the latest version from <a _o="2017" _o-sc="68,60" LinkStatus="UNKNOWN" _o-l="68" _o-e="68,138" _o-tl="-1" _o-s="68,59" href="https://plugins.gradle.org/plugin/org.jetbrains.kotlin.plugin.dataframe" _o-cl="59" id="e3ecf2dd">here</a>
and declare plugin dependency in the <code _o="2134" _o-sc="69,38" _o-l="69" _o-e="69,46" _o-tl="-1" _o-s="69,37" _o-cl="37" id="5ad9344">plugins</code> block:</p>
<code _o="2151" _o-sc="71,0" _o-l="70" _o-e="74,3" _o-tl="82" _o-s="70,0" style="block" _o-cl="0" id="f092230c" lang="groovy">plugins {
  id "org.jetbrains.kotlin.plugin.dataframe" version "&lt;version>"
}
</code>
<p _o="2243" _o-sc="76,0" _o-l="76" _o-e="77,0" _o-tl="-1" _o-s="76,0" _o-cl="0" id="54b39b92">Note that it's better to use the same version for a library and plugin to avoid unpredictable errors.</p>
</chapter></chapter><chapter _o="2346" _o-sc="78,3" _o-l="78" _o-e="78,22" _o-tl="-1" _o-s="78,0" _o-cl="0" id="other-build-systems" title="Other build systems">
<p _o="2370" _o-sc="80,0" _o-l="80" _o-e="82,0" _o-tl="-1" _o-s="80,0" _o-cl="0" id="cca58ce">If you are using Maven, Ivy or Bazel to configure your build, you can still use DataFrame in your project.
Just follow the instructions for your build system on <a _o="2531" _o-sc="81,55" LinkStatus="UNKNOWN" _o-l="81" _o-e="81,150" _o-tl="-1" _o-s="81,54" href="https://search.maven.org/artifact/org.jetbrains.kotlinx/dataframe/0.8.0-dev-515/jar" _o-cl="54" id="253bb4dd">this page</a>.</p>
</chapter></topic>