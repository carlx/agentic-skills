---
name: generate-changelog
description: Generate a structured changelog using multiple agents working in parallel to analyze git history and write release notes.
metadata:
  version: "1.1"
---

# Generate Changelog

Generate a changelog for the current repository using parallel agents.

## Steps

1. Launch two agents in parallel:
   - **Agent A – Git Analyst**: Run `git log --oneline` since the last tag (or last 50 commits if no tags). Collect commit messages and categorize them into: `feat`, `fix`, `breaking`, `chore`, `docs`, `other`.
   - **Agent B – PR/Issue Analyst**: Run `git log --oneline` and look for PR numbers or issue references in commit messages. List them with their descriptions.

2. Wait for both agents to finish.

3. Combine their output and write a `CHANGELOG.md` entry in this format:

```
## [version] – YYYY-MM-DD

### Breaking Changes
- ...

### Features
- ...

### Bug Fixes
- ...

### Other
- ...
```

Use today's date. If no version is provided, use `Unreleased`.
