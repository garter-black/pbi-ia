# pbi-ia

Source of truth for `https://ia.black.industries/` (Pages project `pbi-ia`).

Decided by the estate source-of-truth lane, 17 Oct 2026. Evidence:
`C:/Hecate-Umbra/estate/decisions/pbi-ia.md`.

## Status: committed baseline, no build recipe

This is a **single-file static page with no build step**. There is no `build.py`,
`package.json` or `wrangler.toml` anywhere in the candidate set, so plan criterion 1
(rebuildable) is **unmet and recorded as unmet**. `index.html` here is the deployed
production bytes, verified byte-identical to `pbi-ia.pages.dev`:

```
sha256 dbe0036ace1c0d062aaeb0858b7820b66d1ae9d3ff9aeeeba727266b7df173ce
5121 bytes, LF-only, 0 CR
```

Committing this establishes truth. It does not improve the site.

## What is live

| Surface | Bytes | Note |
|---|---|---|
| `pbi-ia.pages.dev` | 5,121 | Byte-identical to this repo. |
| `ia.black.industries` | 6,096 | Same page plus edge-injected voice-agent markup. |
| `www.ia.black.industries` | — | DNS does not resolve. |

The 975-byte difference on the custom domain is **entirely injected**, verified three
ways as the lane requires: visible text is identical (1,668 chars on both), and the
only added tags are `script` ×6, `style` ×4 and the `elevenlabs-convai` widget ×2.
No authored content differs. Do not hand-strip these tags to compare bytes — that
does not converge.

## Known gaps, recorded not fixed

- **No `canonical`.** The page declares none, while every other accepted Witchcraft
  and Pitch Black surface in this sweep does.
- **No `robots.txt` or `sitemap.xml`.** Both paths return the 5,121-byte HTML page as
  `text/html` (SPA fallback) on both hosts. A crawler receives a 5 KB HTML document
  where it expects a 40-byte text file.
- **No JSON-LD.** Zero `@type` blocks. Every other accepted site in the sweep carries
  at least `Organization`.
- **No build recipe.** Criterion 1 unmet.

These are repair items for an authorised change, not for this read-only lane.

## Rules

- **Never commit media.** The media layer is R2 / object storage, not git.
- **Never commit `.env` or `.dev.vars`.** Secret values must never enter a commit.
- This is a **Pitch Black Industries** surface, so the footer carries
  `Cognitive Intelligence Services Pty Ltd · ABN 42 689 181 208`, which is correct
  for this arm. Do not convert it to Butterfly Kingdom NSW Pty Ltd
  (`ABN 11 691 050 969`) — that is the Witchcraft arm's entity, and transferring an
  entity or its benefits between arms is a house-rule violation.
- `theblackgarter.com.au` links and data must never be committed.

## Deploy

From this repo, through a separately reviewed registry transaction. This lane is
diagnose-and-queue only and never deploys.