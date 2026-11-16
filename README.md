# AI builds

Tools and automations I build with LLMs and AI coding agents: what problem each one solves, how it is put
together, and how it is tested. New projects go into their own folder here.

## Projects

| Project | What it does |
|---|---|
| [seo-serp-mvp](seo-serp-mvp) | Daily Google.ca mobile SERP tracking with LLM site labelling (Python, Gemini, Google Sheets, Telegram, GitHub Actions). Its workflows live in the root `.github/workflows` (`daily.yml`, `seo-serp-mvp-tests.yml`) because GitHub runs workflows only from there. |
| [claude-skills](claude-skills) | Claude Code skills that make an AI agent write tests in my style (pytest and Playwright TypeScript). Public description; the full skills are shared on request. |
| [api-test-agent](https://github.com/testomut/api-test-agent) | CLI that audits OpenAPI specs and generates reviewable Playwright API tests, with an optional AI step through Claude Code or Codex. Published on npm, so it stays in its own repository. |

## Layout

```text
ai-builds/
  <project>/   one folder per project, each with its own README and dependencies
```
