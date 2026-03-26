---
title: "GRIM"
date: 2025-02-16
draft: false
summary: "Granularity-Related Inconsistency of Means — tests whether reported means are mathematically possible given the sample size."
tags: ["consistency-testing"]
categories: ["means", "sample-sizes"]
methods_id: "grim"
year_introduced: 2016
---

## GRIM (Granularity-Related Inconsistency of Means)

The GRIM test checks whether a reported mean is mathematically consistent with the reported sample size, assuming integer-valued data. For example, if a study reports a mean of 1.47 for 20 participants on a Likert scale, GRIM checks whether any combination of 20 integers can produce exactly that mean.

## Tools implementing GRIM

- [scrutiny](/tools/scrutiny/) — R package
