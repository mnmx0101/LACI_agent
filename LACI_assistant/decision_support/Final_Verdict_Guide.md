# Final Verdict Guide

Use bullet-point reasoning from the checklist. Include performance implication, triggered limitations, allowed actions, and not-allowed actions.

## Verdict Badges

| Badge | Label | Use |
| :--- | :--- | :--- |
| ![RED - Do Not Consider](https://img.shields.io/badge/RED-Do%20Not%20Consider-dc2626) | `RED - Do Not Consider` | Output is unsuitable for this context or fails required gates. |
| ![RED - Not Suggested](https://img.shields.io/badge/RED-Not%20Suggested-dc2626) | `RED - Not Suggested` | Output should not be suggested for this IPC application/function. |
| ![ORANGE - Reassess First](https://img.shields.io/badge/ORANGE-Reassess%20First-f97316) | `ORANGE - Reassess First` | Relevant but current conditions or operational metadata require review. |
| ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) | `YELLOW - Investigation Prompt` | Can help analysts decide where to look harder. |
| ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) | `BLUE - Contextual Supporting Information` | Can support contextual interpretation with documented limitations. |
| ![GREEN - Consider As Assessed](https://img.shields.io/badge/GREEN-Consider%20As%20Assessed-16a34a) | `GREEN - Consider As Assessed` | All gates pass for the defined use case. |
| ![GRAY - Not Applicable](https://img.shields.io/badge/GRAY-Not%20Applicable-6b7280) | `GRAY - Not Applicable` | Output does not apply to the proposed IPC application/function. |

## Required Final Verdict Structure

- **Decision:** Use one badge and one plain-text verdict label.
- **Reasoning From Checklist:** Summarize the checklist findings in bullets.
- **Allowed:** State exactly what analysts may do with the output.
- **Not Allowed:** State exactly what analysts may not do with the output.
- **Owner:** The IPC Analyst issues the case-specific final verdict for the defined use case, with IPC-GSU and IPC-LACI Team support as needed.

## Interpretation Rule

The badge is a visual aid, not a shortcut. The final verdict must still be justified against the current analysis environment, known model limitations, operational note, spatial/temporal fit, threshold/signal meaning, and population/20 percent compatibility where relevant.
