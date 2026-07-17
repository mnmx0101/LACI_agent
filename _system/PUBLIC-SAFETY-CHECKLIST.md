# Public Safety Checklist

Run this before committing, sharing, or publishing LACI_agent updates.

## Must Pass

- [ ] **No confidential IPC analysis:** No restricted analysis results, unpublished country material, or sensitive partner inputs.
- [ ] **No private operational data:** No private current-run notes, restricted model outputs, or non-public data extracts.
- [ ] **No local machine paths:** Replace local absolute paths with repo-relative links.
- [ ] **No internal workspace references:** Remove private workspace references that should not appear in the public repo.
- [ ] **Raw and outputs are placeholders:** `raw/` and `outputs/` should contain README files, `.gitkeep`, or public-safe examples only.
- [ ] **Technical claims are verified or labeled:** Claims needing model-builder confirmation are marked as draft/unverified until confirmed.
- [ ] **IPC role language is diplomatic and precise:** The repo remains strict procedurally without implying that external partners are being judged outside agreed review channels.
- [ ] **Non-replacement rule is intact:** No text implies model outputs replace IPC consensus-based outcome classification.
- [ ] **Links work:** Relative markdown links resolve inside the repo.

## If Any Box Fails

Do not commit or publish the affected file. Move the content to local private storage, redact it, or convert it into a public-safe placeholder.
