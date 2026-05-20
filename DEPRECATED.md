# ⚠️ DEPRECATED — obsidian-plugins repo

This Hugo site is **archived** as of 2026-05-20.

## Why

- All articles (34/35) have been migrated to the `notes-automate` Astro site
- `hugo.toml` baseURL is `https://notes-automate.com/` which collides with the Astro site
- No Cloudflare Pages project deploys this repo (only ai/gear/notes/pkm/tools-app)
- Translations done in this repo do not show up in production

## Last migration status

- **EN posts**: 35 in `content/en/posts/`
- **ZH-CN posts**: 35 in `content/zh-cn/posts/` (1:1 match after 2026-05-20 cleanup)
- **Orphan content not in notes-automate**: `periodic-notes-plugin-for-weekly-reviews.md`
  (migrated to `notes-automate/content/posts/` on 2026-05-20)

## DO NOT

- ❌ Run `i18n_translator.py` on this repo — it has been removed from the SITES list (2026-05-20)
- ❌ Commit new translations here — they will not appear on any production site
- ❌ Run `hugo` to deploy — this will overwrite the actual `notes-automate` site

## Plan

- 2026-Q3: Migrate any remaining orphans + delete this repo from GitHub
- Until then: keep frozen for git history reference
