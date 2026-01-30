# The 7 mandatory deliverables for any GenAI pilot

A GenAI pilot is not “a demo with real data.” A pilot is the first time an organisation is tempted to treat the system as real. These seven deliverables exist to prevent the two classic outcomes:

1) You can’t prove it works (or that it keeps working).  
2) It works until it doesn’t, and then you can’t explain what happened.

Each deliverable removes a specific category of risk. If a vendor can’t produce them (or you can’t produce them internally), you are not piloting GenAI—you are gambling.

---

## 1) Evaluation harness

**What it is**  
A repeatable way to test the system against a representative set of tasks, with scoring and “go/no-go” gates. It is not a one-off demo script.

**Why it exists**  
GenAI systems fail gradually and silently: prompt tweaks, data updates, model changes, and retrieval changes drift output quality. Without a harness you can’t tell whether a change improved anything—or just moved the failure elsewhere.

**Minimum contents**
- **Test set:** curated prompts/tasks reflecting the real domain (including edge cases).
- **Expected outcome:** not always a single “correct answer,” but at least a rubric or constraints.
- **Scoring:** automated where possible (exact match, structured checks), human/rubric where needed.
- **Pass/fail gates:** explicit thresholds (e.g., “≥80% useful,” “≤1% critical errors,” “0 policy breaches”).
- **Repeatability:** versioned dataset + versioned prompts/config + repeatable run command.

**Done when**  
You can run it in one command, get a scored report, compare to last run, and make a decision.

**Common anti-patterns**
- “We’ll evaluate in UAT.”
- Test set is all happy-path; no negatives or adversarial cases.
- No gates—only “it looks better.”

---

## 2) Failure taxonomy

**What it is**  
A structured way to describe how the system breaks in *your* domain, with severity and examples.

**Why it exists**  
If you can’t name failures, you can’t reduce them. If you can’t prioritise them, you’ll fix cosmetic issues while critical failures remain.

**Minimum contents**
A table with at least:
- **Failure category** (e.g., hallucination, wrong source, missed constraint, unsafe advice, policy violation, refusal/over-refusal)
- **Severity** (minor / major / critical, with criteria)
- **Examples** (real outputs from your tests)
- **Detection method** (harness metric, heuristic, human review)
- **Likely mitigations** (prompting, retrieval changes, constraints, escalation)

**Done when**  
Every failing test case in the evaluation harness maps to a taxonomy category and severity.

**Common anti-patterns**
- A taxonomy that reads like generic AI theory rather than your actual failure data.
- No severity levels, so everything becomes “a bug.”

---

## 3) Traceability / provenance approach

**What it is**  
A documented approach to answering: **“What sources were used to produce this output, when, and how?”** This applies to both the data and the model/system configuration.

**Why it exists**  
In enterprise and regulated environments, you must be able to defend outputs. If a user asks “why did it say that?” you need more than “the model did it.”

**Minimum contents**
- **Source identification:** what documents/records are eligible, and what is excluded.
- **Retrieval trace (for RAG):** document IDs, versions, timestamps, chunk references, retrieval parameters.
- **Model/config trace:** model name/version, prompt version, tool versions, retrieval index version.
- **Citation format:** how the system references sources (links, footnotes, doc IDs).
- **Update process:** how sources are refreshed and how changes are tracked.

**Done when**  
Given any output, you can reconstruct: the input, the retrieved sources (if any), the system configuration, and the versions involved.

**Common anti-patterns**
- “We cite sources” but citations are not reproducible (no IDs, no versions).
- Index refreshes overwrite history so you can’t reproduce yesterday’s answer.

---

## 4) Logging and “what becomes a record” decision

**What it is**  
A clear policy and implementation for what is logged, what is retained, who can access it, and what is considered an official record.

**Why it exists**  
If something goes wrong, you will be asked what happened. If you can’t answer with logs, the conversation becomes opinion and blame. In government/regulated contexts, recordkeeping is not optional.

