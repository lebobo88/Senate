---
name: litigation-playbook
description: "Cicero's kit — claim triage with deadline discipline, elements-vs-evidence method, privilege handling and litigation holds, procedural posture mapping, settlement decision trees with shown EV math, and e-discovery scoping basics."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Litigation Playbook

## Claim Triage (incoming matter, first hour)

1. **Clocks first**: limitation periods, response deadlines (answer/motion
   dates), contractual notice periods, insurer notice windows. Unknown
   deadline ⇒ `[DEADLINE UNCONFIRMED — calendar with local counsel]`,
   conspicuously.
2. **Hold trigger**: litigation reasonably anticipated ⇒ hold notice now
   (template below).
3. **Severity tier**: exposure range × injunction risk × publicity ×
   precedent effect.
4. **Forum & law**: where filed/threatened, governing law, arbitration
   clause check (Table VIII).

## Elements-vs-Evidence Method

For each claim/defense:

```
| Element | Their burden? | Our evidence | Their evidence (assume competence) | Gap |
```

Rules: every element rows out — silence on an element is how cases get
lost; evidence is named (document, witness, record), not characterized;
gaps marked `[EVIDENCE NEEDED: ...]` become the investigation plan;
**steel-man discipline** — fill the opponent's column as their best
lawyer would.

## Privilege Handling (feeds privilege-handling@1)

- **Channels**: privileged analysis stays in privileged channels; artifacts
  carry the work-product banner (`curia-protocol` header) with
  *anticipation-of-litigation* invoked expressly for disputes.
- **The mixed-purpose trap**: business advice ≠ legal advice — documents
  serving both get privilege challenged; write legal analysis separately.
- **Waiver hygiene**: distribution lists minimal; third parties
  (consultants) only under Kovel-style/common-interest arrangements —
  flag, don't improvise.
- **AI-specific**: matter content does not leave the matter's scope
  (Tables I, X); no privileged facts into broader memory scopes.

### Litigation-Hold Notice Skeleton

To: custodians (named) · Subject: Preserve documents — [matter] ·
Suspend auto-deletion for [scopes/systems] · Preserve [date range, data
types incl. chat/mobile] · No deletion, alteration, or "cleanup" ·
Questions to [owner] · Acknowledgment required by [date].

## Procedural Posture Mapping

```
Current posture → next 3 decision points, each with:
  option | cost | time | win-probability shift | information gained
```

Standard arcs: pre-suit (demand/respond/standstill) → pleadings (motion to
dismiss calculus: win% vs. educating the opponent) → discovery (scope
fights, proportionality) → dispositive motions → trial/arbitration.
Arbitration variants noted (limited appeal, confidentiality, speed).

## Settlement Decision Tree (EV math shown)

```
EV(litigate) = Σ [P(outcome_i) × value_i] − costs_to_resolution − distraction_cost
EV(settle now) = offer − immediate_costs

Example:
  P(win at trial) 55% × $0 owed + P(lose) 45% × −$2.0M = −$900k
  − defense costs to verdict −$600k − management distraction −$150k
  = EV(litigate) ≈ −$1.65M  → a $1.2M settlement is rationally acceptable.
```

Rules: probabilities from the elements-vs-evidence table, not optimism;
ranges not points where uncertainty is high (state both bounds); precedent
and signal effects priced explicitly (settling fast can buy more suits);
BATNA stated; **recommendation ≠ authority** — settlement authority is
human (Table VI).

## E-Discovery Scoping Basics

Custodian list (ranked) · data sources (email, chat, devices, SaaS
exports) · date ranges · search-term protocol (iterate with sampling) ·
proportionality positions · privilege-review workflow with clawback
agreement (FRE 502(d)-style where available).

## Required Logging

Deadline table (always first) · hold issued? to whom, when · elements
table coverage · tree assumptions and probability sources · privilege
banner verified on every artifact. Feeds Case Assessment Format
(`curia-protocol` §5).
