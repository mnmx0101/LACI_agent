# Context-Specific Limitation Review

Use this to compare known model limitations against the current analysis environment.

| Known limitation | Source | Current condition present? | Geography/time affected | Implication for this use case | Action |
| :--- | :--- | :--- | :--- | :--- | :--- |
|  |  | Yes / No / Unknown |  |  | Consider / constrain / reassess / do not consider |

## Required Checks

- **Performance relevance:** Does the reported performance apply to this geography, time window, and prediction horizon?
- **Training-context match:** Are current conditions represented in the training or validation data?
- **Unaccounted factors:** Are there current shocks or data conditions the model does not account for?
- **Threshold implication:** If a threshold, alert, probability, score, or anomaly is used, what does it mean for IPC interpretation?
- **Spatial/temporal fit:** Does the output unit align with the IPC analysis unit and time window?
