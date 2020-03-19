---


---

<h2 id="basic-javascript-algorithms">Basic JavaScript algorithms</h2>
<h6 id="daniel-norris-19-march-2020"><a href="https://github.com/daniel-norris">Daniel Norris</a>, 19 March 2020</h6>
<h6 id="home--basic-javascript-algorithms"><a href="./">Home</a> &gt; Basic JavaScript algorithms</h6>
<p>Working through FreeCodeCamp’s basic JavaScript algorithms. I need to come back to this and refactor using different approaches, e.g. recursion, reduce, map, etc.</p>
<p><strong>Reverse a string</strong></p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span>  <span class="token function">reverseString</span><span class="token punctuation">(</span>str<span class="token punctuation">)</span> <span class="token punctuation">{</span>
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
Using recusion here. This can be rewritten a number of different ways, e.g. <strong>tail recursion</strong>, <strong>for</strong> statement and <strong>reduce()</strong>.</p>
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

