---
title: "Introducing the Chinese Workday Plugin"
url: "https://www.jenkins.io/blog/2026/03/22/introducing-chinese-workday-plugin/"
date: "2026-03-22T00:00:00+00:00"
author: "donhui"
feed_url: "https://www.jenkins.io/rss.xml"
---
<div id="preamble">
<div class="sectionbody">
<div class="paragraph">
<p>Many Jenkins jobs depend on business calendars.</p>
</div>
<div class="paragraph">
<p>For teams in China, that can be difficult to model with a simple weekday/weekend check. A weekday is not always a workday, and a weekend is not always a holiday. Chinese statutory holidays and make-up workdays change every year, so Pipeline logic often needs more than basic date rules.</p>
</div>
<div class="paragraph">
<p>The <a href="https://plugins.jenkins.io/chinese-workday/">Chinese Workday Plugin</a> was created to support that use case in Jenkins.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="what-the-plugin-provides"><a class="anchor" href="#what-the-plugin-provides">What the plugin provides</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The plugin adds Pipeline steps for Chinese workday checks:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><code>isChineseWorkday(…​)</code></p>
</li>
<li>
<p><code>isChineseHoliday(…​)</code></p>
</li>
<li>
<p><code>chineseWorkdaySupportedYears()</code></p>
</li>
</ul>
</div>
<div class="paragraph">
<p>It also lets administrators add or override calendar data in:</p>
</div>
<div class="paragraph">
<p><code>Manage Jenkins → System → Chinese Workday</code></p>
</div>
<div class="paragraph">
<p>This makes it possible to keep holiday calendar logic in one place instead of repeating it across Jenkinsfiles.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="example"><a class="anchor" href="#example">Example</h2>
<div class="sectionbody">
<div class="paragraph">
<p>One common use case is to run a stage only on a Chinese workday:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="rouge highlight nowrap"><code><span class="n">pipeline</span> <span class="o">{</span>
    <span class="n">agent</span> <span class="n">any</span>
    <span class="n">stages</span> <span class="o">{</span>
        <span class="n">stage</span><span class="o">(</span><span class="s1">'Release'</span><span class="o">)</span> <span class="o">{</span>
            <span class="n">when</span> <span class="o">{</span>
                <span class="n">expression</span> <span class="o">{</span>
                    <span class="n">isChineseWorkday</span><span class="o">()</span>
                <span class="o">}</span>
            <span class="o">}</span>
            <span class="n">steps</span> <span class="o">{</span>
                <span class="n">echo</span> <span class="s1">'Release runs only on a Chinese workday.'</span>
            <span class="o">}</span>
        <span class="o">}</span>
    <span class="o">}</span>
<span class="o">}</span></code></pre>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="why-it-helps"><a class="anchor" href="#why-it-helps">Why it helps</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Without dedicated support, teams often duplicate holiday logic in Pipelines or rely on weekday-only checks. That can cause jobs to run during holidays or skip make-up workdays.</p>
</div>
<div class="paragraph">
<p>The plugin keeps those rules centralized and makes Pipeline behavior easier to understand.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="learn-more"><a class="anchor" href="#learn-more">Learn more</h2>
<div class="sectionbody">
<div class="ulist">
<ul>
<li>
<p>Plugin site: <a href="https://plugins.jenkins.io/chinese-workday/">plugins.jenkins.io/chinese-workday</a></p>
</li>
<li>
<p>Source code: <a href="https://github.com/jenkinsci/chinese-workday-plugin">github.com/jenkinsci/chinese-workday-plugin</a></p>
</li>
</ul>
</div>
<div class="paragraph">
<p>Feedback and contributions are welcome.</p>
</div>
</div>
</div>
