# Senate ↔ Xenia (The Hearth)

Xenia is the constellation's **customer-support Hearth** — now an **active**
Hydra squad (`customer-support`), an 11-agent crew that triages tickets,
recommends responses, mines Voice-of-Customer, and executes only behind an
approval gate (WS-AUTH capability enforcement). The Hearth answers guests;
the Senate is the **legal-review depth** behind its compliance gate.
Advisory relationship — the Senate never holds up a ticket directly; it
supplies counsel when a response crosses into regulated territory.

## The seam — regulated claims in support responses

Xenia's policy-and-compliance agent, **Eunomia**, enforces a hard rule:
regulated claims (financial / medical / legal) ship in **pre-approved
language only**; anything improvised is a **block + escalation referral**
(`regulated_claims: BLOCKED`). That referral is where the Senate begins.
The Hearth knows *that* a response is regulated; the Senate decides *what
may lawfully be said*.

Typical escalations (Xenia → Senate):

- **Regulated-claim language** — a support reply that would assert a
  financial, medical, or legal outcome → Ulpian
  (`/legal-opinion regulatory-counsel <draft response + context>`) to
  confirm substantiation, required disclosures, and approved phrasing.
- **Consent / data-subject mechanics** — deletion, access, or
  retention promises made to a customer in-channel → Angerona
  (`/privacy-assess`), so a well-meant assurance does not become an
  unbacked legal commitment.
- **Contractual commitments** — a response that touches SLA credits,
  warranty scope, or refund entitlements beyond policy → Gaius, to map
  the reply against the governing paper.

## Return contract

The Senate returns a DECISION_RECORD with claim-by-claim verdicts
(supported / needs-substantiation / barred), the approved disclosure or
referral language drafted for the channel, and regime citations (verified
per Table III). Xenia attaches it to the ticket record; the response then
flows back through the Hearth's own approval gate (WS-AUTH) before send —
the Senate counsels, Xenia's gate executes. HITL-grade findings ride the
Tribune's Veto.

## Boundary

Xenia owns the **relationship** (tone, retention, de-escalation, the
guest's experience); the Senate owns only the **lawfulness layer**. A
legally clean reply can still be the wrong thing to say to an upset
customer — that is Harmonia's and Soteria's call, not the Curia's. And a
warm, on-brand reply that promises a regulated outcome is still barred
until the Senate clears the words.

## Wiring

No code dependency either direction. In Hydra, multi-squad routing handles
tickets that need both (a support matter with a regulated-claim or
data-rights question fingerprints `customer-support` + `legal-compliance`).
Standalone, the human carries the flagged draft across. Both squads now
enroll in AgentMesh (`integrations/agentmesh.md`); the control plane can
route the referral, but the Hearth's approval gate and the Tribune's Veto
remain the only authorities that release anything.
