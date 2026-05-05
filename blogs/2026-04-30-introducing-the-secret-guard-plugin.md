---
title: "Introducing the Secret Guard Plugin"
url: "https://www.jenkins.io/blog/2026/04/30/introducing-secret-guard-plugin/"
date: "2026-04-30T00:00:00+00:00"
author: ""
feed_url: "https://www.jenkins.io/rss.xml"
---
<div id="preamble">
<div class="sectionbody">
<div class="paragraph">
<p><span class="image"><img alt="Secret Guard cover" src="https://www.jenkins.io/images/post-images/2026/04/30/secret-guard-cover-jenkins-shield.png" /></span>
</p>
<div class="paragraph">
<p>Hardcoded secrets still show up in Jenkins for very ordinary reasons.</p>
</div>
<div class="paragraph">
<p>A token is pasted into a job field during a quick test. A webhook URL with a secret query parameter stays in <code>config.xml</code>. An inline Pipeline header works once and is never revisited. These cases are easy to introduce and easy to overlook.</p>
</div>
<div class="paragraph">
<p>Once a secret is stored in job configuration or a Jenkinsfile, it becomes harder to rotate and easier to expose through exports, backups, logs, or screenshots.</p>
</div>
<div class="paragraph">
<p>The Secret Guard Plugin was created to help Jenkins administrators and job authors catch those patterns earlier.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="what-it-checks"><a class="anchor" href="#what-it-checks">What it checks</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Secret Guard is a Jenkins plugin that checks Jenkins jobs and Pipeline definitions for hardcoded secret leakage risks.</p>
</div>
<div class="paragraph">
<p>It scans common high-risk locations such as:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Job <code>config.xml</code></p>
</li>
<li>
<p>inline Pipeline scripts</p>
</li>
<li>
<p>Pipeline-from-SCM Jenkinsfiles when lightweight SCM access is available</p>
</li>
<li>
<p>multibranch Pipeline Jenkinsfiles when lightweight SCM access is available</p>
</li>
<li>
<p>parameter default values</p>
</li>
<li>
<p>environment variable definitions</p>
</li>
<li>
<p>command content such as <code>sh</code>, <code>bat</code>, <code>powershell</code>, and HTTP-style request usage</p>
</li>
</ul>
</div>
<div class="paragraph">
<p>It can be used in several practical ways:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>save-time enforcement for job configuration changes</p>
</li>
<li>
<p>build-time scanning</p>
</li>
<li>
<p>job-level <code>Scan Now</code></p>
</li>
<li>
<p>global <code>Scan All Jobs</code></p>
</li>
</ul>
</div>
<div class="paragraph">
<p>The plugin stores masked results only, so administrators can review findings without persisting raw secret values in plugin reports.</p>
</div>
<div class="paragraph">
<p>The global Secret Guard page gives administrators a single place to review the latest scan results and run an on-demand scan across jobs.</p>
</div>
<div class="paragraph">
<p><span class="image"><img alt="Secret Guard root action page" src="https://www.jenkins.io/images/post-images/2026/04/30/secret-guard-root-action-page-screenshot.png" /></span>
</p>
</div>
</div>
<div class="sect1">
<h2 id="a-simple-example"><a class="anchor" href="#a-simple-example">A simple example</h2>
<div class="sectionbody">
<div class="paragraph">
<p>A common case is a Pipeline that embeds a token directly in an environment variable or HTTP header:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="rouge highlight nowrap"><code><span class="n">pipeline</span> <span class="o">{</span>
    <span class="n">agent</span> <span class="n">any</span>
    <span class="n">environment</span> <span class="o">{</span>
        <span class="n">API_TOKEN</span> <span class="o">=</span> <span class="s1">'ghp_012345678901234567890123456789012345'</span>
    <span class="o">}</span>
    <span class="n">stages</span> <span class="o">{</span>
        <span class="n">stage</span><span class="o">(</span><span class="s1">'Call API'</span><span class="o">)</span> <span class="o">{</span>
            <span class="n">steps</span> <span class="o">{</span>
                <span class="n">sh</span> <span class="s2">"curl -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.abc123456789.def123456789' https://example.invalid"</span>
            <span class="o">}</span>
        <span class="o">}</span>
    <span class="o">}</span>
<span class="o">}</span></code></pre>
</div>
</div>
<div class="paragraph">
<p>The safer pattern is to store the secret in Jenkins Credentials and inject it only at runtime:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="rouge highlight nowrap"><code><span class="n">pipeline</span> <span class="o">{</span>
    <span class="n">agent</span> <span class="n">any</span>
    <span class="n">stages</span> <span class="o">{</span>
        <span class="n">stage</span><span class="o">(</span><span class="s1">'Call API'</span><span class="o">)</span> <span class="o">{</span>
            <span class="n">steps</span> <span class="o">{</span>
                <span class="n">withCredentials</span><span class="o">([</span><span class="n">string</span><span class="o">(</span><span class="nl">credentialsId:</span> <span class="s1">'api-token'</span><span class="o">,</span> <span class="nl">variable:</span> <span class="s1">'API_TOKEN'</span><span class="o">)])</span> <span class="o">{</span>
                    <span class="n">sh</span> <span class="s1">'curl -H "Authorization: Bearer $API_TOKEN" https://example.invalid'</span>
                <span class="o">}</span>
            <span class="o">}</span>
        <span class="o">}</span>
    <span class="o">}</span>
<span class="o">}</span></code></pre>
</div>
</div>
<div class="paragraph">
<p>This is the kind of issue Secret Guard is designed to catch with deterministic rules rather than broad inference.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="why-the-scope-is-narrow"><a class="anchor" href="#why-the-scope-is-narrow">Why the scope is narrow</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Secret Guard is intentionally narrow in scope.</p>
</div>
<div class="paragraph">
<p>It does not try to be a general-purpose governance platform or a generic code-quality tool. Instead, it focuses on recurring high-confidence secret leakage patterns in Jenkins configuration and Pipeline usage. That keeps the plugin easier to reason about and reduces noise from overly aggressive heuristics.</p>
</div>
<div class="paragraph">
<p>For teams that want to adopt it gradually, the plugin supports multiple enforcement modes:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><code>AUDIT</code> records findings without blocking</p>
</li>
<li>
<p><code>WARN</code> allows the operation but surfaces the risk</p>
</li>
<li>
<p><code>BLOCK</code> prevents unexempted findings at or above the configured threshold</p>
</li>
</ul>
</div>
<div class="paragraph">
<p>This makes it possible to start with visibility and move toward stricter enforcement when teams are ready.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="learn-more"><a class="anchor" href="#learn-more">Learn more</h2>
<div class="sectionbody">
<div class="ulist">
<ul>
<li>
<p>Plugin site: <a href="https://plugins.jenkins.io/secret-guard">Secret Guard Plugin</a></p>
</li>
<li>
<p>Source code: <a href="https://github.com/jenkinsci/secret-guard-plugin">jenkinsci/secret-guard-plugin</a></p>
</li>
</ul>
</div>
<div class="paragraph">
<p>Feedback and contributions are welcome.</p>
</div>
</div>
</div></div></div>
