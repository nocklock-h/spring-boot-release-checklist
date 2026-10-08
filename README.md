[English](./README.md) | [한국어](./README.ko.md)

---

# Ship Your Spring Boot MVP

A practical release checklist for Spring Boot MVPs moving from localhost to production.

Your application running successfully on localhost does not mean it is ready for real users.

This repository focuses on a simple release habit:

> Check → Verify → Save evidence → Make the release decision

It is designed for developers who want a lightweight way to catch obvious release blockers and verify their assumptions before shipping.

**Want the complete workflow? → [Explore the 58-Page Spring Boot Deployment Runbook](https://nocklock.lemonsqueezy.com/checkout/buy/587f273f-2eb7-4e55-9ad7-cfdcba6acc99)**


---

## Why I made this

While building and deploying small Spring Boot products, I found that the difficult part was often not writing one more feature.

It was answering questions like:

- Did I verify the production configuration?
- Are secrets actually separated from the application?
- Does the critical user flow work after deployment?
- What evidence do I have that the release is healthy?
- If something breaks, what can I roll back to?
- Am I relying on an AI answer, or did I actually verify it?

This repository is a small workflow for making those questions explicit before a release.

---

## Who this is for

This may be useful if:

- you built a Spring Boot MVP
- it already works locally
- you are preparing for a first or early production deployment
- you used ChatGPT, Claude, Copilot, Cursor, or another AI coding tool during development
- you want a lightweight release process without introducing a full SRE framework
- you keep asking: “What did I forget?”

This is probably not the right resource if you are looking for:

- a complete AWS / Railway / Render deployment tutorial
- an enterprise SRE framework
- a Spring Boot starter codebase
- a security or compliance certification checklist

---

## What is included

### 1. 15 Critical Spring Boot Ship Blockers

A compact pre-release review covering:

- build and tests
- configuration and secrets
- database and external integrations
- application security
- deployment and production behavior

[Open the checklist](./checklist/15-ship-blockers.md)

### 2. Evidence-first AI review

Use AI as a second reviewer — not as the owner of the release decision.

Instead of asking:

> “Is this application production-ready?”

ask the model to show the evidence behind each claim.

Example:

```text
Review this Spring Boot MVP for release blockers.

For every finding:
1. State the check.
2. Show the file, config, command output, or other evidence.
3. Mark it VERIFIED or NOT VERIFIED.
4. Explain what would block release.

Do not assume missing evidence is safe.
Do not modify code unless I ask.
```

The important distinction is:

> **Evidence ≠ inference**

If evidence is missing, treat the result as:

```text
NOT VERIFIED
```

You can also use the repository prompt:

**[Open the AI review prompt](./prompts/deployment-blocker-review.md)**

---

### 3. Release evidence template

You do not need a complicated release system for every MVP.

A small record is often enough:

```text
Release commit:
Production URL:
Clean build evidence:
Test evidence:
Production configuration reviewed:
Critical user flow:
Rollback point:
Known unresolved risk:
```

Examples:

```text
./gradlew clean build → BUILD SUCCESSFUL
./gradlew test → expected tests passed
Release commit → a1b2c3d
Deployment ID → platform release identifier
Health check → expected response from production URL
Critical flow → manually verified against production
Rollback point → previous known-good commit / deployment
```

> Never store passwords, API keys, tokens, secrets, or sensitive user data in a release evidence record.

For a reusable version:

**[Open the release evidence template](./checklist/ship-score-template.md)**

---

## 10-minute quick start

1. Open the [15 Critical Spring Boot Ship Blockers](./checklist/15-ship-blockers.md).
2. Mark only the checks you actually verified.
3. Review the relevant files, configuration, logs, and deployment output.
4. Use AI as a second reviewer where useful.
5. Treat missing evidence as `NOT VERIFIED`.
6. Fix release-blocking issues.
7. Deploy.
8. Run the critical production smoke test.
9. Record the deployed commit and rollback point.

---

## Release mindset

The main idea behind this repository is simple:

> **A successful deployment is not the same as a verified release.**

A platform showing a green deployment status proves that the deployment process completed.

It does not automatically prove that:

- configuration is correct
- external integrations work
- the critical user journey works
- secrets are handled safely
- rollback is possible
- the deployed version is the version you expected

For an MVP, the release process does not need to be heavy.

It just needs to make important assumptions visible.

---

## Extended release workflow

This repository intentionally stays small and Markdown-based.

While developing this workflow, I also created a more structured version for releases that need stronger evidence tracking.

It adds:

- a six-stage release workflow
- interactive verification checkboxes
- editable evidence fields
- detailed failure actions
- AI review prompts
- deployment and rollback guidance
- reusable release templates
- chapter-level ship / no-ship decisions

If the lightweight checklist here is enough, keep using it.

If you want the more structured workflow:

**[Explore the 58-Page Spring Boot Deployment Runbook](https://nocklock.lemonsqueezy.com/checkout/buy/587f273f-2eb7-4e55-9ad7-cfdcba6acc99)**

---

## Scope and limitations

This repository is an engineering checklist and workflow aid.

It does not guarantee that an application is:

- secure
- bug-free
- compliant
- performant
- production-ready for every use case

Different applications may require additional architecture, performance, privacy, legal, compliance, security, infrastructure, or operational review.

Use this workflow as a starting point, not as a substitute for engineering judgment.

---

## About Nocklock

**Nocklock** is where I document experiments in backend development, AI-assisted engineering, deployment, and building small software products.

Current focus:

- Java / Spring Boot
- backend systems
- AI-assisted development
- deployment workflows
- privacy and security tooling
- turning small ideas into working products

---

Built by **Nocklock**

**AI-assisted. Built for human verification. Evidence-backed.**

---

