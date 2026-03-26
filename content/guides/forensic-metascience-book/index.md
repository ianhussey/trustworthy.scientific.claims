---
title: "An Introduction to Forensic Metascience"
date: 2026-03-24
draft: false
summary: "A free online book by James Heathers introducing forensic meta-science techniques, with worked examples and R code."
tags: ["forensic-meta-science", "GRIM", "GRIMMER", "SPRITE", "book"]
categories: ["means", "standard-deviations", "sample-sizes", "images"]
---

## An Introduction to Forensic Metascience

[An Introduction to Forensic Metascience](https://jamesheathers.curve.space/) is a free online book by James Heathers (2025) that provides a comprehensive introduction to forensic meta-science techniques — methods for checking the consistency and credibility of scientific reports.

The book is written in a literate programming style, with all analyses implemented in R code that readers can run themselves. It covers techniques ranging from simple consistency checks to more sophisticated statistical tests, along with visual analysis methods for detecting image manipulation.

### Citation

Heathers, J. (2025). An Introduction to Forensic Metascience. doi: [10.5281/zenodo.14871843](https://doi.org/10.5281/zenodo.14871843)

## Topics covered

The book walks through a progression of techniques for evaluating the consistency of reported results in scientific papers:

| Topic | Description |
|-------|-------------|
| **Basic consistency checks** | Verifying that percentages sum correctly, internal consistency of reported numbers |
| **GRIM** | Granularity-Related Inconsistency of Means — determines whether a reported mean is mathematically possible given the sample size and integer data |
| **GRIMMER** | Extension of GRIM to standard deviations, based on the principle that (degrees of freedom x variance) + (n x mean squared) must be a whole number |
| **SPRITE** | Technique for reconstructing possible distributions consistent with reported summary statistics |
| **Image forensics** | Visual analysis techniques for detecting manipulated images, duplicated Western blots, and other figure anomalies |
| **Triage** | Deciding which papers warrant deeper investigation |
| **AI in forensic meta-science** | The potential role and limitations of automated analysis |

## Who is it for?

The book is intended for anyone interested in evaluating the credibility of scientific research, including researchers, research integrity officers, ethics committees, journalists, and aspiring forensic meta-analysts. No prior expertise in forensic meta-science is required, though some familiarity with R is helpful for running the code examples.

## Resources

- [Read the book](https://jamesheathers.curve.space/) — full text, freely available (CC-BY-4.0)
- [DOI: 10.5281/zenodo.14871843](https://doi.org/10.5281/zenodo.14871843) — archived on Zenodo
- [Book announcement](https://jamesclaims.substack.com/p/i-have-written-you-a-book-on-forensic) — Heathers' Substack post introducing the book
