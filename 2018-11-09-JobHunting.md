---


---

<hr>
<h2 id="layout-----posttitle------ds-question-collection-ab-testsubtitle---failue-doesnt-deafeat-youdate-------2018-11-09author----chesterheader-img-imgfailure.jpgcatalog-truetags--job">layout:     post<br>
title:      DS Question Collection-A/B Test<br>
subtitle:   Failue doesn’t deafeat you<br>
date:       2018-11-09<br>
author:    Chester<br>
header-img: img/failure.jpg<br>
catalog: true<br>
tags:<br>
- Job</h2>
<h1 id="ab-testing--interview-question">A/B testing &amp; Interview Question</h1>
<p>Here’s some collection on forum. All the code can be found at my <a href="https://github.com/ChesterHsieh/DSTechNote">github repository</a>.</p>
<h2 id="terminology">Terminology</h2>
<h4 id="is-significant-level">is significant level?</h4>
<h4 id="whats-p-value">What’s P-value?</h4>
<p><a href="https://onlinecourses.science.psu.edu/statprogram/reviews/statistical-concepts/hypothesis-testing/p-value-approach">P-value best explained with example</a><br>
Single sentence explain:<br>
The p-value is the probability of observing a value as or more extreme than the one observed under the Null Hypothesis.</p>
<h4 id="what-is-power">What is power?</h4>
<p><img src="https://github.com/ChesterHsieh/ChesterHsieh.github.io/img/power.png" alt="Power!"></p>
<h4 id="what-is-a-confidence-interval-and-how-do-you-interpret-it">What is a confidence interval and how do you interpret it?</h4>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">def</span> <span class="token function">get_ci</span><span class="token punctuation">(</span>value<span class="token punctuation">,</span> cl<span class="token punctuation">,</span> sd<span class="token punctuation">)</span><span class="token punctuation">:</span>
    loc <span class="token operator">=</span> stats<span class="token punctuation">.</span>norm<span class="token punctuation">.</span>ppf<span class="token punctuation">(</span><span class="token number">1</span> <span class="token operator">-</span> cl<span class="token operator">/</span><span class="token number">2</span><span class="token punctuation">)</span>
    rng_val <span class="token operator">=</span> sci<span class="token punctuation">.</span>norm<span class="token punctuation">.</span>cdf<span class="token punctuation">(</span>loc <span class="token operator">-</span> value<span class="token operator">/</span>sd<span class="token punctuation">)</span>

    lwr_bnd <span class="token operator">=</span> value <span class="token operator">-</span> rng_val
    upr_bnd <span class="token operator">=</span> value <span class="token operator">+</span> rng_val 

    return_val <span class="token operator">=</span> <span class="token punctuation">(</span>lwr_bnd<span class="token punctuation">,</span> upr_bnd<span class="token punctuation">)</span>
    <span class="token keyword">return</span><span class="token punctuation">(</span>return_val<span class="token punctuation">)</span>
