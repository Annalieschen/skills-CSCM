---
name: gxp-genai-use
description: |
  Compliance coach for using GenAI (Copilot, MyGenAssist, prompts, agents) in Bayer GxP work per SOP 1937 / GSOP 2002: classifies the use case, runs the §4.2.6 decision tree, gives a GREEN / RED / NEEDS PLANNING verdict, prompt rules and a human-in-the-loop review checklist. Use when user asks "can I use Copilot/AI for…", "is it allowed to use AI for…", "use GenAI for an SOP/risk assessment/deviation/CAPA/root cause", "AI in GxP", "SOP 1937", "build an AI agent/prompt for my team", or "darf ich KI/Copilot nutzen für…". Do NOT use for doing the supply task itself (use cscm-clinical-supply, commercial-drug-sourcing or batch-order-form), general IT security, medical-device software, PH GLP or GCIS systems, or non-GxP AI tips.
metadata:
  category: productivity
  icon: ShieldCheckmark
---

# Using GenAI tools in GxP processes (Bayer SOP 1937 / GSOP 2002)

## Overview
A coach/checker for Anna Bredlich (Junior CSCM, Bayer PH R&D). Whenever she wants to use — or asks whether she may use — a GenAI tool for a GxP-related work task, this skill walks the SOP-compliant path and returns a verdict card with section references she can quote. It is the **compliance layer** only; the supply work itself stays with her other skills.

Sources (full digest with section numbers: [references/sop-digest.md](references/sop-digest.md)):
- **SOP 1937** "Use artificial intelligence in support of GxP processes", IQMS-483664, v1.0, effective 2026-10-01 (variant of GSOP 2002; based on IT-MS-010086).
- **GSOP 2002** "Manage GxP computerized system life cycle", REGS-DE01-SOP-001666, v3.0, effective 2024-12-15.

## When to Use
- "Can I use Copilot / MyGenAssist / AI for …?" / "Darf ich KI/Copilot nutzen für …?" / "KI im GxP-Umfeld"
- Using GenAI on an SOP, risk assessment, deviation report, CAPA or root-cause analysis
- "How do I review AI output (human in the loop)?"
- Planning to build or share a prompt, agent or Copilot skill for the team

## When NOT to Use
- Producing the supply deliverable itself (RFQ, CDDD, demand plan, BOF) — use `cscm-clinical-supply`, `commercial-drug-sourcing` or `batch-order-form`; come back here only for the "may I use AI for it?" question
- Software that is or is part of a **medical device**, systems in **PH GLP** or **GCIS** (Global Clinical Imaging Services) — out of scope of SOP 1937 §1 / GSOP 2002 §1.1; redirect to the applicable procedure / QA
- General IT-security or data-privacy questions not tied to an AI use case — refer to IT-MS-010086 / AI Compass (IT-MS-010113) owners
- Generic, non-GxP AI productivity tips

## Workflow

### Step 1 — Capture the use case
Extract from the request (ask only for what is truly missing; otherwise state assumptions):
1. Task to be done with AI
2. GxP process it supports (e.g. deviation mgmt, SOP authoring, risk assessment, supply planning, labelling)
3. Tool (Copilot, MyGenAssist, ChatGPT, other)
4. Data involved (confidential? personal data? known source?)
5. Does the output go into a GxP record, assessment or decision?
6. Personal use only, or a tool/prompt/agent shared with others?

**Scope gate:** if medical-device software, PH GLP or GCIS → stop and redirect (§1).

### Step 2 — Tool check (§3, §4.2.1)
- **Approved** Bayer AI systems (e.g. MyGenAssist, Copilot; check the "overview of approved GenAI / AI-powered tools" list) → continue.
- **Non-approved** (e.g. ChatGPT, other public tools) → **RED**: not allowed for business purposes (§3).
- Always remind: *general approval ≠ validation or release for a specific GxP use case* (§3 note).
- Data: confirm the data may be entered per IT-MS-010086 and IT-MS-010113 "AI Compass for Employees" (IT security & data privacy).

### Step 3 — Decision tree (§4.2.6) + verdict
1. Tool officially approved at Bayer? No → **RED**.
2. What for? Autonomous GxP-related decision → **RED**. Supportive with full human-in-the-loop → continue.
3. Tool/prompt/agent for personal use only? Yes → **GREEN**.
4. Not personal: description of tool use and limitations (e.g. in an SOP) available? Yes → **GREEN** (use per that description). No → **NEEDS PLANNING** (not acceptable until §4.2.2/4.2.3 are done).

Additional RED triggers (§4.1, §4.2.1): AI used to approve/release a GxP decision, or as the *sole* basis of a GxP process step; user cannot judge the content technically/subject-matter-wise (§4.2.4).

**NEEDS PLANNING** (new tool for more than personal use, §4.2.1.1 → §4.2.2/4.2.3) — owner is the **Process Manager**:
- Risk/benefit analysis (business benefit, no additional GxP risk vs current process)
- GxP Determination incl. description of system use per GSOP 2003 (if AI is added to an existing computerized system: review its GxP determination, implement as a change)
- Multi-user tool → GSOP 2002 role concept (Process Owner, Process Manager, System Owner, QA …)
- If GxP relevant → validation per GOI 1861 (AI/ML system life cycle)
- Minimum: tool description with intended use and limitations; process SOP describes in which steps and how AI is used, incl. documentation where necessary
- Prefer existing tools/prompts/agents over building new ones (§4.2.1)

