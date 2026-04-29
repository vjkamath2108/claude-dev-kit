# ADR-001: Use Bedrock AgentCore Over Custom Orchestrator

**Date:** 2026-04-23
**Status:** Proposed

## Context

Building an AI agent system requires an orchestration layer to manage agent lifecycle, tool routing, memory, and session state. The team must choose between adopting AWS Bedrock AgentCore (a managed orchestration service) or building a custom orchestrator in-house. The decision affects development velocity, operational burden, flexibility, and vendor dependency.

## Decision

Use AWS Bedrock AgentCore as the agent orchestration layer instead of building a custom orchestrator.

## Consequences

**Positive:**
- Reduced time-to-production — managed service handles lifecycle, memory, and tool routing out of the box
- Built-in integration with AWS services (S3, Lambda, IAM, CloudWatch) lowers glue-code overhead
- Automatic scaling and HA without custom infrastructure work
- AWS-managed security posture and compliance certifications (SOC2, HIPAA-eligible)

**Negative:**
- Vendor lock-in to AWS; migrating away later would require re-implementing orchestration
- Less control over internal routing logic, retry behavior, and prompt engineering hooks
- AgentCore pricing adds per-request cost at scale versus amortized infra cost of a custom solution
- Feature velocity depends on AWS roadmap, not the team's own priorities

## Alternatives Considered

| Option | Reason Rejected |
|---|---|
| Custom orchestrator (e.g. LangGraph, home-grown) | Higher build and maintenance cost; team does not have bandwidth to own orchestration reliability at scale |
| LangChain/LangGraph self-hosted | Still requires infra ownership; less tight AWS integration; added framework abstraction with its own bugs |
| OpenAI Assistants API | Not on AWS; conflicts with existing cloud strategy and data residency requirements |
