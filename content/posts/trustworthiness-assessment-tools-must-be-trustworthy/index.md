---
title: "Trustworthiness assessment tools must be trustworthy"
layout: single
authors: ["ian-hussey", "lukas-jung", "jamie-cummins"]
date: "2026-10-09"
sitemap: true
---

<br>

<br>

*tl;dr: Using vibe-coded, unvalidated forensic meta-science tools to evaluate the trustworthiness of published research means holding authors to standards that we ourselves do not meet. The solution is less vibe-coding and more validation.*

<br>

We recently attended “AI for Research Integrity: A Working Convening” on September 18-19 in Montreal. This small, by-invitation event was organised by COS and funded by Coefficient Giving, who also recently funded the Medical Evidence Project and co-funded the UKRI Meta-Science grants. As the organisers stated in the event’s materials:

*“The problem: A lot of people are building AI tools for research integrity: replication prediction, evidence synthesis, fraud detection, automated peer review, pre-registration checking, and more. Tool builders don't know what other teams are working on, datasets aren't being shared, and without coordination we're heading toward many bespoke tools that don't interoperate and don't build on each other's work. There's also a risk that this space ends up with many aborted efforts and few sustainable services. Establishing communication and light coordination could have substantial benefits.”*

The three of us are meta-scientists who work in the forensic space ourselves, to varying extents. We are grateful to have been invited and thank the organisers and funder. We agreed with the meeting’s problem statement, which mirrored our own observations over the past year or so.  

Unfortunately, in our opinion, the communication facilitated by the convening did more to demonstrate the depth of the problems we collectively face. Of course, understanding a problem is an important early step in solving it, hence this post. 

## **The field faces a first-mile problem, not a last-mile problem**

