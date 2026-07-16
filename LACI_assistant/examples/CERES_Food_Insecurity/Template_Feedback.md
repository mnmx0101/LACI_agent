# Template Feedback v2 - CERES Probabilistic Early Warning System

## What This Stress Tests

CERES stress-tests the LACI Assess Card more sharply than the flood or AMN models because it directly outputs IPC-like probabilities and alert tiers. The main issue is not whether the architecture is interesting; it is whether an IPC-facing workflow can tolerate a model that has not yet demonstrated prospective calibration.

## What Worked

- The Special Rule clearly triggers.
- The B1a/B1b performance structure is useful because it distinguishes in-sample sanity checks from prospective performance.
- The Suggested Use Guide can explicitly separate experimental monitoring from IPC evidence use.

## Template Stress Points

- The template may need a specific prompt for `prospective vs retrospective/in-sample validation`.
- It may need a prompt for `commercial interest / governance / independent review` where a model is offered by a private vendor.
- IPC-like probability outputs need particularly strong non-communication rules.

## Proposed Refinement

Add to the template guidance: when a model directly estimates IPC phases or IPC-like probabilities, the Assess Card must state whether performance is prospective, retrospective, in-sample, out-of-sample, or merely planned.


