---
title: "Jenkins 2.562 and 2.555.2: Signed by LF Open Source, LLC"
url: "https://www.jenkins.io/blog/2026/04/29/windows-installer-signing-change/"
date: "2026-04-29T00:00:00+00:00"
author: ""
feed_url: "https://www.jenkins.io/rss.xml"
---
<div class="paragraph">
<p>Beginning April 28, 2026 with Jenkins weekly 2.562, the MSI installer is signed using the Microsoft Artifact Signing Service.
The installer is signed by LF Open Source, LLC, courtesy of the Linux Foundation.
The same change will be made in Jenkins LTS 2.555.2 beginning May 13, 2026.</p>
</div>
<div class="paragraph">
<p>In the transition period, there are some changes to the installation process.
We hope that these changes are temporary while the installer’s reputation develops in Microsoft Defender SmartScreen.</p>
</div>
<div class="sect1">
<h2 id="windows-edge-infrequently-downloaded"><a class="anchor" href="#windows-edge-infrequently-downloaded">Windows Edge - infrequently downloaded</h2>
<div class="sectionbody">
<div class="paragraph">
<p>Windows Edge, the default browser on Microsoft Windows, is integrated with Windows Defender SmartScreen.
That integration causes new installers and new applications to be flagged as "infrequently downloaded".</p>
</div>
<div class="paragraph">
<p>Windows administrators that download the Jenkins installer with Microsoft Edge will need to click the "<strong>Keep anyway</strong>" button until Windows Defender SmartScreen decides the Jenkins MSI installer has enough reputation.</p>
</div>
<div class="paragraph">
<p>The Windows Edge dialog looks like this:</p>
</div>
<div class="paragraph">
<p><span class="image center"><img alt="make sure you trust jenkins msi" src="https://www.jenkins.io/images/post-images/2026/04/29/make-sure-you-trust-jenkins-msi.png" /></span>
</p>
</div>
</div>
<div class="sect1">
<h2 id="windows-defender-smartscreen"><a class="anchor" href="#windows-defender-smartscreen">Windows Defender SmartScreen</h2>
<div class="sectionbody">
<div class="paragraph">
<p>When the MSI installer is run, Windows displays the SmartScreen prompt that says:</p>
</div>
<div class="quoteblock">
<blockquote>
Microsoft Defender SmartScreen prevented an unrecognized app from starting.
Running this app might put your PC at risk.
</blockquote>
<div class="attribution">
— Microsoft Defender SmartScreen
</div>
</div>
<div class="paragraph">
<p>The dialog looks like this:</p>
</div>
<div class="paragraph">
<p><span class="image center"><img alt="protected your pc 1" src="https://www.jenkins.io/images/windows/protected-your-pc-1.png" /></span>
</p>
<div class="paragraph">
<p>Click the "<strong>More info</strong>" link and that will change the dialog to display the publisher of the signed MSI file.
The publisher is "LF Open Source, LLC".</p>
</div>
<div class="paragraph">
<p>The dialog looks like this:</p>
</div>
<div class="paragraph">
<p><span class="image center"><img alt="protected your pc 2" src="https://www.jenkins.io/images/windows/protected-your-pc-2.png" /></span>
</p>
<div class="paragraph">
<p>Press the "<strong>Run anyway</strong>" button and the MSI installer will run.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="frequently-asked-questions"><a class="anchor" href="#frequently-asked-questions">Frequently Asked Questions</h2>
<div class="sectionbody">
<div class="sect2">
<h3 id="why-change-the-msi-signing"><a class="anchor" href="#why-change-the-msi-signing">Why change the MSI signing?</h3>
<div class="paragraph">
<p>The previous code signing certificate expires May 16, 2026.
An unsigned MSI installer has an even worse experience for users than the experience with Windows Defender SmartScreen.</p>
</div>
</div>
<div class="sect2">
<h3 id="why-use-lf-open-source-llc"><a class="anchor" href="#why-use-lf-open-source-llc">Why use LF Open Source, LLC?</h3>
<div class="paragraph">
<p>The Linux Foundation has already pioneered the MSI installer signing process through their work with the NodeJS Foundation.
We were able to use their experiences to quickly revise our MSI installer signing to use the same techniques used by the NodeJS Foundation.</p>
</div>
<div class="paragraph">
<p>We interact frequently with the Linux Foundation because they host the Jira issue tracker for the Jenkins project.
Those interactions continue to help the Jenkins project.</p>
</div>
<div class="paragraph">
<p>The Linux Foundation is the parent organization of the Continuous Delivery Foundation.
The Continuous Delivery Foundation is the parent organization of the Jenkins project and holds its intellectual property.</p>
</div>
</div>
<div class="sect2">
<h3 id="why-not-purchase-an-extended-validation-code-signing-certificate"><a class="anchor" href="#why-not-purchase-an-extended-validation-code-signing-certificate">Why not purchase an extended validation code signing certificate?</h3>
<div class="paragraph">
<p>Extended validation certificates require a secure physical storage device or they require reliance on the code signing service of the certificate prvider.
We rarely interact with the certificate providers and find it difficult when we interact with them.
They are accustomed to working with corporations, not open source projects.
Open source projects are not their primary income source and are not their target market.</p>
</div>
</div>
<div class="sect2">
<h3 id="which-operating-systems-are-affected"><a class="anchor" href="#which-operating-systems-are-affected">Which operating systems are affected?</h3>
<div class="paragraph">
<p>All supported versions of Windows are affected.</p>
</div>
</div>
</div>
</div></div></div></div>
