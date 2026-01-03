# TTX-SEC-2026-01 — API Key Exposure Incident

## 1. Scenario Description

A production-grade API key used for AI-assisted operations is suspected to have been exposed via a local development environment or shell misconfiguration.

The system must respond under the assumption that:

* The key may already be compromised
* Abuse may not yet be visible
* Regulatory exposure is possible

---

## 2. Trigger Event

A developer detects inconsistent authentication behavior followed by a 401 error and identifies that an API key may have been exposed in a local shell configuration or script.

---

## 3. Assumptions

* The API key grants write access
* The environment is connected to production resources
* Logs may be incomplete
* No external confirmation of abuse exists at trigger time

---

## 4. Roles and Authority Mapping

* **Incident Commander (IC):** Security Architect
* **Key Authority:** Organization Owner
* **Audit Authority:** Governance Layer
* **Observer:** Compliance / GDPR Oversight

No role may exceed documented authority.

---

## 5. Decision Points

1. Is this a confirmed incident or a precautionary response?
2. Should the key be revoked immediately?
3. Is system downtime acceptable?
4. Is regulatory notification required at this stage?

---

## 6. Expected Actions

* Immediate revocation of the suspected key
* Generation of a replacement key
* Rotation of dependent services
* Verification of usage logs
* Preservation of evidence

---

## 7. Observability and Evidence Produced

* API key lifecycle logs
* Timestamped revocation record
* Access attempt logs
* Redacted configuration snapshots

---

## 8. Gaps Identified

* Lack of automated key rotation
* Insufficient local environment isolation
* Manual dependency on shell configuration

---

## 9. Risk Ownership Assignment

* **Risk Owner:** Security Architecture
* **Mitigation Owner:** DevOps / SecOps
* **Review Authority:** Governance Layer

---

## 10. Post-Exercise Governance Actions

* Enforce Keychain-based secret storage
* Prohibit plaintext keys in shell files
* Introduce automated rotation policy
* Update developer onboarding standards

---

## Final Statement

This TTX validates the organization’s ability to:

* Act decisively under uncertainty
* Preserve evidence
* Maintain governance integrity under pressure