**Minimum contents**
- **Event list:** what you log (inputs, outputs, tool calls, retrieval metadata, errors, latency/cost).
- **Record policy:** what becomes an official record vs ephemeral telemetry.
- **Retention:** how long logs are stored; deletion rules.
- **Access controls:** who can view logs; audit access.
- **Privacy handling:** treatment of PII/sensitive data; redaction strategy (if any).
- **Correlation IDs:** ability to trace a single interaction across components.

**Done when**  
You can answer: “Who asked what, what did the system do, what data did it touch, what did it output, and what actions occurred?”

**Common anti-patterns**
- Logging is “whatever the vendor platform does by default.”
- Logs exist but can’t be searched or correlated.
- No decision on retention → panic later.

---

## 5) Red-team plan

**What it is**  
A planned set of adversarial tests targeting realistic abuse and failure modes: prompt injection, data leakage, unsafe outputs, policy bypass, tool misuse, and boundary violations.

**Why it exists**  
Red-teaming is how you discover failures you didn’t think to test—especially in safety/security. A “pilot” without red-teaming is an incident waiting for a user with curiosity and time.

**Minimum contents**
- **Scope:** what you are testing (data, prompts, tools, integrations, roles).
- **Threat scenarios:** domain-specific cases (not generic jailbreak memes).
- **Success criteria:** what counts as failure (severity rubric).
- **Execution plan:** who runs it, when, and with what access.
- **Reporting format:** findings, severity, reproducibility, recommended mitigations.
- **Re-test requirement:** fixes must be verified before expanding use.

**Done when**  
You have documented findings and you’ve either mitigated them or accepted residual risk explicitly.

**Common anti-patterns**
- Red-team happens after stakeholders are already committed.
- Only tests “model jailbreaks” and ignores data leakage and tool misuse.

---

## 6) Cost / latency guardrails

**What it is**  
Defined and enforced limits on how expensive and how slow the system is allowed to be, plus behaviours when limits are hit.

**Why it exists**  
GenAI systems are easy to make impressive and hard to make predictable. Cost blowouts and latency spikes are normal unless controlled.

**Minimum contents**
- **Budget model:** estimated cost per request and per user/day; worst-case scenario.
- **Latency targets:** acceptable response times for the workflow.
- **Runtime enforcement:** token caps, timeouts, max tool calls, max context size.
- **Fallback behaviour:** what happens when limits are hit (shorter answer, clarification, downgrade model, defer to human).
- **Monitoring:** dashboards/alerts for spend and latency.

**Done when**  
The system cannot exceed your defined ceilings without you noticing—and it degrades gracefully when it hits them.

**Common anti-patterns**
- Cost is “someone else’s problem” until the invoice arrives.
- Latency is measured only on the best-case happy path.

---

## 7) Handover kit

**What it is**  
A package that allows another competent team (internal or external) to run, evaluate, and continue the work without vendor lock-in or tribal knowledge.

**Why it exists**  
If you can’t take over the pilot, you don’t own it. If you don’t own it, you are buying dependency.

**Minimum contents**
- **Repo + run instructions:** how to run locally and in the target environment.
- **Configuration:** model endpoints, prompt templates, retrieval settings, tool configs.
- **Evaluation harness:** included and runnable.
- **Architecture overview:** components, data flows, security boundaries.
- **Operational runbook:** logging, monitoring, common failure handling, rollback steps.
- **Known limitations:** explicit list of what it can’t do and unsafe use cases.
- **Decision artifacts:** results summary vs gates; recommended next step.

**Done when**  
A different team can reproduce results and continue development without “asking the original builder.”

**Common anti-patterns**
- Handover is a meeting, not an artefact.
- Critical logic is embedded in prompts in someone’s private account/workspace.

---

## Optional: one-line acceptance criteria (for the checklist)

- [ ] **Evaluation harness:** runnable and produces a scored report with pass/fail gates.
- [ ] **Failure taxonomy:** every failing test case maps to a category and severity.
- [ ] **Provenance:** outputs can be traced to specific sources/config versions.
- [ ] **Logging/record:** you can reconstruct an interaction end-to-end with retention rules.
- [ ] **Red-team:** documented findings + mitigations + retest.
- [ ] **Cost/latency:** enforced ceilings + defined fallback behaviours.
- [ ] **Handover:** another team can reproduce and continue.