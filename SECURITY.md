# Security Policy

## About This Repository

This repository is a personal fork of [Anthropic's Claude Code](https://github.com/anthropics/claude-code) maintained by Jesse Evans ([@jevans3](https://github.com/jevans3)), Principal Solutions Architect and Product Director at Infor Healthcare. It is used for local development, evaluation, and enterprise adaptation of Claude Code tooling for the Infor FHIR Services (IFS) platform and related healthcare interoperability workflows.

This fork does not ship production software or public releases. It does not process, store, or transmit Protected Health Information (PHI) or Personally Identifiable Information (PII).

---

## Upstream Security Policy

For vulnerabilities in Claude Code itself, refer to Anthropic's upstream security policy:

- **Upstream Repository:** https://github.com/anthropics/claude-code
- **Anthropic Security:** https://www.anthropic.com/security
- **Anthropic Responsible Disclosure:** security@anthropic.com

Upstream vulnerabilities should be reported directly to Anthropic, not to this fork.

---

## Supported Versions

This fork tracks the upstream `main` branch on a best-effort basis. No formal versioning or release lifecycle is maintained for this fork.

| Version | Supported |
|---------|-----------|
| Latest `main` (this fork) | ✅ Best-effort |
| All prior tags in this fork | ❌ Not supported |

---

## Reporting a Vulnerability

If you discover a vulnerability that is **specific to modifications made in this fork** (i.e., not present in the upstream Anthropic repository), please report it responsibly using one of the following methods:

### Preferred: GitHub Private Security Advisory

1. Navigate to the [Security tab](https://github.com/jevans3/claude-code-JEVANS-Fork/security) of this repository.
2. Click **"Report a vulnerability"** to open a private advisory draft.
3. Include as much detail as possible (see below).

### Alternate: Direct Contact

- **Email:** Use GitHub's private messaging or the email associated with [@jevans3](https://github.com/jevans3).

---

## What to Include in a Report

Please include the following in any vulnerability report:

- **Description:** Clear summary of the vulnerability and its potential impact.
- **Affected Component:** File(s), module(s), or configuration(s) involved.
- **Reproduction Steps:** Minimal steps to reproduce the issue.
- **Proof of Concept:** Code, payload, or screenshots demonstrating the issue (if safe to share).
- **Suggested Fix:** If you have a proposed remediation, include it.
- **Severity Assessment:** Your estimate of severity (Critical / High / Medium / Low) using CVSS v3 or equivalent rationale.

---

## Response Expectations

Since this is a personal development fork with no dedicated security team:

| Stage | Target Timeframe |
|---|---|
| Acknowledgment | Within 5 business days |
| Initial assessment | Within 10 business days |
| Remediation (if applicable) | Best-effort; critical issues prioritized |

If the vulnerability is determined to originate in upstream Claude Code, it will be forwarded to Anthropic's security team and you will be notified.

---

## Scope

### In Scope (this fork only)

- Custom scripts, wrappers, or configuration files added to this fork.
- Fork-specific modifications to Claude Code source files.
- Integration code connecting Claude Code to internal tooling (e.g., MCP servers, monitoring daemons, IFS pipelines).
- Credential handling or secrets management in fork-specific code.

### Out of Scope

- Vulnerabilities in the upstream `anthropics/claude-code` codebase (report to Anthropic).
- Vulnerabilities in Anthropic's Claude API or claude.ai products.
- Attacks requiring physical access to the developer machine.
- Social engineering attacks targeting the repository owner.
- Issues in third-party dependencies not modified by this fork (report to the dependency maintainer).

---

## Security Practices in This Fork

The following practices are maintained across all code in this fork:

- **No PHI/PII in code or logs.** Healthcare data is never committed to this repository.
- **No hardcoded secrets.** All credentials use environment variables or AWS Secrets Manager references.
- **No mock credentials.** Test configurations reference real sandboxes (HAPI public server, Da Vinci RI, Optum Sandbox) — not hardcoded fake values.
- **Dependency hygiene.** Dependencies are not modified from upstream except where explicitly documented.
- **Private repositories for sensitive work.** Forks containing patient-adjacent tooling are kept in private repos under the Infor GitHub organization.

---

## Healthcare & HIPAA Notice

This fork does **not** constitute a HIPAA-covered component or business associate agreement (BAA) scope. It is a developer toolchain used for local development and testing against synthetic or de-identified data environments only.

Any deployment of code derived from this fork into production healthcare environments is the responsibility of the deploying organization and must comply with applicable HIPAA, HITRUST, and CMS regulatory requirements.

---

## Acknowledgments

Security researchers who responsibly disclose valid vulnerabilities specific to this fork will be acknowledged in the relevant commit or advisory (unless they prefer to remain anonymous).

---

*Last updated: 2026.04.03 | Maintained by [@jevans3](https://github.com/jevans3)*
