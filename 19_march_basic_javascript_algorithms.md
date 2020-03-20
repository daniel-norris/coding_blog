---


---

<h2 id="basic-javascript-algorithms">Basic JavaScript algorithms</h2>
<h6 id="daniel-norris-20-march-2020"><a href="https://github.com/daniel-norris">Daniel Norris</a>, 20 March 2020</h6>
<h6 id="home--basic-javascript-algorithms"><a href="./">Home</a> &gt; Basic JavaScript algorithms</h6>
<br> 
<p>I’ve been working through a lot of basic JavaScript algorithms - some of which were useful problems to keep a note of for future reference.</p>
<p>I need to come back to this as it’s helped to identify weaknesses I have around my ability to refactor using different approaches, e.g. recursion, reduce, map, etc.</p>
<p><strong>Reverse a string</strong></p>
<pre class=" language-json"><code class="prism  language-json"><span class="token keyword">function</span>  <span class="token function">reverseString</span><span class="token punctuation">(</span>str<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">let</span>  newArr <span class="token operator">=</span> str<span class="token punctuation">.</span><span class="token function">split</span><span class="token punctuation">(</span><span class="token string">""</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>newArr<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">let</span>  revArr <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span>  i <span class="token operator">=</span> newArr<span class="token punctuation">.</span>length <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">;</span> i<span class="token operator">--</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		revArr<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span>newArr<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>revArr<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token keyword">return</span>  revArr<span class="token punctuation">.</span><span class="token function">join</span><span class="token punctuation">(</span><span class="token string">""</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token function">reverseString</span><span class="token punctuation">(</span><span class="token string">"hello"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Factorialise a number</strong><br>
Using recusion here. This can be rewritten a number of different ways, e.g. <strong>tail recursion</strong>, <strong>for</strong> statement and <code>reduce()</code>.</p>
<p>Explanation on recursion <a href="https://www.youtube.com/watch?v=k7-N8R0-KY4">here</a>.</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span> <span class="token function">factorialize</span><span class="token punctuation">(</span>num<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span>num <span class="token operator">===</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> <span class="token number">1</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> num <span class="token operator">*</span> <span class="token function">factorialize</span><span class="token punctuation">(</span>num <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token function">factorialize</span><span class="token punctuation">(</span><span class="token number">5</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>Same problem using <strong>tail recusion</strong>.</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span> <span class="token function">factorialize</span><span class="token punctuation">(</span>num<span class="token punctuation">,</span> factorial <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span>num <span class="token operator">==</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> factorial<span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span> <span class="token function">factorialize</span><span class="token punctuation">(</span>num <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">,</span> factorial <span class="token operator">*</span> num<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>

<span class="token function">factorialize</span><span class="token punctuation">(</span><span class="token number">5</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Check <em>typeof</em> value</strong></p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span>  <span class="token function">booWho</span><span class="token punctuation">(</span>bool<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token keyword">typeof</span><span class="token punctuation">(</span>bool<span class="token punctuation">)</span> <span class="token operator">===</span> <span class="token string">"boolean"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span>  <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		<span class="token keyword">return</span>  <span class="token boolean">false</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token function">booWho</span><span class="token punctuation">(</span><span class="token keyword">null</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Converting string to sentence case</strong><br>
Again, rewritten a number of different ways. Originally tried a regex pattern with <code>replace()</code> but couldn’t figure out how to get the callback function to return the right value.</p>
<p>This solution uses <code>map()</code>, <code>split()</code> and <code>replace()</code>.</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span>  <span class="token function">titleCase</span><span class="token punctuation">(</span>str<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">let</span>  newArray <span class="token operator">=</span> str<span class="token punctuation">.</span><span class="token function">toLowerCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">split</span><span class="token punctuation">(</span><span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token comment">// console.log(newArray);</span>

	<span class="token keyword">let</span>  result <span class="token operator">=</span> newArray<span class="token punctuation">.</span><span class="token function">map</span><span class="token punctuation">(</span><span class="token keyword">function</span><span class="token punctuation">(</span>val<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">// console.log(val.replace(val.charAt(0), val.charAt(0).toUpperCase()));</span>
		<span class="token keyword">return</span>  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>val<span class="token punctuation">.</span><span class="token function">replace</span><span class="token punctuation">(</span>val<span class="token punctuation">.</span><span class="token function">charAt</span><span class="token punctuation">(</span><span class="token number">0</span><span class="token punctuation">)</span><span class="token punctuation">,</span> val<span class="token punctuation">.</span><span class="token function">charAt</span><span class="token punctuation">(</span><span class="token number">0</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">toUpperCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span><span class="token punctuation">)</span>
	console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>result<span class="token punctuation">.</span><span class="token function">join</span><span class="token punctuation">(</span><span class="token string">" "</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token function">titleCase</span><span class="token punctuation">(</span><span class="token string">"I'm a little tea pot"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Edit</strong>: found a solution using a <strong>regex</strong> pattern, which looks a lot easier.</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span> <span class="token function">titleCase</span><span class="token punctuation">(</span>str<span class="token punctuation">)</span> <span class="token punctuation">{</span> 
	<span class="token keyword">return</span> str<span class="token punctuation">.</span><span class="token function">toLowerCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">replace</span><span class="token punctuation">(</span><span class="token regex">/(^|\s)\S/g</span><span class="token punctuation">,</span> L <span class="token operator">=&gt;</span> 	L<span class="token punctuation">.</span><span class="token function">toUpperCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span> 
<span class="token punctuation">}</span>
</code></pre>

