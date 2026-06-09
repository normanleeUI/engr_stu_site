---
title: Interrogating Your Sources
parent: Citation Integrity
nav_order: 1
---

# Interrogating Your Sources

Finding scholarly sources is only half the job.
Your assignment also asks you to "discuss the validity of your sources and identify any gaps in the information provided."
This means you need to do more than confirm that a source is peer-reviewed — you need to examine what it actually proves, where its evidence is strong, and where it falls short.
This page covers two skills that will strengthen your paper: checking that your sources are independent of each other, and critically evaluating what each source does and does not show.

## Checking Citation Independence

Your assignment instructions say: "Ensure that your sources do not contain circular reasoning or references to one another."
This requirement exists because your paper needs to be built on independently produced evidence, not on a closed loop of sources that only reinforce each other.

**Circular citation** occurs when Source A cites Source B as evidence, and Source B cites Source A as evidence, with neither source providing independent data to support the shared claim.
When this happens, the claim looks well-supported — two sources agree! — but neither one actually generated its own proof.
You're looking at one piece of evidence wearing two hats.

Here's how to check for this problem:

1. Open the references section of each source you plan to cite.
2. Look for the authors and titles of your other sources in those reference lists.
3. If Source A appears in Source B's references *and* Source B appears in Source A's references, check whether the shared claim has any independent backing.
4. If the only support for a key claim traces back and forth between the same two (or three) sources with no outside evidence, you have a circular citation problem.

This doesn't mean your sources can never mention each other.
In an active research area, it's normal for researchers to be aware of and cite related work.
The issue arises when the *evidence* for a claim you're using loops back on itself — when you trace the support and end up where you started, with no independent data underneath.

If you find circular citations, the fix is straightforward: find an additional source that reaches the same conclusion through its own methodology and data.
That independent source breaks the loop and gives your paper a stronger evidentiary foundation.

## Critical Evaluation vs. Justification

This is one of the most common issues instructors see in student papers.
When asked to "discuss the validity of your sources," many students respond by justifying why the source is credible — and stop there.
But your assignment is asking for something deeper: it wants you to evaluate what the source actually shows.

**Justification** describes a source's credentials.
It answers the question "Why should I trust this source?"
**Interrogation** evaluates a source's substance.
It answers the question "What does this source actually prove, and where are its limits?"

Both are useful, but justification alone isn't enough.
Saying a source is peer-reviewed tells your reader that experts vetted it before publication.
It doesn't tell your reader what the source's methodology can and cannot support, or whether its conclusions apply to your specific topic.

## A Before-and-After Example

Suppose you're writing about low-power design techniques for IoT sensor nodes, and one of your sources is a journal article that tested a new power management algorithm on a specific microcontroller platform.

### Justification only (weaker)

> "This source is a credible reference for my paper. It was published in *IEEE Transactions on Very Large Scale Integration Systems*, which is a well-known peer-reviewed journal. The authors are affiliated with a major research university and have published extensively in this area. The article has been cited over 50 times, which indicates that the research community considers it reliable."

This paragraph tells the reader *about* the source, but it doesn't engage with what the source actually found.
It could describe almost any paper in the field — it says nothing specific about this paper's research.

### Interrogation (stronger)

> "This study tested its power management algorithm on a single ARM Cortex-M0 platform running a temperature-monitoring workload. The results showed a 34% reduction in active-mode power consumption compared to the baseline. However, the authors noted that they did not test the algorithm under variable workloads or on other microcontroller architectures. This means the 34% figure may not generalize to the mixed-signal processing workloads common in industrial IoT deployments, which is the context of my paper. The study's contribution is valid for its tested conditions, but I should note this limitation when applying its conclusions to my broader topic."

This paragraph shows the reader that you've actually read and understood the source.
It identifies what the study tested, what it found, what it didn't test, and what that means for your paper's argument.
This is the level of engagement your assignment is looking for.

## Questions to Ask About Every Source

When you read a source you plan to cite, work through these questions.
You don't need to address all of them in your paper, but thinking through them will help you write a more substantive discussion of your sources' validity.

- **What methodology was used?**
Did the researchers run experiments, build simulations, conduct surveys, or perform a theoretical analysis?
Each method has different strengths and limitations.

- **What conditions were tested?**
What specific hardware, software, parameters, or scenarios did the study use?
Results obtained under narrow conditions may not apply broadly.

- **Do the conclusions follow from the data?**
Look at whether the authors' claims are supported by the results they present.
Sometimes conclusions overreach — a study that tested one scenario may claim general applicability without sufficient evidence.

- **What is missing?**
What did the study *not* test, *not* measure, or *not* account for?
These gaps aren't necessarily flaws — every study has boundaries — but identifying them shows that you understand the limits of the evidence.

- **How recent is the work?**
In fast-moving fields like ECE, a study from ten years ago may use outdated tools or assumptions.
Check whether newer work has superseded its findings.

{% include feature/alert.html color="blue" text="You don't need to tear your sources apart. Identifying limitations isn't the same as saying a source is bad — it's saying you understand what the source can and cannot support. Strong papers acknowledge these limits honestly." %}

## Why This Matters for Your Paper

When you justify a source, you're telling your reader to trust it.
When you interrogate a source, you're showing your reader that *you* understand it.
Instructors consistently note that students tend toward justification — listing credentials, impact factors, and citation counts — rather than engaging with the research itself.

The difference shows up in your paper's quality.
A paper that interrogates its sources reads like it was written by someone who understands the topic.
A paper that only justifies its sources reads like it was written by someone who found some articles and confirmed they were peer-reviewed.

Your assignment's instruction to "discuss the validity of your sources and identify any gaps" is specifically asking for interrogation.
Use the questions above as a starting point, and your discussion of sources will be substantially stronger than a surface-level credibility check.

## Further Resources

- [**"How to Read a Paper" by S. Keshav**](https://svr-sk818-web.cl.cam.ac.uk/keshav/papers/07/paper-reading.pdf) - A widely used three-pass method for reading research papers efficiently and critically

- [**U of I Library Research Help**](https://www.lib.uidaho.edu/help/) - Ask a University of Idaho librarian for help evaluating sources or finding independent references for your topic
