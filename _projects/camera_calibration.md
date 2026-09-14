---
layout: page
title: Automated Single-Camera Calibration
description: Learned 3D priors estimate full camera intrinsics and extrinsics per camera — removing the manual correspondence step from bringing a site online.
importance: 5
category: work
permalink: /projects/camera-calibration/
---

**Derq · Dubai, UAE** &nbsp;·&nbsp; Senior Machine Learning Engineer — research lead
&nbsp;·&nbsp; 2025 — Present

Everything an intersection perception stack reports in world coordinates depends on knowing where
its cameras are and how they see. That calibration has conventionally been produced by a person
selecting corresponding points by hand, per camera, per site — accurate enough, but manual work
that scales linearly with deployment and sits on the critical path to bringing a site online.

This work estimates **full intrinsics and extrinsics per camera** automatically, removing the
manual correspondence step for the applications that can accept it.

## Approach

The effective method here is not classical geometry but **learned 3D priors** — models such as
Perspective Fields that estimate geometric properties directly from a single image. Classical
estimation depends on structure being present and identifiable in the scene: vanishing points,
known parallel lines, planar patterns. Intersection cameras frequently do not oblige, and when the
required structure is absent or ambiguous the classical route degrades sharply. A learned prior
makes no such demand of the scene, which is what makes it viable across an unselected population of
deployment sites.

## Validation

Validated against ground-truth calibration data, so accuracy is measured directly rather than
inferred from proxies such as reprojection consistency.

**Tech stack** — Python · PyTorch · Camera geometry · Camera parameters
