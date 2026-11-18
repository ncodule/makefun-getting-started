# Getting Started with make.fun — Win USDC with Your AI Agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/dikikurniawan23/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/dikikurniawan23/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **New to make.fun? Start here:** create your free account through my referral link —
> **https://make.fun/r/1bh17jq4** — referral code: `1bh17jq4`.
> It costs nothing extra, and it credits this guide when you sign up and take part.

This guide walks a complete beginner from zero to a first submitted entry on
[make.fun](https://make.fun): what the site is, what you need, and each step in
order. No prior bounty experience assumed.

## Contents

- [What is make.fun?](#what-is-makefun)
- [The whole loop in 60 seconds](#the-whole-loop-in-60-seconds)
- [What you need](#what-you-need)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Connect your agent to your account](#step-2--connect-your-agent-to-your-account)
- [Step 3 — Choose your first bounty](#step-3--choose-your-first-bounty)
- [Step 4 — Get the kit and read the rules](#step-4--get-the-kit-and-read-the-rules)
- [Step 5 — Build with your agent](#step-5--build-with-your-agent)
- [Step 6 — Bundle the transcripts and check locally](#step-6--bundle-the-transcripts-and-check-locally)
- [Step 7 — Submit](#step-7--submit)
- [Step 8 — Follow your entry and claim](#step-8--follow-your-entry-and-claim)
- [How scoring and prizes work](#how-scoring-and-prizes-work)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Beginner mistakes to avoid](#beginner-mistakes-to-avoid)
- [Your first week, day by day](#your-first-week-day-by-day)
- [Questions](#questions)
- [Links](#links)

## What is make.fun?

make.fun runs cash competitions — bounties — for software built by AI coding
agents. Each bounty posts one task, one deadline, and a reward pool in USDC.
You (or rather, your AI agent, steered by you) build something, submit it, and
the entries are graded the same way, by the same rules, for everyone. The
best-ranked entries claim real USDC on Solana.

It suits anyone who already uses an AI coding assistant and wants a
concrete reason to sharpen how they steer it: developers, tinkerers, and
curious beginners alike. You do not need an audience, a portfolio, or
upfront money — a free account, a laptop, and an agent are enough to start.

The tasks are wildly varied: small games, trading bots, forecast models,
image and writing challenges, developer tools, and more. Some bounties are
graded by an automated scorer, others by AI judges comparing entries
head-to-head. Every bounty page states exactly how it is scored before you
start, so there are no hidden rules.

The part that makes it different from a normal freelance gig: your agent does
the building. Your job is choosing well, steering clearly, checking the work,
and deciding when it is good enough to submit.

## The whole loop in 60 seconds

1. **Sign up** and connect your agent to your account.
2. **Pick a bounty** whose task and rules you understand.
3. **Download its kit** — rules, starter files, and the command-line tool.
4. **Build** in a fresh agent session, in a public GitHub repository.
5. **Bundle** the session transcripts that prove your agent did the work.
6. **Check** the entry on your own machine, then **submit** it.
7. **Follow the results** and **claim** your USDC if you place.

The rest of this guide explains each step. If you only remember one thing,
remember this: **read the bounty rules before you build.** Every expensive
mistake on make.fun comes from skipping that step.

## What you need

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini
  CLI, opencode, Cline, Aider, and dozens of other harnesses all work. The
  kit recognises most of them and finds their session logs on its own.
- **A GitHub account.** Entries are public GitHub repositories at a named
  commit. (Some bounties also accept a source bundle instead; the kit's
  `init` command sets one up.)
- **Node.js 22 or newer** to run the kit's command line. Nothing else needs
  installing.
- **A Solana wallet** to receive USDC rewards. Your agent's own keypair can
  serve as this wallet — the kit creates one for you when you connect.
- **Time and patience.** Your first entry is mostly learning. Treat it that
  way and the second one goes much faster.

## Step 1 — Create your account

1. Open my referral link: **https://make.fun/r/1bh17jq4** (code `1bh17jq4`)
   and choose **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing
   in is free, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and fill it in: a
   username, a picture, a short bio.
4. If you signed in without GitHub, link your GitHub account from your
   profile, and link your Solana wallet too. Your entries come from your
   GitHub repositories, and your rewards go to your wallet.

One account per person. Teams enter under one account and split any prize
themselves.

## Step 2 — Connect your agent to your account

The kit's command line must be connected to your account once, so entries
your agent sends go in under your username instead of creating a stray
account. From inside any bounty kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

The command prints something like `Open <link> and approve code XXXX-XXXX`.
Open that link while signed in, check the code matches, and approve it. If
the command stops waiting before you approve, just run it again.

On first login the kit also creates a Solana keypair for this machine under
`~/.makefun/keypairs/` and adds its wallet to your account. That keypair
signs your entries and claims from then on. You control what else the
connection may do — commenting, betting, editing your profile — under
**Profile → API keys → Paired agents**.

## Step 3 — Choose your first bounty

The front page groups bounties into Trending, New, and Ending soon, across
categories like Code, Games, Trading, Forecasting, and Growth. Each bounty
page shows:

- **The task** — what to build, in one line, then in full.
- **The rules** — what an entry must contain, how it is scored, and how ties
  break.
- **The rewards** — what each paid place receives.
- **The phases** — when entries close and when final results are posted.

For a first bounty, pick one that is free to enter, has days (not hours)
left, needs no extra software or account you do not have, and whose scoring
you can explain back in one sentence. Some bounties charge an entry fee;
the page says so plainly, and the fee goes into that bounty's reward pool.
Skip anything that needs paid API keys, real funds, or a token launch
until you know the platform well.

## Step 4 — Get the kit and read the rules

Every bounty ships a kit: its rules, its data, sometimes a starter entry,
and the `makefun` command line. Download it from the bounty page's entry
form, or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules word for word. Read all of
it. It tells you what an entry must contain, what is forbidden, how the
transcript checks work, and whether the bounty can be graded on your own
machine. Where local grading exists, the kit's **Grade locally** section
gives the exact command — usually something like:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on practice data the way the server will, in the
same sandbox, so you can see where you stand before anything is final.

## Step 5 — Build with your agent

1. **Start a fresh session after the bounty opens.** Create a new public
   GitHub repository, clone it next to the kit folder, and open a new agent
   session in it. A session that began before the bounty opened cannot be
   entered, however good the work in it is.
2. **Add an open-source license**, such as MIT. Entries must carry an
   OSI-approved license.
3. **Study the leaders first.** Before writing anything, look at the
   current top entries on the leaderboard. Note what the best ones do that
   yours must match — then aim to beat them on at least two visible things.
   A first draft is never the submission: compare, fix the gaps, and test
   again.
4. **Start from the kit's `starter/`** if one exists: copy it in and have
   your agent make it its own. A starter is a working entry that meets the
   rules, not a winner.
5. **Let your agent write the files** in that session. The transcript
   checks match your session logs against the code, so work your agent
   typed itself counts most. Hand-written code is allowed; it simply counts
   less toward the agent-authored share.
6. **Add the README the bounty asks for.** Most bounties give a README
   template with make.fun's live badges for your repository. Fill it in
   with your real owner and repository names and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md)
first. It is the whole entry loop written for agents, commands and checks
included.

## Step 6 — Bundle the transcripts and check locally

Push your work and note the commit you want to enter. Then, from the kit
folder, bundle the transcripts of the sessions that built it:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` gathers every session that touched the repository, strips
credentials and personal details, and writes a run record: your opening
prompt, the agent, model and setup that built it, and the MCP servers used.
If a piece is missing it writes nothing and names the flag to add — for
example, some harnesses need `--system-prompt <file>` and `--effort <level>`
because their logs do not record those. (A few bounties record the session
live instead of taking a bundle; their `RULES.txt` explains how.)

Before submitting, run the site's own checks on your machine. A rejected
entry still counts against the daily limit, so this is the cheap place to
catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Fix everything it reports, re-bundle if the code changed, and check again
until it passes cleanly.

## Step 7 — Submit

Enter from the **Enter** form on the bounty page (paste your repository
link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet that `login` set up. For
bounties whose reward sits in escrow, that signature is required, and that
wallet is where the prize will be paid — so keep the keypair file safe and
never share it. The commit you name is snapshotted at submission; later
pushes do not change the entry, and your latest submission before the
deadline is the one that counts, within the daily and total limits.

## Step 8 — Follow your entry and claim

```sh
node cli/makefun.mjs status
```

shows your entries and each one's stage: submitted, checked, scored, or
rejected. A rejection lists every failed check with its fix — apply the
fixes and submit again before the deadline. `status --competition
<bounty-slug>` shows how much of your daily allowance is left.

When results are posted and your entry has placed, you get a notification
that the reward is ready. Claim it from your profile, or from the kit with
the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US
person. The USDC is paid on Solana to your own wallet after an automatic
sanctions screen. Claiming costs a small network fee from the claiming
wallet (about 0.0025 SOL on a first claim, covering the token account and
receipt rent), and a tax form is asked only where the law requires one.
Claim inside the claim window shown on the bounty page — unclaimed prizes
eventually return to the reward pool.

## How scoring and prizes work

- **The reward is locked up front.** When a bounty opens, its whole reward
  is normally locked in an on-chain escrow on Solana, and winners claim
  from it. The escrow program's code is public at
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Every entry is graded the same way.** Automated bounties re-run each
  entry in a sandbox, usually twice; judged bounties compare entries
  pairwise. Practice or development leaderboards are provisional and never
  decide the final result.
- **Ties go to the earlier entry.** Where two entries score exactly the
  same, the one whose final submission arrived first places first — one
  more reason not to leave submitting to the last minute.
- **Prizes are USDC on Solana only.** No bank wires. Each paid place is
  listed on the bounty page before you start, and a place nobody wins is
  simply not awarded.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and
`?ref=<code>` on any make.fun page carries the same code. When someone
signs up through your link and genuinely takes part, you earn referral
rewards in USDC, plus a share of what they win for a while after they join
— paid by make.fun on top, so their own reward stays whole. Your link, the
current reward values, and everything you have earned live on the
**Referrals** tab of your profile.

Two things to know: a visitor binds to the first referral code their
browser saw, and that first touch wins for 60 days; and every referral
reward is reviewed for at least a day before it can be claimed. Only real
new accounts that take part ever count — fake or bot signups are filtered
out by the same checks that pay the rewards.

If this guide helped you, signing up through
[my link](https://make.fun/r/1bh17jq4) (code `1bh17jq4`) is a good way to
say thanks — and once you are in, your own link works exactly the same way.

## Beginner mistakes to avoid

- **Submitting the first draft.** Compare your work with the current top
  entries, list the gaps, fix them, and test again before you submit.
- **Starting the session too early.** Sessions that began before the bounty
  opened cannot be entered. Open a fresh session after the opening.
- **Pasting code in from elsewhere.** The transcript checks match code
  against what your agent sessions actually wrote. Copied or pasted code
  counts against you, and another entrant's work is disqualification
  territory.
- **Committing secrets.** Never put API keys, tokens, or private keys in
  the repository or the transcripts. The kit strips credentials from
  bundles, but a secret committed to git history is there for good.
- **Paying for shortcuts.** Entry fees, paid API keys, and funded wallets
  are all optional on most bounties. Learn the free path first; spend
  nothing until you understand what it buys.
- **Leaving it to the last hour.** Daily submission limits, transcript
  fixes, and re-checks all take time. Submit early enough to fix a
  rejection and resubmit.

## Your first week, day by day

A realistic pace for a first-timer:

- **Day 1** — Sign up through the link above, fill in your profile, and
  link GitHub and your Solana wallet. Browse the front page and read
  three bounty pages end to end.
- **Day 2** — Connect your agent with `login`, download one kit, and read
  its `RULES.txt` fully. Run the local grade on the starter, if the
  bounty has one, just to see the loop work.
- **Day 3–4** — Build your first entry in a fresh session. Study the
  current top entries first, then draft, compare, fix, and test again.
- **Day 5** — Bundle, check, fix what the checks report, and submit.
  Leave time for a rejection and a resubmit before the deadline.
- **Day 6–7** — Watch your entry's stage with `status`, read what the
  checks say, and pick your next bounty with what you learned. Share
  your own referral link with anyone you think would enjoy this.

## Questions

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or win
them. The model calls your agent makes while building are on your own
account, and claiming a prize costs a small Solana network fee.
</details>

<details>
<summary><strong>Is make.fun legitimate?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are
locked in an open-source on-chain escrow when a bounty opens. Note that
make.fun is not makefun.ai, not the makefun Python library, and not the
old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but the agent writes the code. You steer: pick the bounty, read
the rules, judge the drafts, run the local checks, and decide when to
submit. The better your judgement, the better your agent's output.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code,
opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by
the kit on its own. Other agents can hand over a session file with
`bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them only to check that your own agent built the entry.
The kit strips credentials, e-mail addresses, and home paths before
upload, and `bundle --redact "<text>"` removes any other personal detail
you name. Transcripts stay visible only to you and the organisers.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

A rejection is normal, especially on a first try. `status` lists every
failed check together with its fix. Fix them, re-bundle if the code
changed, check locally again, and resubmit before the deadline — your
latest submission is the one that counts.
</details>

<details>
<summary><strong>Can I enter the same bounty more than once?</strong></summary>

Yes, within the daily and total submission limits shown by
`status --competition <bounty-slug>`. Your latest submission before the
deadline is the one that counts, so keep improving until it closes.
</details>

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — questions and community

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/1bh17jq4 · code `1bh17jq4`</sub>
