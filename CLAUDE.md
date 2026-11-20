# Cold outreach to DTC ecommerce brands

## What this workflow does

Turns what I know about one prospect (their HubSpot record, any call summary, their LinkedIn profile, and their website) into a short, personalized cold email or LinkedIn DM. Each message ties their store to how Opensend identifies anonymous visitors and sends them into Klaviyo flows, so I can reach more prospects with messages that feel written for them.

- **Who runs it:** Rin, SDR
- **How often:** Daily, one prospect at a time
- **Who uses the result:** Rin, who reviews each draft and sends it to the prospect

## Who you are talking to

Rin, an SDR at Opensend. Not an engineer. Use plain words and explain any technical term the first time.

## Inputs

<!-- Every input lives in raw/ and is never committed. -->

| File | Where it comes from | How to get it |
|---|---|---|
| `raw/[prospect]-hubspot.txt` | The prospect's HubSpot contact and company record | Copy the record's fields from HubSpot into a text file |
| `raw/[prospect]-call-summary.txt` | Notes from a call with the prospect, if there was one | Copy the call summary into a text file |
| `raw/[prospect]-linkedin.txt` | The prospect's LinkedIn profile | Copy the useful parts (role, background, recent posts) into a text file |
| The prospect's website | The brand's public online store | Give Claude the web address. It's public, so it isn't saved in `raw/` |

## How it's done today

<!-- Session 2: describe how you do this workflow now, in your own words. Messy is fine.
     In Session 3 this section is replaced by the numbered steps below. -->

I pick one prospect, read their HubSpot record, any call summary, their LinkedIn profile, and their website, and look for something about their store that connects to Opensend: identifying anonymous visitors and sending them into Klaviyo flows. Then I write a short email or LinkedIn DM from scratch, signed as Rin, and send it myself.

## Steps

<!-- Leave this section as it is until Session 3. WORKFLOW.md and steps/ don't exist yet. -->

The numbered steps are in `WORKFLOW.md`, one file per step in `steps/`. Run them one at a time. After each step, check its done-check and stop for review before going on.

## Outputs

| File | What it is | Where it goes |
|---|---|---|
| `outputs/history/[YYYY-MM-DD]-[prospect]-[email or dm].md` | A ready-to-send email or LinkedIn DM, signed as Rin | Rin reviews it, then sends it from email or LinkedIn |

## How to check it still works

<!-- Leave this section as it is until Session 4, when you make the golden example. -->

Run the golden example in `golden/`. Its README says what the correct output is.

## Where things live

| Folder | What goes there | Committed to GitHub? |
|---|---|---|
| `raw/` | Inputs exactly as they arrived: exports, PDFs, spreadsheets | Never |
| `derived/` | Files the workflow steps create from the raw inputs and can recreate any time | Never: they hold real data |
| `outputs/history/` | Finished results, one file per run, kept forever | Never in this public repo. Kept on this computer, never overwritten |
| `golden/` | The golden example: a made-up input and its correct output | Yes. Made-up data only |
| `templates/` | Starting points for CLAUDE.md, steps, and the golden example | Yes |
| `docs/` | Short reference docs for the series | Yes |

## Rules you must always follow

<!-- Keep rules 1 to 5 word for word. This repo is public. -->

1. **Never commit anything under `raw/`, `derived/`, or `outputs/history/`.** Before every commit, run `git status` and make sure no file from those folders is staged.
2. **Check every commit for sensitive content.** This repo is public. Read the staged diff, the commit message, and any pull request text for anything on the "Never commit" list in `CONTRIBUTING.md`: client or customer names and details, real business numbers, personal information, passwords, API keys, tokens, internal links, screenshots. If you find any, stop, show me the lines, and suggest a made-up replacement.
3. **Never overwrite anything under `outputs/history/`.** Each run writes a new file with the date in its name. If a step would write over an existing file there, stop and ask.
4. **Always show a diff before applying a change,** and wait for a yes.
5. **Never push to `fueled-io/os-claude-advanced-training` directly.** Push my branch to my fork, and open a pull request.
6. **Draft only, never send.** Rin reviews and sends every message. Use only facts from the prospect's HubSpot record, call summary, LinkedIn profile, or website. Don't invent details about their store, and don't make up Opensend results or numbers. Emails stay under 120 words and DMs under 60.
