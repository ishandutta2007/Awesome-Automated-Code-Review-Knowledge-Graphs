# Awesome Automated Code Review & Knowledge Graphs [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of SaaS products, open-source projects, and developer tools for **AI-assisted automated code review**, **pull request (PR) analysis**, and **codebase knowledge graphs**.

Accelerate code reviews, detect security vulnerabilities, automate pull request triage, and index complex repositories into queryable AST/graph models for coding agents (Claude Code, Cursor, Codex, OpenCode, and Gemini).

---

## Table of Contents
- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS / Hosted Platforms](#saas--hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Choose](#how-to-choose)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

---

## Sector Overview & Market Dynamics

The automated code review and developer productivity intelligence sector is experiencing hyper-growth, expanding alongside the global AI code tools and DevSecOps market valued at **$1.5B–$2.5B in 2026** and compounding at a **27%–48% CAGR** toward **$14B+ by 2032**. 

The market dynamics reflect a **moderately fragmented sector in active transition toward platform consolidation**:
- **Consolidation at the Workflow Edge:** Established developer platform and IDE vendors (such as Cursor's acquisition of Graphite) and DevSecOps incumbents (like Snyk) are competing aggressively to absorb review loops into end-to-end coding workflows.
- **Agentic Review & Code Intelligence Specialization:** Dedicated review engines (CodeRabbit, Qodo) and local-first code knowledge graph architectures (Tree-sitter SQLite/Neo4j/MCP indexes) maintain defensible differentiation by solving LLM token exhaustion, context drift, and cross-repository structural impact analysis that general-purpose coding LLMs miss.

---

## SaaS / Hosted Platforms

A comparison of leading hosted automated code review, PR analysis, and developer security platforms. Sorted in descending order by enterprise company size (valuation / funding / revenue scale).

| Product | Company Size (Valuation / Revenue) | Starting Pricing (Paid Tiers) | Free Tier / Trial Limits | Key Capabilities |
| :--- | :--- | :--- | :--- | :--- |
| **[Snyk](https://snyk.io/)** | **~$7.4B valuation** ($309M+ revenue / $326M ARR) | **$25/mo per contributing developer** (Team plan billed monthly); **$1,260/dev/year** (~$105/mo) for Ignite plan | **Free forever plan**: $0/mo for individual developers & small teams (includes up to 200 open-source test scans/mo, 100 code test scans/mo, and 300 container scans/mo) | Developer-first security analysis, automated SAST, dependency/container scanning, SARIF/PR status checks, and license compliance. |
| **[CodeRabbit](https://www.coderabbit.ai/)** | **$1.5B valuation** (Series C $143M in Aug 2026; >5x YoY ARR growth) | **$24/dev/mo** billed annually (**$30/dev/mo** billed monthly) for Essentials plan; **$48/dev/mo** for Team plan | **Free forever plan**: $0 for unlimited public & private repositories (limited to PR summaries, release notes, and high-level reviews; inline automated review comments require Essentials). 14-day free trial on paid plans with unlimited reviews. Free Team tier for qualifying open-source repos. | Context-aware AI pull request reviews, automated line-by-line feedback, sequence diagrams, chat on PR diffs, and AST verification. |
| **[Graphite](https://graphite.com/)** | **~$290M+ valuation** (Acquired by Cursor/Anysphere in Dec 2025; raised $72M+) | **$20/user/mo** billed annually for Starter plan; **$40/user/mo** billed annually for Team plan | **Free forever plan**: $0/mo for personal GitHub repositories & small hobby teams (includes stacked PR creation, CLI tool, and up to 10 AI PR reviews/mo). 14-day trial of Team features. | Stacked PR workflow automation, continuous merge queues, AI PR summaries, automated inline feedback, and fast code sync. |
| **[Qodo](https://www.qodo.ai/)** | **~$280M valuation** (Series B $70M in Mar 2026; $120M total raised) | **$30/mo base** for Pro Team (includes pooled credits at $0.015/credit; ~14 reviews/mo at 2,000 credits, ~114 reviews/mo at 16,000 credits) | **14-day free trial** with unlimited AI review and test generation. **No permanent free tier** on hosted Pro; free community CLI version available via open-source `pr-agent`. | Agentic PR reviews with whole-codebase contextual awareness, automated test generation, PR descriptions, and custom merge rules. |
| **[Codacy](https://www.codacy.com/)** | **~$50M–$100M valuation** ($7.3M estimated ARR; $32M raised) | **$15/dev/mo** billed annually (**$18–$21/dev/mo** billed monthly) for Pro plan | **Free forever plan**: $0/mo for open-source repositories with unlimited public repos and full static analysis; 14-day free trial of Pro plan with full access for private repositories. | Automated static code analysis across 40+ languages, code coverage tracking, technical debt metrics, security analysis, and AI auto-fix. |
| **[Bito](https://bito.ai/)** | **~$8.9M total funding raised** (Seed-stage enterprise software startup) | **$20/seat/mo** billed annually (**$25/seat/mo** billed monthly) for Professional plan (includes 5,000 LOC/seat/mo; overage at $5 per 1,000 LOC) | **14-day free trial**: capped at 15 code review executions per user; large PRs cannot be manually triggered during trial. Free tier for basic personal AI assistant extension. | AI code reviews, automated PR summaries, line-of-code tracking, DSPy & LLM-assisted linting, and developer agent routing. |
| **[Reviewpad](https://reviewpad.com/)** | **~$1.5M total funding raised** (€1M Seed stage) | **$89/month** starting flat tier for team automation | **14-day free trial** with full access to policy engine and GitHub Action review integrations. No permanent free tier for private orgs. | Policy-based PR automation, rule-driven labels and routing, merge gates, and AI-assisted reviewer assignment. |

---

## Open-Source GitHub Projects

Self-hosted, transparent, and community-driven tools for automated code review, AST knowledge graph indexing, and PR workflow automation.

> **Sorted in descending order by GitHub Stars.** Each repository name includes a real-time star badge linking directly to the repository's stargazers.

- ### [codegraph](https://github.com/colbymchenry/codegraph) [![GitHub stars](https://img.shields.io/github/stars/colbymchenry/codegraph?style=social&color=white)](https://github.com/colbymchenry/codegraph/stargazers)
  **Pre-indexed code knowledge graph for local and cloud AI coding agents.**  
  Auto-syncs on source code changes to feed Claude Code, Codex, Gemini, Cursor, and OpenCode with localized structural intelligence. Provides ~100% local operation with dramatic token overhead reduction and minimal tool calls.

- ### [code-review-graph](https://github.com/tirth8205/code-review-graph) [![GitHub stars](https://img.shields.io/github/stars/tirth8205/code-review-graph?style=social&color=white)](https://github.com/tirth8205/code-review-graph/stargazers)
  **Local-first code knowledge graph for AI agents and risk-scored PR reviews.**  
  Builds a persistent SQLite graph of functions, classes, imports, and calls using Tree-sitter without requiring an external database. Emits sticky GitHub Action comments with symbol-level risk scoring, execution flows, and test gap analysis. Yields ~63x median per-question token reduction for MCP coding agents.

- ### [tree-sitter](https://github.com/tree-sitter/tree-sitter) [![GitHub stars](https://img.shields.io/github/stars/tree-sitter/tree-sitter?style=social&color=white)](https://github.com/tree-sitter/tree-sitter/stargazers)
  **The parsing engine foundation for modern codebase knowledge graphs.**  
  An incremental parsing system that builds concrete syntax trees (CST/AST) for source files across dozens of programming languages. Serves as the core syntax indexing engine powering `code-review-graph`, `codegraph`, `okf-generator`, and automated code review AST parsers.

- ### [semgrep](https://github.com/semgrep/semgrep) [![GitHub stars](https://img.shields.io/github/stars/semgrep/semgrep?style=social&color=white)](https://github.com/semgrep/semgrep/stargazers)
  **Lightweight static analysis engine for code review and security enforcement.**  
  Fast, syntax-aware pattern matching for searching code and enforcing secure coding standards in CI/CD pipelines. Uses code-like syntax instead of complex AST queries to detect bugs, CVEs, and compliance issues on every pull request.

- ### [pr-agent](https://github.com/qodo-ai/pr-agent) [![GitHub stars](https://img.shields.io/github/stars/qodo-ai/pr-agent?style=social&color=white)](https://github.com/qodo-ai/pr-agent/stargazers)
  **Open-source autonomous AI agent for pull request review and analysis.**  
  Posts inline PR code suggestions, generates structured pull request descriptions, answers natural language questions on code diffs, and evaluates PR compliance across GitHub, GitLab, and Bitbucket. Supports custom LLM endpoints (Ollama, LiteLLM, OpenAI, Anthropic).

- ### [infer](https://github.com/facebook/infer) [![GitHub stars](https://img.shields.io/github/stars/facebook/infer?style=social&color=white)](https://github.com/facebook/infer/stargazers)
  **Static analyzer for Java, C, C++, and Objective-C by Meta.**  
  Employs deep formal methods (separation logic) to find critical memory leaks, null pointer exceptions, and concurrency race conditions before code lands in production. Widely integrated into automated commit and PR gating pipelines.

- ### [sonarqube](https://github.com/SonarSource/sonarqube) [![GitHub stars](https://img.shields.io/github/stars/SonarSource/sonarqube?style=social&color=white)](https://github.com/SonarSource/sonarqube/stargazers)
  **Continuous code quality, vulnerability inspection, and static analysis.**  
  Analyzes 20+ languages to flag bugs, security hotspots, code smells, and technical debt. Connects directly to GitHub, GitLab, and Azure DevOps pull requests with SARIF report ingestion and customizable quality gates.

- ### [reviewdog](https://github.com/reviewdog/reviewdog) [![GitHub stars](https://img.shields.io/github/stars/reviewdog/reviewdog?style=social&color=white)](https://github.com/reviewdog/reviewdog/stargazers)
  **Automated code review runner with unified diff reporting.**  
  Integrates any linter or static analysis tool with code review services. Automatically parses linter output and posts inline comments directly on GitHub Pull Requests, GitLab Merge Requests, and Bitbucket PRs.

- ### [danger](https://github.com/danger/danger) [![GitHub stars](https://img.shields.io/github/stars/danger/danger?style=social&color=white)](https://github.com/danger/danger/stargazers)
  **Automate team pull request review conventions & chore policies.**  
  Codifies social team norms during code review (e.g., verifying changelog updates, enforcing test coverage, checking PR size, and auditing milestone tags) with native comments on GitHub and GitLab.

- ### [codesearch](https://github.com/google/codesearch) [![GitHub stars](https://img.shields.io/github/stars/google/codesearch?style=social&color=white)](https://github.com/google/codesearch/stargazers)
  **Fast, regular-expression-based search indexing over massive codebases.**  
  Google's trigram indexing engine for navigating large-scale source repositories. Used as a reference implementation for regex code navigation and high-speed structural symbol lookups.

- ### [kythe](https://github.com/google/kythe) [![GitHub stars](https://img.shields.io/github/google/kythe?style=social&color=white)](https://github.com/google/kythe/stargazers)
  **Pluggable developer tools platform for code analysis and cross-reference graphs.**  
  Google's ecosystem for creating and querying language-agnostic code graphs. Captures definitions, references, call graphs, and type hierarchies across multi-language enterprise repositories.

- ### [scip](https://github.com/sourcegraph/scip) [![GitHub stars](https://img.shields.io/github/stars/sourcegraph/scip?style=social&color=white)](https://github.com/sourcegraph/scip/stargazers)
  **SCIP Code Intelligence Protocol by Sourcegraph.**  
  A modern, language-agnostic protocol for indexing source code symbol graphs, cross-references, and type relationships. Powers precise jump-to-definition, find-references, and code navigation in review workflows.

- ### [graphicle](https://github.com/Graphicle-AI/graphicle) [![GitHub stars](https://img.shields.io/github/stars/Graphicle-AI/graphicle?style=social&color=white)](https://github.com/Graphicle-AI/graphicle/stargazers)
  **Rust-native code graph and project memory system over MCP.**  
  Combines architectural symbol graphs with historical review decisions directly in a single Rust engine. Integrates with coding agents to preserve context and suppress stale review suggestions.

- ### [RepoLens](https://github.com/TheMorpheus407/RepoLens) [![GitHub stars](https://img.shields.io/github/stars/TheMorpheus407/RepoLens?style=social&color=white)](https://github.com/TheMorpheus407/RepoLens/stargazers)
  **Multi-perspective AI code audit and production readiness evaluation.**  
  Deploys specialized agents across security, architecture, and reliability perspectives. Includes opt-in local learning indexes and plugins for Semgrep, Gitleaks, and OSV.

- ### [dagayn](https://github.com/manji-0/dagayn) [![GitHub stars](https://img.shields.io/github/stars/manji-0/dagayn?style=social&color=white)](https://github.com/manji-0/dagayn/stargazers)
  **Local-first code knowledge graph with multi-backend embeddings.**  
  Parses source files, Markdown, and Terraform infrastructure into an SQLite call graph. Offers FTS-only fast search, local GGUF sidecar embeddings, and remote vector lookups for AI agent review pipelines.

- ### [okf-generator](https://github.com/tommypacker/okf-generator) [![GitHub stars](https://img.shields.io/github/stars/tommypacker/okf-generator?style=social&color=white)](https://github.com/tommypacker/okf-generator/stargazers)
  **Map any codebase into an Open Knowledge Format (OKF) graph for AI agents.**  
  Tree-sitter parser covering 11 languages and 17 package/build manifests. Exports code architectures into GraphML, Neo4j Cypher, Obsidian vaults, and D3 force-directed interactive diagrams.

- ### [gfy](https://github.com/qiangli/gfy) [![GitHub stars](https://img.shields.io/github/stars/qiangli/gfy?style=social&color=white)](https://github.com/qiangli/gfy/stargazers)
  **Go-based code knowledge graph CLI with semantic graph traversal.**  
  CLI tool for calculating shortest symbol paths, fuzzy code queries, and local semantic embeddings via Ollama. Exposes MCP configuration for Claude Code and Cursor.

- ### [codeKG](https://github.com/eviking/codeKG) [![GitHub stars](https://img.shields.io/github/stars/eviking/codeKG?style=social&color=white)](https://github.com/eviking/codeKG/stargazers)
  **Neo4j-backed codebase knowledge graph for AI developer agents.**  
  Parses repository definitions and dependencies into a Neo4j graph database. Generates commit-level `.codekg/INDEX.md` context maps and monitors codebases for incremental re-indexing.

---

## How to Choose

| Requirement | Recommended Solution |
| :--- | :--- |
| **Instant PR summaries and conversational AI review** | [CodeRabbit](https://www.coderabbit.ai/) or [Graphite](https://graphite.com/) |
| **Local-first code review with 0 external token exposure** | [code-review-graph](https://github.com/tirth8205/code-review-graph) or [codegraph](https://github.com/colbymchenry/codegraph) |
| **Open-source self-hosted PR agent for GitHub / GitLab** | [pr-agent](https://github.com/qodo-ai/pr-agent) |
| **Enterprise static analysis and quality gates** | [SonarQube](https://github.com/SonarSource/sonarqube) or [Codacy](https://www.codacy.com/) |
| **Deep security, secrets, and dependency vulnerability scanning** | [Snyk](https://snyk.io/) or [Semgrep](https://github.com/semgrep/semgrep) |
| **Formal verification of memory leaks & concurrency bugs** | [Infer](https://github.com/facebook/infer) |
| **Cross-repository symbol intelligence and code graphing** | [SCIP](https://github.com/sourcegraph/scip) or [Kythe](https://github.com/google/kythe) |

---

## How to Contribute

1. Fork this repository.
2. Add your tool to either the **SaaS / Hosted Platforms** table or the **Open-Source GitHub Projects** list.
   - For SaaS products: provide exact pricing tiers, specific free tier/trial limits, and company scale metrics.
   - For Open-Source projects: provide the GitHub repository link and ensure the social star badge (`style=social&color=white`) links to `/stargazers`.
3. Submit a Pull Request with a clear description of the project.

---

## Disclaimer

- This repository is a community-curated educational resource and does not constitute formal endorsement.
- Automated code review tools process source code and pull request data. Always enforce least-privilege repository permissions, audit third-party data retention policies, and verify automated code modifications before merging.
