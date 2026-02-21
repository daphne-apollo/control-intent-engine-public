# Control Intent Engine — Demo Walkthrough

This walkthrough demonstrates how governance expectations emerge from **system characteristics**, rather than from framework checklists or policy assertions.

The goal is not to show tool features.  
The goal is to show a different way of reasoning about governance.

---

## Demo goal

Show that:

- governance logic can be expressed explicitly as **intents**
- applicability is determined by **system reality**
- frameworks are **projections**, not drivers
- outputs are **explainable and reproducible artifacts**

---

## Demo scenario (conceptual)

We will reason about a representative system with the following characteristics:

- A cloud-hosted application
- Handles customer or internal business data
- Uses automation and service identities
- May incorporate AI-assisted capabilities (e.g., retrieval or decision support)

Participants do **not** answer framework questions.
They describe the system as it exists (or is planned).

That description is translated into a structured intake profile.

---

## Step 1: Describe the system (no framework language)

The intake captures facts such as:

- How identities are used (human vs service)
- Whether access is provisioned dynamically
- Whether data is sensitive or regulated
- Whether external content is retrieved
- Whether automated actions are taken

Importantly, the intake does **not** ask:
- “Do you meet ISO control X?”
- “Is this SOC 2 compliant?”

It captures **system truth**, not compliance posture.

---

## Step 2: Explain governance logic explicitly

Before evaluating anything, we can inspect the governance logic itself.

```bash
cie explain-activation <INTENT_ID>
```

---

## Step 3: Evaluate which governance intents apply

```bash
cie map-intents
```

The engine evaluates the intake and produces three classes of outcomes:
- Activated — governance expectations that clearly apply
- Not applicable — conditions are not present
- Inconclusive — required context is missing

Missing information is surfaced explicitly.
Unknowns are treated as first-class results, not silent assumptions.

---

## Step 4: Generate a governance report

```bash
cie report --out demo-report.md
```

The report includes:
- a timestamp (generated_at)
- an input fingerprint (profile_hash)
- the activated governance intents
- a framework impact summary

This produces a defensible artifact that answers:
“What governance logic applied, when, and based on what inputs?”

---

## Step 5: Trace a framework requirement

```bash
cie trace "5.18"
```

This answers a common audit question:
“Why does this control apply to this system?”

The answer is not:
“Because the framework says so”

The answer is:
“Because governance intent X@version determined it applies, given these system characteristics.”

This is traceable, explainable governance reasoning.
