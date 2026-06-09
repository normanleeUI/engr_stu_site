---
title: Common Citation Pitfalls
parent: Citation Integrity
nav_order: 3
---

# Common Citation Pitfalls

Not every source that looks credible on the surface will strengthen your paper.
Some problems with sources aren't obvious from a title or abstract — they require you to look at how a paper was published, how it's been used by other researchers, and whether its claims hold up under scrutiny.
This page covers four common pitfalls that can weaken your two-page IEEE-format paper if you don't watch for them.

## Over-Cited Seminal Papers

Some papers are cited so often that they become shorthand for an entire idea.
In ECE, you'll encounter landmark papers with hundreds or thousands of citations — foundational work on topics like Shannon's information theory, Moore's law observations, or early neural network architectures.
These papers are important, but their popularity creates a specific risk: researchers (and students) cite them without carefully reading them.

**Over-citation** happens when a widely cited paper gets referenced as blanket support for a claim it doesn't actually make, or when its findings get generalized far beyond what the original authors intended.
For example, a seminal paper that demonstrated a technique on one class of circuits might get cited as evidence that the technique works universally — even though the authors explicitly noted it was tested under narrow conditions.

This matters for your paper because citing a source you haven't fully read is one of the fastest ways to introduce an inaccurate claim.
If a reviewer or instructor traces your citation back to the original, and the paper doesn't say what you implied it says, your credibility takes a hit.

Here's how to protect yourself:

- **Read the paper**, not just the abstract.
Pay particular attention to the methodology section (what was actually tested) and the limitations section (what the authors say their work does *not* prove).

- **Check the date.**
A highly cited paper from 1998 may have been superseded by newer work.
Look for more recent studies that build on or revise its conclusions.

- **Cite for specifics, not authority.**
Instead of citing a famous paper to lend general weight to your argument, cite it for the specific finding or method you're actually using.

## Publish-or-Perish Distortions

Academic researchers are under significant pressure to publish frequently.
Hiring, tenure, and funding decisions often depend on publication counts, which creates an incentive structure known as **publish-or-perish**.
The result is that not every published paper represents a meaningful contribution — some exist primarily to add a line to someone's CV.

This doesn't mean most research is bad.
It does mean you should watch for papers that exhibit signs of quantity-over-quality pressure:

- **Minimal novelty** — The paper restates known results with a trivial variation (e.g., testing an existing algorithm on a slightly different dataset without new insight).

- **Inflated claims** — The abstract or conclusion makes broad claims ("revolutionary," "paradigm-shifting") that the actual results don't support.
Look at the data: does a 2% improvement on one benchmark really justify the language used?

- **Salami slicing** — A single study's worth of results is split across multiple papers, each presenting a thin slice.
If you find several papers by the same authors that seem to cover nearly identical ground, this may be what's happening.

For your assignment, the practical takeaway is simple: don't be impressed by a paper's existence alone.
Read the results section and ask whether the paper actually contributes something you can use as evidence.
A peer-reviewed paper that shows a minor, incremental result is a weaker source than one that presents clear evidence for a substantive claim.

## Predatory Journals

A **predatory journal** is a publication that charges authors a fee to publish their work but provides little or no legitimate peer review in return.
These journals mimic the appearance of real academic journals — they have official-sounding names, professional-looking websites, and ISSN numbers — but they will publish nearly anything for a fee.

Predatory journals are a problem because a paper published in one has not been properly vetted.
Citing it in your paper is essentially citing unreviewed work, even though it looks like a journal article.

Watch for these warning signs:

- **Aggressive solicitation emails.**
If a journal sends unsolicited emails inviting submissions (especially flattering ones addressed to "Dear Esteemed Researcher"), treat it with suspicion.
Reputable journals don't typically recruit authors this way.

- **Unrealistically fast peer review.**
Legitimate peer review in engineering takes weeks to months.
If a journal promises publication within days, it isn't conducting a serious review.

- **No recognizable editorial board.**
Check the journal's website for its editorial board.
If the board members are not established researchers in the field, or if no board is listed at all, that's a red flag.

- **Missing from major indexes.**
Reputable ECE journals are indexed in databases like IEEE Xplore, Web of Science, or Scopus.
You can also check whether a journal has a **Journal Impact Factor** (JIF) by looking it up in [Journal Citation Reports (JCR)](PROXY_URL_PLACEHOLDER), which is available through the University of Idaho Library.
If a journal isn't indexed anywhere you recognize, investigate further before citing it.

{% include feature/alert.html color="blue" text="If you found your source through a library database like IEEE Xplore or Web of Science, it has almost certainly passed through legitimate editorial and review processes. The predatory journal risk is highest when you find articles through general web searches." %}

## Circular Citation Patterns

**Circular citation** occurs when a small group of papers cite each other as evidence for the same claim, with no independent source providing outside validation.
The result is a closed loop: the claim looks well-supported because multiple sources agree, but when you trace the evidence, it all originates from the same small group.

This is especially relevant to your assignment, which specifically requires that your sources "do not contain circular reasoning or references to one another."
That instruction exists because your paper needs to rest on independently produced evidence.

Here's how to check for circular patterns:

1. Open the references section of each source you plan to cite.
2. Look for the names and titles of your other sources in those reference lists.
3. If Source A cites Source B, and Source B cites Source A, check whether either one provides its own independent data for the claim you're using.
4. If the evidence for a key point traces in a circle with no outside support, you need to find an additional, independent source.

It's normal for papers in the same research area to be aware of and reference each other's work.
The problem arises when the *evidence* for a claim you depend on loops back on itself — when every trail leads back to the same starting point.

If you discover circular citations among your sources, the fix is to find a source that reaches the same conclusion through its own independent methodology and data.
That independent source breaks the loop and gives your argument a solid foundation.

## Putting It All Together

These four pitfalls are related.
A predatory journal might publish a paper with inflated claims, which gets cited by other low-quality papers in a circular pattern, and eventually a student cites it because it appears in enough reference lists to seem credible.
The common thread is that none of these problems are visible from a quick glance at a title or abstract.

For your two-page IEEE paper, the investment is small but important: before you cite a source, take a few minutes to check where it was published, read its methodology and limitations, and verify that your sources provide independent evidence for your claims.
These habits will produce a stronger paper now and serve you well in future coursework and research.

## Further Resources

- [**"Think. Check. Submit."**](https://thinkchecksubmit.org/) - A checklist to help researchers evaluate whether a journal is trustworthy before submitting or citing work from it

- [**Journal Citation Reports (JCR)**](PROXY_URL_PLACEHOLDER) - Look up journal impact factors and indexing information to verify a journal's standing (available through the U of I Library)

- [**Retraction Watch**](https://retractionwatch.com/) - Tracks retractions of published scientific papers, useful for checking whether a source you found has been retracted
