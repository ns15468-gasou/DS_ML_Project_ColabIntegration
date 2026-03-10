# Speaker Notes - Nic
## Even-numbered slides. ~1 min each.

---

## Slide 2 - Introduction to Our Topic

The chart behind me tells the story pretty well — Business Email Compromise losses went from around $200 million in 2015 to $2.7 billion in 2022. The threat is not slowing down, and traditional defenses — keyword filters, static blocklists — are fundamentally reactive. They can only block what they've already seen.

What makes this an interesting data science problem is that AI and NLP have evolved dramatically in the last five years, but the foundational data underpinning phishing — the domains themselves — hasn't been deeply analyzed semantically. That's the gap we're after.

Our guiding research question is: **Do domain semantics predict real-world malicious activity to a statistically significant degree?**

That's what the literature review is here to set up — what's been tried, where it falls short, and why our angle is worth pursuing.

---

## Slide 4 - Reactive Detection of Attacks

These two 2020 papers both arrive at the same conclusion from different directions: keyword-based detection fails because spammers can obfuscate words, but they can't easily disguise intent or meaning.

Saidani et al. built a two-level semantic classification framework for email — categorizing by subject domain first, then building domain-specific feature spaces. Result: up to 98% accuracy, which was a significant jump over the bag-of-words baseline.

Sonowal and Gunikhan applied similar thinking to SMS — smishing. Worth noting that SMS has a 98% open rate versus email's 20-30%, so the stakes are higher. They reduced 52 features down to 20 using Kendall rank correlation — a 61% dimensionality reduction — while maintaining 98% accuracy. That reduction was critical for making the model viable on a phone's limited hardware.

Both papers share a weakness: as generative AI gets better at mimicking professional writing, the readability gap these systems rely on starts to close.

---

## Slide 6 - Proactive Prevention of Attacks

These are the two most recent papers in the review, and they represent what's possible now that LLMs are mature.

PhishFighter, from Brezeanu et al., takes a structural approach — instead of looking at content, it analyzes the HTML tag structure of a page. Phishing kits reuse the same HTML skeletons across campaigns, even when targeting different brands. Their system clusters those structures and self-retrains when it finds something new. Weighted F1 scores above 90%.

APOLLO from Desolda et al. uses GPT-4o to both classify phishing emails and generate plain-English explanations for the user. Without any hand-crafted features, it hit 97.4% accuracy — rising to 99.9% when VirusTotal data was mature. Notably, 76% of users shown APOLLO's warnings chose not to continue to the site, versus 53% with a manually written warning.

Both are impressive, but both hit the same ceiling: zero-day. PhishFighter needs three pages from a new kit before it can cluster it. APOLLO degrades when VirusTotal has no prior data on a URL. That unsolved problem is the thread connecting everything in this review.

---

## Slide 8 - Primary Research Gaps Identified

Every paper we reviewed — regardless of approach — runs into these three walls.

**Zero-day.** The most fundamental problem. Every system we reviewed degrades sharply against threats it hasn't seen before. This isn't a minor footnote — it's the central unsolved challenge connecting all eight papers.

**Evolution of ML capabilities.** In five years, the field went from bag-of-words filters to a general-purpose LLM classifying phishing at 97.4% accuracy with no hand-crafted features. We're at an inflection point where the tools are finally capable enough to tackle the zero-day problem — if we apply them to the right data.

**Empowering the end user.** Sarno et al. showed that some phishing will always reach the inbox, and that users are often overconfident in their ability to detect it. APOLLO showed that interpretable warnings meaningfully change behavior. The implication is that interpretability isn't a luxury — it's a design requirement for any system that wants to actually protect people.

---

## Slide 10 - Summary & Conclusion

To pull it together: semantic analysis is becoming instrumental in fighting cyber threats, and the tools to do it cost-effectively are finally here.

Our project's angle is to start at the most fundamental unit of phishing data — the domain itself. A human can look at "scamazon.com" and know something is off. The question is whether cost-effective semantic embeddings can automatically "know" the same thing — and do it at scale, proactively, before a threat has been reported anywhere.

We're using Gemini text embeddings and cosine similarity to compare 50,000 legitimate Tranco domains against 55,000 verified PhishTank URLs. From there: similarity thresholds, model training, and ultimately real-time risk scoring.

The literature told us what's been tried and where the ceiling is. Our contribution is going one level deeper — to the semantic metadata of the domain itself — which none of the reviewed papers explored directly.