Daniel Acuna, of [reviewerzero.ai](http://reviewerzero.ai), provided his own reflections on the convening in a [Linkedin post](https://www.linkedin.com/pulse/ai-research-integrity-montreal-notes-daniel-acuna-zdatc/), in which he says that discussion of such tools at the event “gave us a sense of how hard the last mile problem” is. We believe that the field does not face a [last mile problem](https://en.wikipedia.org/wiki/Last_mile_\(transportation\)), but rather a first mile problem.

For several years, two of us (Ian and Jamie) have employed the following heuristic when encountering new ideas, proposals, tools, etc: can it withstand one follow-up question? We decided to try to ask a follow-up question for one particular forensic method: the GRIM test.

GRIM was one of the first forensic methods that emerged from the data sleuthing movement of the 2010s. In short, GRIM tests whether a reported mean value is mathematically consistent with the reported sample size and the data being integer (e.g., Likert scales). Its caveats and limitations have been known from the start, and are clearly laid out in the well-cited canonical article that presents the method ([Brown and Heathers, 2017](https://doi.org/10.1177/1948550616673876)). 

At the convening, we spoke to at least five individuals or groups developing forensic meta-science tools that employ the GRIM test, some public-facing and some not. In order to keep our points here general, we’re not going to name any of the individual tools.

We are very familiar with GRIM: Lukas is the developer of [scrutiny](https://lhdjung.github.io/scrutiny/), which is arguably the most robust and widely-used R package implementing GRIM. Ian and Lukas also maintain [INSPECT-SR](https://inspect-sr.com/)’s [recommended GRIM checker](https://errors.shinyapps.io/inspect-sr-means-variances/), which is Cochrane’s recommended Trustworthiness Assessment tool ([Wilkinson et al., 2026](https://www.bmj.com/content/394/bmj-2026-100611)). More generally, we have all used GRIM as part of wider trustworthiness assessments of published papers, which has resulted in multiple retractions. 

Being highly familiar with GRIM, and having experience in teaching students how to use it, we are also aware of the most common misunderstandings and misuses of the method: how to handle multi-item scales.[^1] The point of this post is not to fully explain this common misunderstanding; suffice it to say that any tool implementing GRIM to screen papers for problems should have a clear way to deal with this tricky issue, or else GRIM will produce false positives \- i.e., it can incorrectly flag some results as being problematic. So, our go-to follow up question for tool developers implementing GRIM was “how does your tool handle multi-item self-report scales?” 

Most of the developers we spoke to were unaware of this consideration, and only one of them explicitly accommodated this parameter. It is unclear that their tools correctly implement GRIM, and therefore are likely to produce false positives.

Tool developers in this space seem to be generally oriented towards implementing several individual checks, not just GRIM, and towards applying tools “at scale” to dozens, hundreds, or even thousands of articles. But the first mile problem here is whether tool developers understand the specifics of each method. No human vetting or validation of the tools output can meaningfully validate its output if the humans themselves do not understand the methods. 

We also have a second-order concern: in many cases, tool developers who we made aware of this issue did not seem overly concerned, despite the fact that their tools are likely producing false positives as a consequence.[^2] We believe this represents a problematic asymmetry in rigour between what we ask of authors of published work and the developers of tools designed to audit that work. This could have down-stream reputational risks, both for forensic meta-science and for the authors of articles being scrutinised, which we think are very important to avoid. Put simply: the trustworthiness assessment tools must be trustworthy.

## **Forensic meta-science tools require validation that is currently severely lacking**

The term *vibe coding* is thrown around a lot lately. We think the term generally fails to capture the problem, which relates to what has not been done rather than what has. More specifically: there is generally little-to-no systematic checking or validating of these tools. *Vibe checking*, if you will. 

Forensic meta-science work holds published research, and its authors, to certain standards of scientific scrutiny, transparency, and verifiability. We believe forensic metascience tools must be held to the same, or perhaps higher, standards. Some of us, along with others, have recently argued similar points in the context of meta-science datasets ([Elson et al., 2026 in press](https://psyarxiv.com/6eyjf)). 

We are currently writing an article length treatment of this concern, whose working title represents its key message: *Forensic meta-science methods and tools require validation.* As far as we can see, there is a conspicuous and worrying lack of validation of most tools.

Validation means many things, and many forms of validation \- plus verifiability of that validation \- would be required for a tool to meet the bar for it being ready for use in trustworthiness assessment contexts. This requires deeper treatment than this blog post. For now, we will pull out just one of our specific recommendations from that in-preparation manuscript, which relates to the deployment of resources: 

1. Making a nice GUI front-end for a software tool used to be hard, but now with LLMs it is easy.[^3]   
2. Validating a tool against a human-coded reference standard is still hard \- particularly when this usually involves the painstaking collection of new human data.  
3. The appropriate reaction to a changing difficulty landscape (i.e., due to LLMs) is not to pour more resources into the thing that is now easy. Rather, it is to reallocate the saved resources from the thing that is now easy to the thing that is still hard (validation). 

On reflection, we no longer think that the over-abundance of early stage tool development projects, highlighted by the organisers of the convening in their blurb, is due merely to a lack of communication between developers. Communication and collaboration are a very good thing, and we support them. But this over abundance of early stage projects might be usefully ascribed to the fact that those early stages are relatively easy, at least relative to actually validating such tools which is much harder. Given the importance of the subject matter \- i.e., pointing out potentially retraction-worthy issues in published articles \- there must be great certainty about the validity of the trustworthiness assessment tools themselves.

## **Conflict of Interest statement**

Ian Hussey is developer of multiple forensic meta-science methods and tools (e.g., [strait](https://github.com/ianhussey/strait), [recalc](https://github.com/ianhussey/recalc), [INSPECT-SR consistency checker for means and variances](https://errors.shinyapps.io/inspect-sr-means-variances/)).  
Lukas Jung is developer of multiple forensic meta-science methods and tools (e.g., [scrutiny](https://github.com/lhdjung/scrutiny), [unsum](https://github.com/lhdjung/unsum), [INSPECT-SR consistency checker for means and variances](https://errors.shinyapps.io/inspect-sr-means-variances/)).  
Jamie Cummins is developer of several tools, including RegCheck ([regcheck.app](https://regcheck.app)), PreCheck, and CodeBot. RegCheck is both a tool in its own right soon to be recommended as part of [INSPECT-SR](https://inspect-sr.com), and is also used in the INSPECT-AI tool (Vorland & Avenell) for semi-automated research integrity checks.   
All tools are currently undergoing extensive validation.  


[^1]:  GRIM assesses whether reported rounded sample means are consistent with reported sample sizes given integer data. However, averaging across participants to create a sample mean is not the only thing that can ‘use up’ the granularity that GRIM relies on: if the researchers calculated participant-means across multi-item scales (i.e., as opposed to participant sum-scores, or using a single item measure), the number of scale items averaged over changes which sample means are a) checkable and b) consistent with the reported sample size.   

[^2]:  Note that GRIM is deterministic, and not a statistical inference test like a *p* value is. Correctly reported means derived from real data will never be labelled as inconsistent, and therefore all inconsistent results require there to be a problem somewhere, either on behalf of the authors or the person applying GRIM. 

[^3]:  We’re aware we are making sweeping generalisations here; give us some poetic license to make a general point.