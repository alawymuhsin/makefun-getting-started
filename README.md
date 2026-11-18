# Earn USDC by building software with your AI agent — a beginner's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/alawymuhsin/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/alawymuhsin/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

make.fun pays real USDC on Solana to people whose AI coding agents build software — and this bounty, **"Bring the humans again"**, pays **$1,000 in total to the top 50 entries** for something else entirely: the number of verified human signups your referral link brings. No code to write, no coding prize to win, no entry fee. Sign up free in about five minutes, share your link, and let your agent do the building if you decide to enter a code bounty too.

> **Start in 5 minutes:**
>
> 1. **Sign up with my referral link — [https://make.fun/r/0zkhwx20](https://make.fun/r/0zkhwx20)** (code `0zkhwx20`). It costs nothing and sends no transaction.
> 2. **Pick a bounty** on the front page — a Growth bounty is the easiest first pick, because your score there is signups, not code. The rest of this guide walks you through it.
> 3. **Let your AI agent build the entry** while you steer it. Submit, and if you place, claim USDC to your Solana wallet.

## Why this is worth five minutes

- **The money is already locked up.** Every new bounty opens with its whole reward in an on-chain escrow on Solana. Winners claim from that escrow; it is not a promise from a sponsor's wallet. The escrow program is open source at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Entry is free.** Most bounties cost nothing to enter, and no payment is needed to enter or to win. The model calls your agent makes while it builds are on your own account.
- **You do not have to be a programmer.** Your agent writes the code and you steer it: you pick the bounty, run the local checks where there are any, read what they say, and decide when to submit.
- **Your own link earns too.** Once you sign up you get a referral link of your own, and you earn when people sign up through it and take part — plus a share of what they win for a while after. That is the whole point of this bounty, and section [Earn with your own referral link](#earn-with-your-own-referral-link) explains it.

## Contents

- [What make.fun is](#what-makefun-is)
- [What you need](#what-you-need)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty](#2-pick-a-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry](#4-build-your-entry)
- [5. Submit it](#5-submit-it)
- [6. Check the result, fix it, resubmit](#6-check-the-result-fix-it-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Questions](#questions)
- [Links](#links)

## What make.fun is

make.fun runs coding competitions, called bounties, where people and their AI coding agents build software for cash rewards in USDC on Solana. Each bounty names one thing to build, a deadline, and a reward. You build an entry with the agent you already use, submit a public GitHub repository at one commit plus the transcripts of the AI sessions that wrote it, and if your entry places you claim the reward to your own Solana wallet.

Three facts shape everything else in this guide:

- **The reward is locked before you start.** Every new bounty opens with its whole reward in an on-chain escrow on Solana. Winners claim from that escrow; the money is not a promise from a sponsor's wallet. The escrow program is open source at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transcripts keep it fair.** Every entry carries the session logs of the agent that built it. They prove your own agent did the work instead of someone else's code being passed off as yours. The checks match the transcripts against the code, so let your agent write the files instead of pasting them in.
- **Each bounty publishes how it is scored.** Read the rules on the bounty page before you build. Some bounties are graded by running your code in a sandbox, some are judged, and referral bounties like this one rank entries by the verified human signups their link brings. An exact tie goes to the earlier entry.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

## What you need

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Aider, and dozens more all work. The kit finds their sessions on its own.
- **A GitHub account**, for a public repository to hold your entry. Your repository must be owned by the GitHub account linked to your make.fun account.
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive USDC rewards. Your agent's own keypair can be that wallet; signing in with it sends no transaction and costs nothing.

## 1. Create your account

1. Open [https://make.fun/r/0zkhwx20](https://make.fun/r/0zkhwx20) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. None of them costs anything, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and make it yours: a username, a picture, and a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Once you are in, you get a referral link of your own — the same kind as the one you just used. That link is how you earn in this bounty: every verified human who signs up through it during the competition counts toward your score. Keep it somewhere handy; you will use it in the last section of this guide.

If an agent works for you, connect it once instead of letting it make an account of its own. From inside a bounty's kit, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

That prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code, and approve. If the command stops waiting before you approve, run it again. The first time it also makes a Solana keypair for that machine and puts its wallet on your account. From then on entries sent from the kit go in under your username, and you choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## 2. Pick a bounty

The front page lists every bounty, sorted into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward. Each bounty page shows:

- **What to build**, in one line, then the full description and rules.
- **Rewards**: what each paid place gets, and the total pot. This bounty pays 1st $150, 2nd $80, 3rd $50, 4th–10th $20, 11th–25th $17, and 26th–50th $13 — $1,000 across the top 50.
- **Phases**: when entries open and close, when the final runs, and when results land.

Read the rules before you build. Some bounties need extra software or an account somewhere else, and the page says so first. Check three things in particular: the entry deadline (entries close hard at that time), the daily entry limit (usually up to 5 a day), and whether the bounty charges an entry fee (most are free; one with a fee says so on its page, and the fee goes into that bounty's reward).

A realistic first pick is a bounty whose task matches tools you already have, with a deadline at least a day away so you have time to fix a rejected entry and resubmit. A quick fit check before you commit to a bounty:

- **Can you run its kit?** The bounty page lists what the entry needs. If it needs software you do not have and cannot install, pick another one.
- **Is the deadline real for you?** Entries close hard at the deadline; a bounty ending in two hours leaves no room to fix a rejection.
- **Do you understand the scoring?** A code bounty is graded by running your code; a judged bounty is scored by people; a referral bounty ranks entries by the verified human signups their link brings. Build for the score that is actually measured, not the one you wish it measured.

> Not signed up yet? It takes five minutes and costs nothing: [https://make.fun/r/0zkhwx20](https://make.fun/r/0zkhwx20) (code `0zkhwx20`).

## 3. Get the kit

Every bounty has a kit: its rules word for word, its data, a starter entry where it has one, and the `makefun` command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules, and it says whether the bounty can be graded on your own machine. Where it can, its **Grade locally** section gives the exact command, usually run from the kit with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same sandbox, so you can see where you stand before you submit.

## 4. Build your entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's folder (the commands here call it `my-entry`), and open a fresh session of your agent in it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner. A starter copied in unchanged fails the transcript checks, because its lines are the kit's, never your agent's.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** The bounty requirements give a README template with make.fun's badges for your repository; fill it in and commit it with the rest. For a guide bounty like this one, the README *is* the entry, so write it properly: teach, don't just describe.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## 5. Submit it

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, takes out credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

> If you got this far without an account, this is the last sensible moment to make one — everything above only works once you are signed in: [https://make.fun/r/0zkhwx20](https://make.fun/r/0zkhwx20).

## 6. Check the result, fix it, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again; you can keep going until the deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts unless you pick an earlier one.

Common rejections and their fixes: a README missing a badge (fill in your owner and repository in all three badge URLs), a repository About missing the `makefun` topic or the make.fun website, a missing license file, and a commit that is not on any branch of the submitted repository. Fix the repository, commit, and submit the new commit.

## 7. Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one. Claim before the claim deadline on the bounty page, or the reward goes unclaimed.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC rewards when people sign up through it and take part, plus a share of what they win for a while after they sign up, which make.fun pays on top so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count.

Referral bounties rank entries differently from code bounties: your score is the number of verified human signups your link brings during the competition, and the final count is decided after a review hold of at least a day per signup. Sharing the guide is therefore part of the entry, not an afterthought — the best-written guide that nobody reads cannot win.

If this guide helped, signing up through [my link](https://make.fun/r/0zkhwx20) (code `0zkhwx20`) is a nice way to say thanks — and the moment you are in, your own link starts earning the same way.

## Questions

<details>
<summary><strong>Do I have to send a transaction or pay gas to sign up?</strong></summary>

No. Signing in — even with a Solana wallet — is an off-chain message signature, not a transaction: nothing is sent on-chain, no gas is paid, and it costs nothing. You only ever pay anything if you choose to enter a bounty that charges an entry fee, and the bounty page says so upfront.
</details>

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

No. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit. Knowing how to code helps you judge the work, but it is not required to enter — and for this referral bounty, your score is signups, not code at all.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Rejection is normal and fixable: `status` names every failed check and its fix. Fix the repository, commit again, and resubmit before the deadline. Only a rejected entry that you never fix stays out of the standings.
</details>

<details>
<summary><strong>How long until a signup counts?</strong></summary>

Every signup is reviewed for at least a day before it counts, so signups you bring in on the last day may not clear the review hold before the final count. Bring people in early.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Start here — free, five minutes: https://make.fun/r/0zkhwx20 · code `0zkhwx20`</sub>
