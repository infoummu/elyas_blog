---
title: "For the 2nd Time in Weeks, Microsoft Packages Laced with Credential Stealer"
published: true
author: "Dan Goodin"
category: "news"
description: "73 cryptographically verified Microsoft npm packages were backdoored with the Miasma credential-stealing worm that triggers when opened in AI coding agents."
date: "2026-06-08"
source: "Ars Technica"
source_url: "https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/"
tags:
  - Cyber Security
  - Supply Chain Attack
  - Malware
  - Microsoft
  - AI Agents
  - DevOps
  - Open Source
importance_score: "9"
technical_level: "Advanced"

---

# For the 2nd Time in Weeks, Microsoft Packages Laced with Credential Stealer

## Summary

For the second time in two months, Microsoft's official GitHub repositories were compromised. 73 cryptographically verified npm packages were backdoored with the Miasma worm, a credential-stealing malware that executes a 28 KB payload harvesting credentials from AWS, Azure, GCP, Kubernetes, password managers, and 90+ developer tools. Critically, the malware triggers automatically when developers open the packages in AI coding agents (Claude Code, Gemini CLI, Cursor, VS Code), without needing to execute any code. The attack used stolen Microsoft OIDC tokens to publish malicious builds with valid SLSA provenance attestation, bypassing conventional supply-chain security measures.

## Key Points

* 73 official Microsoft npm packages poisoned with the Miasma credential-stealing worm
* Payload fires automatically when opened in AI coding agents (Claude Code, Gemini CLI, Cursor, VS Code)
* Steals credentials from AWS, Azure, GCP, Kubernetes, 90+ dev tools, and password managers
* Stolen Microsoft OIDC tokens used to sign malicious builds with valid SLSA provenance
* Uniquely encrypted payload per infection — hash-based detection completely useless
* Same Microsoft account was compromised in May 2026 (durabletask incident on PyPI, 400k downloads/month)
* GitHub initially labeled packages as "Terms of Service violations" rather than malware
* The Miasma worm (Mini Shai-Hulud toolkit by TeamPCP) is open-sourced and widely available

## Why It Matters

This attack represents a dangerous evolution in software supply-chain attacks across multiple dimensions. By targeting AI coding agents as the trigger mechanism, the attack surface expands dramatically — developers no longer need to run code, just open a file in their IDE. The weaponization of SLSA provenance attestation against itself is particularly troubling: cryptographic verification was designed to increase trust, but attackers turned it into a weapon. The double-compromise of the same Microsoft account raises serious questions about credential hygiene at one of the world's largest tech companies.

## Future Impact

Expect several industry-wide changes: (1) AI coding tools will add mandatory sandboxing for opened packages, (2) SLSA framework revisions to address stolen-OIDC-token attacks, (3) heightened scrutiny across all major package registries (npm, PyPI, GitHub Packages), (4) copycat attacks targeting other high-profile publishers, and (5) fundamental redesign of package signing and identity verification in the software supply chain.

## References

1. Ars Technica - https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/
