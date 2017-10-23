
  #统一搜索服务 ##数据检索帮助文档--根据类SQL语法查询数据## &lt; div id = &quot;wmd-preview&quot;class = &quot;wmd-preview&quot; &gt; 
  <div class="md-section-divider"></div>
  <p data-anchor-id="x9l3"></p>
  <div class="toc"> 
   <ul> 
    <li><a href="#opeansearch-支持的sql类型">opeansearch 支持的sql类型</a> 
     <ul> 
      <li> <a href="#目前opeansearch支持的分词类型"> 目前opeansearch支持的分词类型 &lt; /a&gt;</a></li>
      <a href="#目前opeansearch支持的分词类型"> </a>
      <li><a> </a><a href="#查询对比"> 查询对比 &lt; /a&gt;</a>
       <ul>
        <a> <li><a href="#说明">说明</a></li></a> 
        <li><a href="#eq-查询">EQ 查询</a> 
         <ul> 
          <li> <a href="#标准sql查询"> 标准sql查询 &lt; /a&gt;</a></li>
          <a href="#标准sql查询"> </a>
          <li><a> </a><a href="#不分词"> 不分词 &lt; /a&gt;</a></li>
          <a href="#不分词"> </a>
          <li><a> </a><a href="#模糊分词"> 模糊分词 &lt; /a&gt;</a></li>
          <a href="#模糊分词"> </a>
          <li><a> </a><a href="#拼音分词"> 拼音分词 &lt; /a&gt;</a></li>
          <a href="#拼音分词"> </a>
          <li><a> </a><a href="#ik分词"> IK分词 &lt; /a&gt;</a></li>
          <a href="#ik分词"> </a>
         </ul></li>
        <a href="#ik分词"> </a>
        <li><a> </a><a href="#like-查询"> like查询 &lt; /a&gt;</a>
         <ul>
          <a> <li><a href="#标准sql查询-1">标准sql查询</a></li></a> 
          <li><a href="#不分词-1">不分词</a></li> 
          <li><a href="#模糊分词-1">模糊分词</a></li> 
          <li><a href="#拼音分词-1">拼音分词</a></li> 
          <li><a href="#ik分词-1">IK分词</a> </li>
         </ul> </li> 
       </ul> </li> 
      <li><a href="#不等于">不等于</a></li> 
      <li><a href="#gtgteltlte">GT,GTE,LT,LTE</a></li> 
      <li><a href="#between-and">between and</a></li> 
      <li><a href="#in">in</a></li> 
      <li><a href="#is-null-is-not-null">is null is not null</a></li> 
      <li><a href="#聚合">聚合</a></li> 
      <li><a href="#minmaxavgsumcount">min,max,avg,sum,count</a></li> 
      <li><a href="#stats">stats</a></li> 
      <li><a href="#percentiles-百分比">percentiles 百分比</a> 
       <ul> 
        <li> 
         <ul> 
          <li> <a href="#根据区间聚合"> 根据区间聚合 &lt; /a&gt;</a></li>
          <a href="#根据区间聚合"> </a>
          <li><a> </a><a href="#根据时间区间聚合"> 根据时间区间聚合 &lt; /a&gt;</a></li>
          <a href="#根据时间区间聚合"> </a>
         </ul></li>
        <a href="#根据时间区间聚合"> </a>
       </ul><a href="#根据时间区间聚合"> </a></li>
      <a href="#根据时间区间聚合"> </a>
     </ul><a href="#根据时间区间聚合"> </a></li>
    <a href="#根据时间区间聚合"> </a>
   </ul>
   <a href="#根据时间区间聚合"> </a>
  </div>
  <a href="#根据时间区间聚合"> <p></p>
   <div class="md-section-divider"></div> <h1 data="" -="" anchor="" id="opeansearch-支持的sql类型"> opeansearch支持的sql类型 &lt; /h1&gt;<p data-anchor-id="xys7"><strong>目前只支持单表查询</strong> </p>
    <div class="md-section-divider"></div> </h1><h2 data="" -="" anchor="" id="目前opeansearch支持的分词类型"> 目前opeansearch支持的分词类型 &lt; /h2&gt;
    <ul data-anchor-id="sbfu"> 
     <li>不分词</li> 
     <li> 模糊分词 &lt; /li&gt; </li>
     <li>拼音分词</li> 
     <li> IK分词 &lt; /li&gt;</li>
    </ul> 
    <div class="md-section-divider"> 
    </div></h2><h2 data-anchor-id="yaz1" id="查询对比">查询对比</h2> 
   <div class="md-section-divider"></div><h3 data-anchor-id="an95" id="说明">说明</h3> 
   <ul data="" -="" anchor="" id="8mdt"> 
    <li> 如果字段都是精确查询，索引字段请选择不分词。 &lt; /li&gt; </li>
    <li>如果字段需要模糊查询，但是在某些场景下需要精确查询，查询的时候，请使用<code>字段名.raw</code> 作为条件。 &lt; /li&gt; </li>
    <li>对于分词的字段进行聚合，如<code>group by,sort</code> 等操作的时候，请使用 &lt; code &gt; 字段名.raw &lt; /code&gt;作为聚合条件</li> 
   </ul>
   <div class="md-section-divider"></div> <h3 data="" -="" anchor="" id="eq-查询"> EQ查询 &lt; /h3&gt;
    <div class="md-section-divider"></div> </h3><h4 data="" -="" anchor="" id="标准sql查询"> 标准sql查询 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="brlf"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="str">'数据检索'</span> </span></span></span></code></li> 
     </ol></pre> 
    <div class="md-section-divider"> 
    </div></h4><h4 data-anchor-id="l3a5" id="不分词">不分词</h4> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="crfx">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> </span><span class="pun">*</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;<span class="kwd">where</span> <span class="pln"> name &lt; /span&gt;<span class="pun">=</span> <span class="str"> '数据检索' &lt; /span&gt;</span></span></span></code> </li>
    </ol> </pre>
   <div class="md-section-divider"></div> <h4 data="" -="" anchor="" id="模糊分词"> 模糊分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="1ve6"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'数据检索'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="拼音分词"> 拼音分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="fg1c"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'shujujiansuo'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
      <li class="L1"><code class="language-sql"><span class="pun">--</span> <span class="pln"> </span><span class="pun">或者</span> </code></li> 
      <li class="L2"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'sjjs'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="ik分词"> IK分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="olmr"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">matchquery</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'数据检索'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h3 data="" -="" anchor="" id="like-查询"> like查询 &lt; /h3&gt;
    <div class="md-section-divider"></div> </h3><h4 data="" -="" anchor="" id="标准sql查询-1"> 标准sql查询 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="7qci"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name like </span> <span class="str"> '数据%' &lt; /span&gt;</span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="不分词-1"> 不分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="7p29"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name like </span> <span class="str"> '数据%' &lt; /span&gt;</span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="模糊分词-1"> 模糊分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="4yv0"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'数据'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="拼音分词-1"> 拼音分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="lj19"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'shuju'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
      <li class="L1"><code class="language-sql"><span class="pun">--</span> <span class="pln"> </span><span class="pun">或者</span> </code></li> 
      <li class="L2"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">term</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'sj'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="ik分词-1"> IK分词 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="8mn6"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name</span> <span class="pun">= </span><span class="pln">matchquery</span> <span class="pun"> ( &lt; /span&gt;<span class="str">'数据'</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h2 data="" -="" anchor="" id="不等于"> 不等于 &lt; /h2&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="7rhh"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> age </span> <span class="pun"> &lt; &amp; gt; &lt; /span&gt;<span class="pln"> </span> <span class="lit"> 20 &lt; /span&gt;</span></span></span></span></span></code> </li>
      <li class="L1"><code class="language-sql"></code> </li>
      <li class="L2"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> </span><span class="pun">*</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;<span class="kwd">where</span> <span class="pln"> age &lt; /span&gt;<span class="kwd">is</span> <span class="pln"> </span><span class="kwd">not</span> <span class="pln"> </span><span class="lit">20</span> </span></span></code></li> 
     </ol></pre> 
    <div class="md-section-divider"> 
    </div></h2><h2 data-anchor-id="l2yi" id="gtgteltlte">GT,GTE,LT,LTE</h2> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="kuz7">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> </span><span class="pun">*</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;<span class="kwd">where</span> <span class="pln"> age &lt; /span&gt;<span class="pun">&gt;=</span> <span class="pln"> </span><span class="lit">20</span> <span class="pln"> </span><span class="kwd">and</span> <span class="pln"> age &lt; /span&gt;<span class="pun">&lt;=</span> <span class="pln"> </span><span class="lit">30</span> </span></span></span></code></li> 
    </ol></pre> 
   <div class="md-section-divider"> 
   </div><h2 data-anchor-id="r7uh" id="between-and">between and</h2> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="7t3n">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> </span><span class="pun">*</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;<span class="kwd">where</span> <span class="pln"> age between &lt; /span&gt;<span class="lit">20</span> <span class="pln"> </span><span class="kwd">and</span> <span class="pln"> </span><span class="lit">30</span> </span></span></code></li> 
    </ol></pre> 
   <div class="md-section-divider"> 
   </div><h2 data-anchor-id="rue8" id="in">in</h2> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="clu8">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> </span><span class="pun">*</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;<span class="kwd">where</span> <span class="pln"> age &lt; /span&gt;<span class="kwd">in</span> <span class="pun"> ( &lt; /span&gt;<span class="lit">20</span> <span class="pun"> , </span><span class="lit">30</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></code> </li>
    </ol> </pre>
   <div class="md-section-divider"></div> <h2 data="" -="" anchor="" id="is-null-is-not-null"> is null is not null &lt; /h2&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="8az9"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> where &lt; /span&gt;<span class="pln"> name </span> <span class="kwd"> is &lt; /span&gt;<span class="pln"> </span> <span class="kwd"> null &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h2><h2 data="" -="" anchor="" id="聚合"> 聚合 &lt; /h2&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="nyli"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> </span> <span class="pun"> *</span><span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> <span class="kwd"> group &lt; /span&gt;<span class="pln"> </span> <span class="kwd"> by &lt; /span&gt;<span class="pln"> dept</span> </span></span></span></span></code></li> 
     </ol></pre> 
    <div class="md-section-divider"> 
    </div></h2><h2 data-anchor-id="blqh" id="minmaxavgsumcount">min,max,avg,sum,count</h2> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="5b35">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> avg &lt; /span&gt;<span class="pun">(</span> <span class="pln"> age &lt; /span&gt;<span class="pun">)</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;</span></span></span></code> </li>
    </ol> </pre>
   <div class="md-section-divider"></div> <h2 data="" -="" anchor="" id="stats"> stats &lt; /h2&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="mqkf"> 
     <ol class="linenums"> 
      <li class="L0"> <code class="language-sql"> <span class="kwd"> select &lt; /span&gt;<span class="pln"> stats</span> <span class="pun"> ( &lt; /span&gt;<span class="pln">age</span> <span class="pun"> ) &lt; /span&gt;<span class="pln"> </span> <span class="kwd"> from &lt; /span&gt;<span class="pln">  user </span> </span></span></span></span></code></li> 
     </ol></pre> 
    <div class="md-section-divider"> 
    </div></h2><h2 data-anchor-id="lyoe" id="percentiles-百分比">percentiles 百分比</h2> 
   <div class="md-section-divider"> 
   </div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ptmd">
    <ol class="linenums">
     <li class="L0"><code class="language-sql"><span class="kwd">select</span> <span class="pln"> percentiles &lt; /span&gt;<span class="pun">(</span> <span class="pln"> age &lt; /span&gt;<span class="pun">)</span> <span class="pln"> </span><span class="kwd">from</span> <span class="pln"> user &lt; /span&gt;</span></span></span></code> </li>
    </ol> </pre>
   <div class="md-section-divider"></div> <h4 data="" -="" anchor="" id="根据区间聚合"> 根据区间聚合 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="47sz"> 
     <ol class="linenums"> 
      <li class="L0"> <code> <span class="pln"> SELECT COUNT &lt; /span&gt;<span class="pun">(</span> <span class="pln"> age &lt; /span&gt;<span class="pun">)</span> <span class="pln"> bank GROUP BY range &lt; /span&gt;<span class="pun">(</span> <span class="pln"> age &lt; /span&gt;<span class="pun">,</span> <span class="pln"></span><span class="lit">20</span> <span class="pun"> ,
</span><span class="lit">25</span> <span class="pun"> ,
</span><span class="lit">30</span> <span class="pun"> ,
</span><span class="lit">35</span> <span class="pun"> ,
</span><span class="lit">40</span> <span class="pun"> ) &lt; /span&gt;</span></span></span></span></span></code> </li>
     </ol> </pre>
    <div class="md-section-divider"></div> </h4><h4 data="" -="" anchor="" id="根据时间区间聚合"> 根据时间区间聚合 &lt; /h4&gt;
    <div class="md-section-divider"></div> <pre class="prettyprint linenums prettyprinted" data="" -="" anchor="" id="llge"> 
     <ol class="linenums"> 
      <li class="L0"> <code> <span class="pln"> SELECT online online GROUP BY date_histogram &lt; /span&gt;<span class="pun">(</span> <span class="pln"> field &lt; /span&gt;<span class="pun">=</span> <span class="str"> 'insert_time' &lt; /span&gt;<span class="pun">,</span> <span class="str"> 'interval' &lt; /span&gt;<span class="pun">=</span> <span class="str"> '1d' &lt; /span&gt;<span class="pun">)</span> </span></span></span></span></span></code></li> 
     </ol></pre> /</h4></a>
