---
title: Interrogating Your Sources
parent: Citation Integrity
nav_order: 1
---

# Interrogating Your Sources

Finding scholarly sources is only half the job.
Determining their validity and identifying gaps in the information they provide is another important step.
This page covers two skills that will strengthen your paper: checking that your sources are independent of each other, and critically evaluating what each source does and does not show.

## Checking Citation Independence

It's important to ensure that your sources do not contain circular reasoning or references to one another.
This requirement exists because research needs to be built on independently produced evidence, not an echo chamber of sources that only reinforce each other.

**Circular citation** occurs when Source A cites Source B as evidence, and Source B cites Source A as evidence, with neither source providing independent data to support the shared claim.

### How to check: use "Cited by" links

You don't need to manually read through every source's reference list.
[Google Scholar](https://scholar.google.com/) and [Semantic Scholar](https://www.semanticscholar.org/) both let you check citation relationships in a few clicks:

1. Search for one of your sources by title.
2. Click the **"Cited by"** link beneath the result.
3. On the list of citing articles, search for the authors or titles of your other sources.
If one of your other sources appears, that source cites this one.
4. Repeat in the other direction: search for the other source and check whether the first one appears in *its* "Cited by" list.
5. If both directions match — Source A cites Source B *and* Source B cites Source A — check whether the shared claim has any independent backing.

{% include feature/alert.html color="secondary" text="**Google Scholar tip:** After clicking \"Cited by,\" use the \"Search within citing articles\" box to quickly search for an author name or keyword instead of scrolling through the full list." %}

### When you do find mutual citations

Mutual citation alone is not a problem.
In an active research area, it's normal for researchers to cite related work, and two papers citing each other simply means the authors are aware of each other.

The issue arises when the *evidence* for a claim you're using loops back on itself with no independent data underneath.
When you find a mutual citation pair, read the relevant sections and ask: "Does each paper provide its own independent evidence (different experiments, different data sets), or is one just re-citing the other's findings?"

If the only support for a key claim traces back and forth between the same two or three sources with no outside evidence, find additional sources.

## Critical Evaluation

Even after establishing a source's credentials, it's important to evaluate what the source actually shows.

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

### Interrogation (stronger)

> "This study tested its power management algorithm on a single ARM Cortex-M0 platform running a temperature-monitoring workload. The results showed a 34% reduction in active-mode power consumption compared to the baseline. However, the authors noted that they did not test the algorithm under variable workloads or on other microcontroller architectures. This means the 34% figure may not generalize to the mixed-signal processing workloads common in industrial IoT deployments, which is the context of my research. The study's contribution is valid for its tested conditions, but I should note this limitation when applying its conclusions to my broader topic."

This paragraph shows the reader that you've actually read and understood the source.
It identifies what the study tested, what it found, what it didn't test, and what that means for your paper's argument.
This is the level of engagement your assignment is looking for.

## Helpful Questions to Ask During Interrogations

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

## Further Resources

- [**U of I Library Research Help**](https://www.lib.uidaho.edu/help/) - Ask a University of Idaho librarian for help evaluating sources or finding independent references for your topic
