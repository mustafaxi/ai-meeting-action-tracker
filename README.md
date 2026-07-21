# AI Meeting Assistant & Action Tracker
**Candidate:** Mustafa Osama Zaki | **Role:** AI Agent & OpenClaw Research Intern

---

## 1. Stack
- **UI:** Streamlit (Python)
- **AI/Extraction:** Gemini API (Structured JSON)
- **Data & Audit:** Pandas, Datetime

---

## 2. Workflow
1. **Input:** Paste transcript.
2. **Extract:** LLM parses `executive_summary`, `key_decisions`, and `action_items` (task, owner, deadline).
3. **Guardrail:** Flag all outputs as `⚠️ Pending Human Review`.
4. **Log:** Append run metadata to system audit trail.

---

## 3. Real vs. Simulated
- **Real:** LLM parsing, JSON validation, Streamlit UI, and live audit logging.
- **Simulated:** Downstream API dispatches (Slack/Email/Jira).

---

## 4. Risks & Limitations
- **Ambiguity:** Vague transcripts can cause hallucinated task owners.
- **Context Length:** Long meetings require text chunking.
- **Implicit Dates:** Relative deadlines ("next week") need normalization.

---

## 5. Safety Guardrails (Human-in-the-Loop)
- **State Lock:** Outputs default to `Pending Human Review`.
- **Zero Auto-Dispatch:** Disables automatic webhooks to Slack/Email.
- **Approval Gate:** Requires explicit human validation before sending data to external tools.
