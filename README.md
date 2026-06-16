# Hermes Wiki Manager - AI-Powered Intern Tracker

An autonomous AI agent built with Hermes Agent that captures intern updates from Slack and maintains a structured knowledge base using Karpathy's LLM Wiki pattern.

## What It Does
When an intern posts an update in Slack #intern-updates, the agent automatically:
1. Reads the intern's existing wiki page
2. Integrates the new information
3. Rewrites the Summary section (always current)
4. Appends to the History section (permanent audit trail)
5. Saves raw Slack messages as immutable sources
6. Updates the wiki index and action log

This is Andrej Karpathy's LLM Wiki pattern - knowledge is synthesised at write time, not query time. Pages stay clean as the wiki grows.

## Tech Stack
- Hermes Agent v0.16.0 - autonomous AI agent framework by Nous Research
- DeepSeek V4 Flash via OpenRouter - LLM powering the agent
- Slack - intern update channel with Socket Mode bot
- Markdown Wiki - local file-based knowledge base (no database needed)

## Wiki Structure
wiki/
  SCHEMA.md - conventions and tag taxonomy
  index.md - catalog of all intern pages
  log.md - chronological action log
  entities/ - one .md file per intern
  raw/slack/ - immutable raw Slack message archive

## Why Karpathy's LLM Wiki Pattern?
Traditional approach: All updates appended to one doc. Manager scans everything at query time.
LLM Wiki pattern: Each intern owns a structured page. AI synthesises at write time. Manager asks what is Divyansh working on and gets an instant answer from the Summary. No scanning needed.

## Assignment Context
Built as part of the AIPlanet GenAI Internship (June-October 2026).
- Week 1: Slack to Google Docs pipeline with Hermes agent
- Week 2: Upgrade to Karpathy LLM Wiki pattern with per-intern markdown files

## Key Learnings
- Hermes Agent's built-in llm-wiki skill implements the full Karpathy pattern out of the box
- channel_prompts in config.yaml forces wiki routing for every message in a specific Slack channel
- Knowledge synthesised at write time scales better than query-time synthesis as team size grows

## Setup
1. Install Hermes Agent: uv tool install hermes-agent
2. Configure OpenRouter API key in .env
3. Set up Slack bot with Socket Mode
4. Set WIKI_PATH in .env pointing to wiki folder
5. Start gateway: hermes gateway run
6. Interns post updates in #intern-updates - wiki updates automatically

Note: .env files with API keys are not included in this repo.
