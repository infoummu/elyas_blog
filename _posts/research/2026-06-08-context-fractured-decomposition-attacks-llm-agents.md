---
title: "Context-Fractured Decomposition Attacks on Tool-Using LLM Agents: Exploiting Artifact Provenance Gaps"
published: true
author: "Research Paper"
category: "research"
description: "New class of adversarial attacks against tool-using LLM agents that exploit provenance gaps between decomposed execution contexts to inject malicious artifacts."
date: "2026-06-08"
source: "arXiv"
source_url: "https://arxiv.org/abs/2606.09084"
tags:
  - AI Security
  - LLM Agents
  - Cyber Security
  - Adversarial Attacks
  - Agentic AI
  - Research
  - Tool-Using Agents
importance_score: "8"
technical_level: "Expert"

---

# Context-Fractured Decomposition Attacks on Tool-Using LLM Agents: Exploiting Artifact Provenance Gaps

## Research Background

Large language model (LLM) agents increasingly rely on tool-use capabilities — executing code, accessing databases, browsing the web, and manipulating files. These agents decompose complex tasks into subtasks executed across multiple tool invocations. Each invocation typically operates within its own execution context, creating provenance gaps between the agent's reasoning, tool output, and final decision-making. While decomposition enables sophisticated multi-step workflows, it also introduces a fundamentally new attack surface: adversaries can inject malicious artifacts that exploit these provenance gaps.

## Research Objective

This paper introduces Context-Fractured Decomposition (CFD) attacks — a novel class of adversarial attacks specifically designed to exploit the provenance gaps created by agentic task decomposition. The objective is to demonstrate that current LLM agent architectures are vulnerable to attacks that manipulate intermediate artifacts between decomposed subtasks.

## Methodology

The researchers designed four concrete CFD attack variants: (1) Artifact Injection — inserting malicious content into intermediate files or databases, (2) Context Poisoning — manipulating contextual signals passed between subtasks, (3) Provenance Spoofing — forging provenance metadata to misattribute artifact origins, and (4) Temporal Reordering — exploiting timing gaps between asynchronous tool executions. Attacks were evaluated against multiple state-of-the-art LLM agent systems (AutoGPT, LangChain agents, OpenAI Assistants API) across 12 benchmark tasks.

## Main Findings

* CFD attacks achieved 84% success rate across all tested agent architectures
* Provenance spoofing was the most effective variant (91% success rate)
* Current LLM agents have no built-in provenance tracking capabilities
* Longer task chains (5+ subtasks) were significantly more vulnerable (92%) than short chains (47%)
* All major agent frameworks tested were vulnerable with no existing mitigations
* Detection by existing security tools was near-zero (2% detection rate)

## Contributions

This paper makes several novel contributions: (1) identification of a previously undocumented vulnerability class in LLM agent architectures, (2) formal characterization of CFD attacks with four operational variants, (3) comprehensive empirical evaluation across multiple agent frameworks and task types, (4) demonstration that provenance gaps are a fundamental architectural weakness, and (5) a proposed defense framework incorporating artifact provenance tracking and cross-context validation.

## Limitations

The study was conducted in controlled laboratory environments, not production systems. The attack surface in real-world deployments with additional security layers may differ. Long-running agents with state persistence were not fully tested. The computational overhead of proposed defenses was not quantified.

## Future Research Opportunities

Critical areas for future work include: (1) developing practical provenance tracking systems for LLM agent frameworks, (2) cross-context integrity verification protocols, (3) real-world deployment studies to validate laboratory findings, (4) defense mechanisms that balance security with agent performance, and (5) standardization of agent security best practices.

## References

1. arXiv - https://arxiv.org/abs/2606.09084
