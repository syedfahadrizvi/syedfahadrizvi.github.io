---
layout: page
title: Vulnerable Road User Tracking
description: Asymmetric association and a deliberately simple motion model for pedestrians and cyclists — tracking that holds up where vehicle-tuned trackers break.
importance: 4
category: work
permalink: /projects/vru-tracking/
---

**Derq · Dubai, UAE** &nbsp;·&nbsp; Senior Machine Learning Engineer — research lead
&nbsp;·&nbsp; 2025 — Present

Trackers at traffic intersections are usually tuned on vehicles, because vehicles dominate the
data and behave well. Pedestrians and cyclists — the road users the safety case actually exists to
protect — break several assumptions of that tuning at once.

## Problem Statement

- **Motion is not smooth.** Vehicle motion models assume continuous, constrained trajectories. A
  pedestrian can stop dead, reverse, or pivot between frames, and none of that violates anything
  except the model.
- **Detections are less stable.** VRU bounding boxes fluctuate far more between frames than vehicle
  boxes, which degrades any association metric that leans on box geometry.
- **Detections are lost more often.** VRUs blend into visually similar background and are
  frequently occluded by poles, signage, and other static street furniture — so tracks fragment and
  must be re-acquired rather than merely maintained.

## Approach

- **Asymmetric association.** The association metric was loosened for admitting new detections
  while kept strict for confirming established tracks. The asymmetry follows directly from the
  failure modes above: VRU tracks are fragile at birth and after occlusion, so the tracker must be
  willing to start and re-acquire them, while loose association on confirmed tracks is exactly what
  produces identity switches among people moving in groups.
- **Constant velocity, deliberately.** The motion model was held at constant velocity because VRU
  heading cannot be predicted accurately. This is the opposite of the choice that worked for
  turning vehicles, where adding heading prediction and a constant turn-rate velocity model
  measurably improved tracking. A richer motion model pays off when motion is constrained and
  actively harms when it is not — an unreliable heading estimate does not degrade gracefully, it
  produces confident predictions in the wrong direction.

## Evaluation

Measured with HOTA and IDF1 on an internally collected intersection dataset, which I collected and
curated. Public benchmarks skew toward pedestrian-dense scenes with camera geometry unlike a fixed
intersection installation, so in-domain data was necessary for the numbers to mean anything
operationally.

**Tech stack** — C++ · Python · Multi-object tracking
