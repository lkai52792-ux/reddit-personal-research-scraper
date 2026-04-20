# reddit-personal-research-scraper

  A small personal Python script that uses [PRAW](https://github.com/praw-dev/praw)
  to collect public posts and comments from a curated list of subreddits for
  offline personal analysis of consumer product discussions.

  ## Scope & Principles

  - **Read-only.** The app does not post, comment, vote, send messages,
    or perform any moderation actions.
  - **Local storage only.** Collected data is written to CSV/JSON on the
    developer's personal laptop and never redistributed.
  - **Personal, non-commercial use.** Results are used solely for the
    developer's own note-taking on consumer product discussions.
  - **No ML / LLM training.** Collected data is never used as input for
    model training, fine-tuning, or any derivative AI product.
  - **Rate-limit compliant.** All API calls go through OAuth 2 script
    flow via PRAW, with request volumes strictly below Reddit's published
    limits (60 req/min for OAuth clients).
  - **No autonomy.** Every run is manually triggered. No scheduled jobs,
    no background daemons, no multi-account operation.

  ## Workflow

  1. Developer defines a research topic in a local YAML config file
     (10–20 keywords + a small curated list of topical subreddits).
  2. Script authenticates via OAuth 2 script flow using credentials
     stored in a local `.env` file (never committed).
  3. Script runs keyword search across the listed subreddits and
     collects resulting posts and their comment trees.
  4. Results are dumped to local CSV/JSON files for offline reading
     and analysis in pandas.

  ## Compliance

  This app abides by Reddit's Responsible Builder Policy and Data API Terms:
  no commercialization of Reddit data, no re-identification of users, no
  redistribution, no AI training, no circumvention of rate limits.

  ## Dedicated Account

  The app operates exclusively under a dedicated Reddit account
  (`u/Kai_Teng0519`), separate from the developer's personal browsing
  account, in compliance with the "no mixed use accounts" requirement.
