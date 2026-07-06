# x-autodiscovery

An auto-updating agent skill that keeps a current map of the Vercel platform — what it can do and what just launched — sourced from [@vercel](https://x.com/vercel).

Install: `npx skills add MatiSolina/x-autodiscovery`

How it stays fresh: an [eve](https://vercel.com/docs/eve) agent listens to @vercel every 15 minutes, researches each launch, and commits new dated entries to `news.md`. The skill's freshness protocol tells your agent to fetch the latest `news.md` from this repo before answering.

## How it stays fresh

This skill is maintained by an autonomous [eve](https://github.com/vercel/eve) agent that watches [@vercel](https://x.com/vercel) and commits every new launch here within ~15 minutes. Source: [MatiSolina/x-autodiscovery-agent](https://github.com/MatiSolina/x-autodiscovery-agent) — fork it to build your own updater bot.
