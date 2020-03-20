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
<p>{%  highlight  javascript %}<br>
function factorialize(num) {<br>
if (num === 0) {<br>
return 1;<br>
}<br>
return num * factorialize(num - 1);<br>
}</p>
<p>factorialize(5);<br>
{%  endhighlight  %}</p>
<p>Same problem using <strong>tail recusion</strong>.<br>
{%  highlight  javascript %}<br>
function factorialize(num, factorial = 1) {<br>
if (num == 0) {<br>
return factorial;<br>
} else {<br>
return factorialize(num - 1, factorial * num);<br>
}<br>
}</p>
<p>factorialize(5);<br>
{%  endhighlight  %}<br>
<strong>Check <code>typeof()</code> value</strong><br>
{%  highlight  javascript %}<br>
function  booWho(bool) {<br>
if (typeof(bool) === “boolean”) {<br>
return  true;<br>
} else {<br>
return  false;<br>
}<br>
}<br>
booWho(null);<br>
{%  endhighlight  %}<br>
<strong>Converting string to sentence case</strong><br>
Again, rewritten a number of different ways. Originally tried a regex pattern with <code>replace()</code> but couldn’t figure out how to get the callback function to return the right value.</p>
<p>This solution uses <code>map()</code>, <code>split()</code> and <code>replace()</code>.<br>
{%  highlight  javascript %}<br>
function  titleCase(str) {<br>
let  newArray = str.toLowerCase().split(" ");<br>
// console.log(newArray);</p>
<pre><code>let  result = newArray.map(function(val) {
// console.log(val.replace(val.charAt(0), val.charAt(0).toUpperCase()));
	return  console.log(val.replace(val.charAt(0), val.charAt(0).toUpperCase()));
})
console.log(result.join(" "));
</code></pre>
<p>}<br>
titleCase(“I’m a little tea pot”);<br>
{%  endhighlight  %}<br>
<strong>Edit</strong>: found a solution using a <strong>regex</strong> pattern, which looks a lot easier.</p>
<p>{%  highlight  javascript %}<br>
function titleCase(str) {<br>
return str.toLowerCase().replace(/(^|\s)\S/g, L =&gt; 	L.toUpperCase());<br>
}<br>
{%  endhighlight  %}</p>