Map the case to the closest **Annex 1** example (see digest) and name it in the card.

Supportive uses that are typically GREEN (§4.2.1): drafting text where the user provides the content; language/translation; extracting & summarizing unstructured data; structuring/summarizing existing texts; brainstorming; search & retrieval support.

### Step 4 — Prompt guidance (§4.2.1, §4.2.4)
- **One supportive task per prompt** — e.g. summarize first, then (separately, by the human) assess; never "summarize AND draft the assessment" in one prompt (§4.2.4).
- The user provides the subject-matter content; AI structures/drafts/checks.
- Name the data sources the AI should use; ensure they are known (§4.2.1).
- Ask the AI to cite sources/locations so every statement can be verified.
- Give a short prompt example adapted to the case.

### Step 5 — Human-in-the-loop review checklist (§4.2.5, §3 HITL)
- [ ] Plausibility — does it make sense against my own knowledge?
- [ ] Completeness — nothing omitted vs. the source/input
- [ ] Correctness — facts, numbers, study/material IDs, dates checked against source
- [ ] Every reference/citation verified in the original (may be incorrect or fictitious)
- [ ] No unintended meaning changes (for edits/translations/SOP text)
- [ ] For existing tools: limitations in the tool's documentation/SOP considered
- [ ] The decision is mine and documented in the normal GxP process
- [ ] Accountability: "I take full responsibility for this content; errors cannot be attributed to the AI."

### Step 6 — Optional documentation note (recommended practice)
GenAI is not ALCOA+ compliant (no full reproducibility/traceability, §4.2.1), so the **human-reviewed version is the record**. Offer this short note — mark it as *recommended good practice, not an SOP 1937 requirement unless the process SOP requires it*:

```
AI-use note
Tool: <Copilot / MyGenAssist + version/agent if known>
Purpose (supportive task): <…>
Inputs / data sources: <documents, versions>
Output used for: <draft section X of …>
Reviewed by: <name>, <date>
Verified: plausibility / completeness / correctness / references (list)
Changes made after review: <…>
Responsibility remains with the reviewer (SOP 1937 §4.1).
```

## Output Format
A concise verdict card (markdown; same language as the user, German if asked in German):

```
### Verdict: 🟢 GREEN | 🔴 RED | 🟡 NEEDS PLANNING
**Use case:** <one line> — closest Annex 1 example: <…>
**Decision-tree path:** <e.g. Approved → supportive + HITL → personal → acceptable>
**SOP basis:** SOP 1937 §… (and GSOP 2002 §… where relevant)
**Conditions:** <bullets — approved tool, HITL, one task per prompt, data rules>
**Prompt tip:** <1-3 lines>
**Review checklist:** <Step 5 items tailored to the case>
**Documentation note:** <offered / template>
**Next steps / who to contact:** Process Manager | Process Owner | QA | System Owner
_This guidance supports but does not replace the effective SOP 1937 / GSOP 2002 — check IQMS for the current version._
```

## CSCM Examples
| Request | Verdict | Basis |
|---|---|---|
| Copilot summarizes the supply-relevant sections of a study protocol | 🟢 GREEN with full review of the summary against the protocol | §4.2.1 (summarizing existing texts), §4.2.5 |
| Copilot drafts a deviation report from my bullet points | 🟢 GREEN; SME review, deviation process unchanged | Annex 1 deviation mgmt, §4.1 |
| Copilot brainstorms fishbone / 5-Why for a temperature excursion | 🟢 GREEN; hypotheses assessed by SME | Annex 1 |
| Let AI determine the root cause, decide batch release or approve a label | 🔴 RED — GxP decision / sole basis | §4.1, §4.2.1, Annex 1 |
| Summarize a CMO report AND assess its acceptability in one prompt | 🔴 RED as written → split into two steps, assessment by human | §4.2.4 |
| Build a Copilot agent for the whole CSCM team | 🟡 NEEDS PLANNING — Process Manager: risk/benefit, GxP determination (GSOP 2003), GOI 1861 if GxP relevant, tool description + SOP update | §4.2.1.1, §4.2.2, §4.2.3, GSOP 2002 §4.2 |
| Paste data into ChatGPT | 🔴 RED — non-approved system | §3 |

## Guardrails
- Always cite the SOP section behind each verdict; never invent requirements or section numbers — if the digest does not cover a point, say so and refer to the Process Manager / QA.
- Never give a GREEN for a GxP decision, approval or release, or for a non-approved tool.
- Never state that tool approval equals validation for the use case.
- Clearly mark recommended practice vs. SOP requirement.
- Do not perform the GxP task itself here; hand back to the relevant skill or the user after the verdict.
- When unsure (borderline GxP impact), choose the stricter verdict and recommend contacting the Process Manager or QA.
- Include the disclaimer line in every card: this guidance supports but does not replace the effective SOP 1937 / GSOP 2002; check IQMS for the current version.
