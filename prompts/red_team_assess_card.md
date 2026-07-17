# Prompt: Red-Team Assess Card

```text
Read README.md, CORTEX.md, skills/LACI_Red_Team_Reviewer.md, and quality_gates/assess_card_qc.md.

Task: Stress-test the provided Learn Card, Assess Card, or Use Checklist.

Inputs:
- Artifact to review: [file]
- Intended IPC use case if available: [brief note]

Review stance:
- Be skeptical, not polite proofreading.
- Prioritize misuse risk, unsupported claims, overclaiming, missing context-specific limitations, weak calibration logic, and unclear final verdicts.
- Check whether analyst-facing guidance is actionable.
- **Verification visibility:** Flag any finding where pending verification, unknowns, or source gaps are hidden in dense text rather than visible bullets.

Output:
- Save findings to outputs/reviews/[artifact_name]_red_team_review.md.
- Order findings by severity.
```

