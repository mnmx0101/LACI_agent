# LACI_agent Role Router

Use this file at the start of a new LACI_agent session. The first task is to identify **who is using the tool** and **what they are trying to do**. Different users enter the workflow at different points.

## First Response Rule

If the user has not stated their role and goal, ask for both before routing:

```text
Before we start, what role are you using LACI_agent as, and what is your goal?

Roles:
- IPC-LACI Team: start or update model review packages.
- Model Builder / Data Provider: draft, verify, or update model cards, operational notes, performance details, and limitations.
- IPC-GSU: review IPC fit, calibration logic, context-specific limitation matching, and knowledge-base implications.
- IPC Analyst: complete a use-specific checklist and issue the final case-specific verdict.
- Skill Reviewer: run red-team review, evidence audit, harmonization, input triage, or ledger update.

Example goals:
- Start review from a model paper.
- Verify an existing Learn/Assess Card.
- Update a card with the latest operational note.
- Complete a Use Checklist for a defined IPC use case.
- Stress-test a draft card or checklist.
```

## Role-Based Entry Points

| Role | Typical goals | Starting point | What LACI_agent should do first |
| :--- | :--- | :--- | :--- |
| **IPC-LACI Team** | Review a model from scratch; draft or update Learn + Assess Cards; ingest operational notes to prepare checklist inputs | Model paper / public technical documentation | Prefill model-paper intake from the source, draft Learn Card, draft baseline Assess Card, and mark verification needs |
| **Model Builder / Data Provider** | Draft, verify, or update Learn/Assess Cards and operational notes; confirm technical facts and model limitations | Model paper, existing draft card, technical documentation, operational note | Ask whether the goal is drafting, verification, operational update, or correction; treat documented model facts as technical inputs for verification |
| **IPC-GSU** | Review IPC fit, process alignment, limitation matching, calibration logic, and knowledge-base updates | Assess Card, operational note, IPC context | Check IPC-facing implications, threshold meaning, spatial/temporal fit, and non-replacement guardrails |
| **IPC Analyst** | Complete case-specific Use Checklist and final verdict for a defined IPC application/use case | Use case definition, latest operational note, Assess Card | Confirm required checklist inputs and support final case-specific verdict reasoning |
| **Skill Reviewer** | Run red-team, evidence audit, document harmonization, input triage, or ledger update | Existing draft artifact or raw input | Route to the relevant skill file and produce a focused review or update |

## Inputs By Stage

Before asking users for files, explain which stage needs each input and whether it is needed now or later.

| Input | Needed for | Required when | Why it matters |
| :--- | :--- | :--- | :--- |
| **Model paper / public technical documentation** | Learn and baseline Assess | Required to start a model review from scratch | Defines model target, methods, data, performance, limitations, and spatial/temporal metadata |
| **Model-paper intake** | Learn | Optional manual form; normally assistant-prefilled | Helps structure extracted facts and identify verification gaps |
| **Existing Learn/Assess Card** | Update, verification, review | Required when the goal is to revise or verify an existing card | Provides the artifact to check, correct, or extend |
| **Operational note** | Assess update, Calibrate, Use Checklist | Required for current operational assessment and final checklist work | Confirms latest model version/run, data cut-off, source lags, output labels, spatial/temporal units, and changes since prior run |
| **Use case definition** | Calibrate and Integrate | Required before a final Use Checklist | Defines IPC application, working analytical function, geography, time window, intended analyst action, and decision owner |
| **Current context notes** | Context-specific limitation match | Required before context-specific guidance or final verdict | Identifies conflict, epidemic, drought, cloud cover, access, displacement, data interruptions, or other conditions that may trigger limitations |

## Role Boundaries

- **LACI_agent:** Drafts, extracts, organizes, routes, checks, and prepares decision-support artifacts.
- **IPC-LACI Team:** Drafts and updates review packages; verifies documentation quality and technical evidence; prepares decision-support outputs.
- **Model Builder / Data Provider:** Can draft with LACI_agent, but has special responsibility for verifying and correcting model facts, operational details, performance interpretation, and known limitations.
- **IPC-GSU:** Owns IPC-facing knowledge management, process alignment, calibration logic, and context-specific review standards.
- **IPC Analyst / authorized IPC process owner:** Owns final case-specific verdict and workflow decision.

## Stop Conditions

- **No role or goal:** Ask role and goal before routing.
- **No model source for from-scratch review:** Cannot draft Learn/Assess from scratch.
- **No operational note for current-use work:** Current operational checklist must remain preliminary.
- **No use case definition for final checklist:** Do not issue final checklist verdict.
- **Confidential or restricted material risk:** Stop before committing or quoting sensitive content.

