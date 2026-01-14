# Security & Governance Packet — MHD Platform

This packet documents how the **MHD platform** enforces security, governance, and reliability
*by architecture*, not policy alone.

It is intended for:
- Engineering leadership
- Security / platform reviewers
- Architects evaluating production readiness

This is **not a demo walkthrough**.  
It reflects **production system hardening and operational controls**.

---

## What This Packet Covers

This packet shows how the platform implements:

- Explicit trust boundaries
- Identity-first access control
- Centralized auditability
- Runtime-enforced reliability
- Change and cost governance

All artifacts are derived from a **live cloud deployment**.

---

## Contents

### 1. Security Model & Trust Boundaries
📄 **SECURITY_MODEL.md**

- Trust boundaries (browser → API → data services)
- Identity & access model
- Secrets and configuration governance
- Encryption posture
- Explicit non-goals and exclusions

---

### 2. Threat Model (STRIDE-lite)
📄 **THREAT_MODEL.md**

- Most likely abuse cases
- Threat → mitigation mapping
- Residual risk documentation
- Known tradeoffs and future controls

---

### 3. Audit Logging
📄 **AUDIT_LOGGING.md**

- Audit event schema
- Required audit events
- Storage and retention approach
- Example audit records

---

### 4. Governance Controls
📄 **GOVERNANCE_CONTROLS.md**

- Data retention & deletion
- Least privilege & separation of duties
- Configuration policy
- Change management
- Incident response triggers

---

### 5. Reliability & SRE Posture
📄 **SRE_RELIABILITY.md**

- Health vs readiness semantics
- Runtime-enforced probes
- Logging & observability strategy
- Scale-to-zero and cold start expectations
- Recovery basics

---

### 6. Architecture Overview (Executive)
📄 **ARCHITECTURE_1PAGER.md**

- What the system is
- How data flows
- Why it’s safe
- Why it scales

---

## Runtime Evidence (Screenshots)

📁 **screenshots/**

Includes:
- Container App health probes (/healthz, /readyz)
- Centralized Log Analytics queries
- Environment-scoped secrets
- Revisioned deployments
- Scale-to-zero configuration
- Resource topology

These screenshots exist to **verify claims**, not decorate documentation.

---

## How to Verify (Reviewer Checklist)

A reviewer can independently verify:

- **Centralized logging**  
  → Azure Log Analytics queries show runtime logs

- **Health enforcement**  
  → Liveness and readiness probes configured in Container Apps

- **Secrets governance**  
  → Secrets injected at runtime, not embedded in images

- **Change control**  
  → Revisioned deployments with explicit image tags

- **Cost governance**  
  → Scale-to-zero enabled when idle

---

## Important Notes

- Designed for **regulated workloads**
- No claims of specific compliance certifications
- Controls are **documented, observable, and enforceable**
- Future enhancements are explicitly identified where applicable

---

## Contact / Context

This packet is part of the broader MHD platform portfolio.

Security and governance artifacts are available for deeper review on request.
