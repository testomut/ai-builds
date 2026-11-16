# Claude Code skills for writing tests in my style

Two [Claude Code skills](https://docs.claude.com/en/docs/claude-code/skills) that capture how I write automated
tests, so an AI coding agent produces tests the way I would: same structure, same naming, same rules about data
and assertions. One skill per stack, kept structurally identical so a test reads the same in both languages:

| Skill | Covers |
|---|---|
| `qa-tests-pytest` | pytest: UI with pytest-playwright, API with httpx / requests, database and data-pipeline checks in SQL |
| `qa-tests-playwright-ts` | Playwright Test in TypeScript (UI and API), plus Cypress habits from earlier projects |

The rules were extracted from my own repositories (the [Playwright projects](https://github.com/testomut/playwright),
[api-test-agent](https://github.com/testomut/api-test-agent)) rather than written from scratch.

## What the skills encode

- Test body reads like a manual test case: numbered steps, one action plus its checks per step, case ID in the title.
- `get_*` / `verify_*` split in page objects, API clients and DB connectors; failure messages say what was compared.
- Fixtures clean up first, then create exactly the state a test needs; one isolated resource per parallel worker.
- Created data is removed in `finally`, even when the check fails.
- Suite type in the file name (functional / contract / scenarios), polarity as a tag, stable case IDs in a registry.
- The requirement is the source of truth: no assertion is edited just to make a test pass, assumptions are marked,
  and a missing precondition becomes an explicit `BLOCKED` skip instead of invented data.

### Three rules, as written in the skill

> A test reads like a manual test case. Logic lives in page objects / connectors / clients, not in the test.

> Seed fixtures clean up first, then create the exact state the test needs, so a crashed previous run never
> breaks the next one.

> Never make a test green by editing its assertion. If a check fails, investigate; change the assertion only
> when the requirement says the old expectation was wrong, and say so in the commit.

## Full version

The complete skills are kept in a private repository and shared on request (send me your GitHub username via
[LinkedIn](https://www.linkedin.com/in/stanislavmokshinaqa)).

Copyright (c) 2026 Stanislav Mokshyn. All rights reserved: see [LICENSE.md](LICENSE.md).