</code></pre>
<h4 id="what’s-the-difference-between-a-map-mom-mle-estima-tor-in-which-cases-would-you-want-to-use-each">What’s the difference between a MAP, MOM, MLE estima-tor? In which cases would you want to use each?</h4>
<h2 id="special-case">Special Case</h2>
<h4 id="too-many-variants">Too Many Variants?</h4>
<p>I need to aware of the # of variants might have different effect on overall test.<br>
First number we need to aware of is <a href="http://web.pdx.edu/~newsomj/da1/ho_posthoc.pdf">“cumulative alpha error”</a><br>
There’s an inequality formula using two idea:<br>
n := # of variants</p>
<ol>
<li>Familywise error (FWE)<br>
<img src="http://www.sciweavers.org/tex2img.php?eq=%20%20%20%5Calpha_%7BFWE%7D%20%20%3D%201%20-%281-%5Calpha_%7BEC%7D%29%5En&amp;bc=White&amp;fc=Black&amp;im=jpg&amp;fs=12&amp;ff=arev&amp;edit=0" alt="Formula"></li>
<li>Bonferroni correction<br>
<img src="http://www.sciweavers.org/tex2img.php?eq=%20%20%20%5Calpha_%7BB%7D%20%3D%20%20%20%20%5Calpha_%7BFWE%7D%2F%20n%20&amp;bc=White&amp;fc=Black&amp;im=jpg&amp;fs=12&amp;ff=arev&amp;edit=0" alt="Formula"></li>
</ol>
<p>Actually significant level should between these 2 number. It vary by the dependence of different variants.</p>
<h4 id="what-would-be-the-hazards-of-letting-users-sneak-a-peek-at-the-other-bucket-in-an-ab-test">What would be the hazards of letting users sneak a peek at the other bucket in an A/B test?</h4>
<p><img src="http://www.sciweavers.org/tex2img.php?eq=%20t%3D%7B%5Cfrac%20%7B%7B%5Cbar%20%7Bx%7D%7D-%5Cmu%20_%7B0%7D%7D%7B%5Cfrac%20%7Bs%7D%7B%5Csqrt%20%7Bn%7D%7D%7D%7D%7D&amp;bc=White&amp;fc=Black&amp;im=jpg&amp;fs=12&amp;ff=arev&amp;edit=0" alt=""></p>
<h4 id="in-an-ab-test-how-can-you-check-if-assignment-to-the-various-buckets-was-truly-random">In an A/B test, how can you check if assignment to the various buckets was truly random?</h4>
<p>It’s almost impossible to test randomness on statstic. However we can do another trial. We can try to test equivalence for the A/B two part. That’s some time we call** A/A test**.</p>
<p>Here’s an example to show how A/A test going.</p>
<h4 id="how-would-you-run-an-ab-test-if-the-observations-are-extremely-right-skewed">How would you run an A/B test if the observations are extremely right-skewed?</h4>
<ol>
<li>Lower the variability of your metric.<br>
Say you’re looking at revenue for a retail site (my experience is from Amazon) or revenue from clicks (my experience is from Bing ads). Both have a large mass at $0 (most people don’t purchase or click on ads), and a long right tail.<br>
Instead of revenue, look at two metrics: an indicator for conversion (yes/no), and the conditional (revenue if purchased; null otherwise).<br>
Each of two will have lower variance, thus give more signal for A/B testing.<br>
Their product is revenue.</li>
<li>Cap values.<br>
Here I would caution you to understand the reasons for the skew.<br>
For example, if you’re looking at time on site, you might find a very right-skewed metrics, but also lumpiness. For example, mass around 1440 minutes may mean users visited your site again the day after about the same time. Assuming that’s not your intention, capping time on site to 30 minutes is a common strategy.<br>
At Amazon, we found significant outliers to revenue and number of items purchased. After looking at the details, it turned out these were libraries or purchasing departments. If one of the treatments gets a couple of more libraries than another, it could skew the results.<br>
Capping at a certain dollar values and items purchased lowered the variance (and improved trustworthiness).</li>
<li>Look at percentile metrics or trimmed means.<br>
For example, time-to-X (time-to-onload event for page-load, time-to-click) tends to have a lot right-skew. Instead of the mean, look at some percentile, such as 90th.</li>
</ol>
<h2 id="design-problem">Design Problem</h2>
<p>Here’s real problem I’ve enconterd and failed like idot.</p>
<blockquote>
<p>Assume we are the a platform provide the suggestion on Cloth style<br>
There are two color we need to decide whtich one is better?<br>
That’s say we can only test 1000 time, how you design the experiment??</p>
</blockquote>
<p><img src="https://conversionxl.com/wp-content/uploads/2016/06/1.png" alt="Desgin Process"></p>
<h4 id="radomize">Radomize</h4>
<h4 id="minimum-test-size">minimum test size</h4>
<h2 id="refernce">Refernce</h2>
<p>Strongly recommend to read These as source:</p>
<p><a href="https://conversionxl.com/blog/testing-statistics-mistakes/">10 Statistics Traps in A/B Testing: The Ultimate Guide for Optimizers</a></p>
<p><a href="https://conversionsciences.com/blog/aa-test-gives-you-confidence/">What is an A/A Test</a></p>
<p><a href="https://towardsdatascience.com/the-math-behind-a-b-testing-with-example-code-part-1-of-2-7be752e1d06f">The Math behind A/B Testing</a></p>

