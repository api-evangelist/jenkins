---
title: "Introducing the Jenkins Plugin of the Month"
url: "https://www.jenkins.io/blog/2026/03/16/plugin-of-the-month/"
date: "2026-03-16T00:00:00+00:00"
author: ""
feed_url: "https://www.jenkins.io/rss.xml"
---
<div class="sect1">
<h2 id="introducing-the-jenkins-plugin-of-the-month"><a class="anchor" href="#introducing-the-jenkins-plugin-of-the-month">Introducing the Jenkins Plugin of the Month</h2>
<div class="sectionbody">
<div class="paragraph">
<p><span class="image center"><img alt="plugin of the month march" src="https://www.jenkins.io/images/post-images/2026/03/plugin_of_the_month_march.png" /></span>
</p>
<div class="paragraph">
<p>The Jenkins ecosystem thrives because of its plugins.</p>
</div>
<div class="paragraph">
<p>With more than two thousand plugins available, Jenkins users can extend their automation platform in countless ways—integrating with tools, improving security, enhancing the user interface, or supporting new development workflows.
Behind each plugin are maintainers and contributors who invest their time to build and support these extensions.</p>
</div>
<div class="paragraph">
<p>To highlight this work and help users discover useful functionality, we are introducing a new initiative on the Jenkins blog:</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="plugin-of-the-month"><a class="anchor" href="#plugin-of-the-month">Plugin of the Month</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Each month, we will feature a <strong>Plugin of the Month</strong>.</p>
</div>
<div class="paragraph">
<p>The goal is to showcase plugins that provide valuable functionality for Jenkins users, highlight the work of their maintainers, and help the community discover capabilities they may not yet know about.</p>
</div>
<div class="paragraph">
<p>Sometimes the featured plugin will be widely used but underappreciated.
Other times it may be a newer plugin that solves an interesting problem.
In all cases, the focus is on highlighting contributions that strengthen the Jenkins ecosystem.</p>
</div>
<div class="paragraph">
<p>If you maintain or use a plugin that deserves more visibility, we welcome suggestions for future editions.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="plugin-of-the-month-oidc-provider-plugin"><a class="anchor" href="#plugin-of-the-month-oidc-provider-plugin">Plugin of the Month: OIDC Provider Plugin</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Our first featured plugin is the <a href="https://plugins.jenkins.io/oidc-provider/">OIDC Provider Plugin</a>.</p>
</div>
<div class="paragraph">
<p>This plugin allows Jenkins to act as an <strong>OpenID Connect (OIDC) provider</strong> so that external systems can securely authenticate using identities issued by Jenkins.</p>
</div>
<div class="paragraph">
<p>Instead of storing long-lived credentials or secrets inside Jenkins pipelines, systems can request short-lived tokens using the OIDC standard.
This significantly reduces the need to manage and rotate static secrets.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="why-this-matters"><a class="anchor" href="#why-this-matters">Why This Matters</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Managing credentials and secrets in CI/CD pipelines can quickly become complex and risky.
Long-lived access keys stored in configuration or credentials stores are a common attack vector.</p>
</div>
<div class="paragraph">
<p>By using <strong>OIDC-based authentication</strong>, Jenkins can issue <strong>short-lived identity tokens</strong> that external systems trust.
This approach improves security while simplifying credential management.</p>
</div>
<div class="paragraph">
<p>This is especially useful when Jenkins pipelines interact with cloud providers such as:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Microsoft Azure</p>
</li>
<li>
<p>Google Cloud Platform (GCP)</p>
</li>
<li>
<p>Amazon Web Services (AWS)</p>
</li>
</ul>
</div>
<div class="paragraph">
<p>Instead of storing cloud access keys in Jenkins, pipelines can authenticate using federated identity through OIDC.</p>
</div>
<div class="paragraph">
<p>The plugin is not limited to cloud providers.
It can also be used to authenticate with <strong>internal services</strong>, such as a local <strong>Artifactory</strong> instance or other systems that support OIDC.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="reducing-secrets-in-pipelines"><a class="anchor" href="#reducing-secrets-in-pipelines">Reducing Secrets in Pipelines</h2>
<div class="sectionbody">
<div class="paragraph">
<p>One of the biggest advantages of this approach is the ability to <strong>reduce or eliminate stored secrets</strong> in Jenkins pipelines.</p>
</div>
<div class="paragraph">
<p>Benefits include:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>No long-lived credentials stored in pipelines</p>
</li>
<li>
<p>Reduced secret management overhead</p>
</li>
<li>
<p>Short-lived tokens issued on demand</p>
</li>
<li>
<p>Better alignment with modern cloud security practices</p>
</li>
</ul>
</div>
</div>
</div>
<div class="sect1">
<h2 id="looking-ahead"><a class="anchor" href="#looking-ahead">Looking Ahead</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The Jenkins plugin ecosystem is one of the project’s greatest strengths.
With the new <strong>Plugin of the Month</strong> series, we hope to highlight the innovation and dedication that plugin maintainers bring to the community.</p>
</div>
<div class="paragraph">
<p>Stay tuned for next month’s featured plugin — and if you have a favorite plugin you think should be highlighted, let us know.</p>
</div>
<div class="paragraph">
<p>Together, we continue to grow and strengthen the Jenkins ecosystem.</p>
</div>
</div>
</div></div>
