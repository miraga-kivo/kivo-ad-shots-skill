# Kivo ad shots skill

An agent skill for making ads with the [Kivo Studio](https://kivst.com) MCP: brand TVC (including a long-take variant), 9:16 feed ads, product review and demo films, realistic beauty or lifestyle mood pieces, and e-commerce detail-page sets and posters. It also includes seven special-shot recipes that stand in for expensive real-world cinematography (aerial, underwater, macro, crane/slider, product motion tracking, timelapse, and surreal compositing).

Homepage: [kivst.com](https://kivst.com). Official MCP guide: [Connect an agent with MCP](https://kivst.com/en/mcp). Related guidance: [kivo-studio-production-skill](https://github.com/miraga-kivo/kivo-studio-production-skill), [kivo-white-model-video-skill](https://github.com/miraga-kivo/kivo-white-model-video-skill). This is independent community packaging of the workflow, not official documentation or a quality guarantee. It is not affiliated with Kivo or ByteDance.

## Install

Copy the folder that contains `SKILL.md` (this package) into your agent's skills directory, keeping the folder name `kivo-ad-shots`. Restart the agent if it does not pick up the skill right away.

### Claude Code

Claude Code loads skills from the paths in [Extend Claude with skills](https://code.claude.com/docs/en/skills):

- **Personal (all your projects on this machine):** `~/.claude/skills/kivo-ad-shots/`
- **Project (this repository):** `.claude/skills/kivo-ad-shots/`

```sh
mkdir -p ~/.claude/skills
cp -R kivo-ad-shots-skill ~/.claude/skills/kivo-ad-shots
```

Ask Claude to use the skill, or invoke it with `/kivo-ad-shots`.

### Codex

Codex loads local skills from these locations, as documented in [Build skills](https://developers.openai.com/codex/skills/):

- **User (all your projects):** `$HOME/.agents/skills/kivo-ad-shots/`
- **Project (this repository):** `.agents/skills/kivo-ad-shots/` at the repo root, or in the folder from which you launch Codex

```sh
mkdir -p ~/.agents/skills
cp -R kivo-ad-shots-skill ~/.agents/skills/kivo-ad-shots
```

In Codex CLI or the IDE extension you can mention the skill with `$kivo-ad-shots` or open `/skills`, or just ask to make an ad or a special shot and let Codex match the skill `description`.

### Cursor

[Cursor's Agent Skills docs](https://cursor.com/docs/skills) load project skills from `.agents/skills/` or `.cursor/skills/`, and user skills from `~/.agents/skills/` or `~/.cursor/skills/`. You can also type `/` in Agent chat and select the skill by name.

```sh
mkdir -p ~/.cursor/skills
cp -R kivo-ad-shots-skill ~/.cursor/skills/kivo-ad-shots
```

Other hosts that implement the Agent Skills `SKILL.md` layout can mount this same folder; follow that host's own skill documentation.

## Requirements

- An MCP host that can connect to the Kivo Studio server at `https://kivst.com/mcp` (Streamable HTTP) and complete browser OAuth. See the [Kivo connection guide](https://kivst.com/en/mcp).
- A Kivo project the user is allowed to use. The project creator pays for successful generation.

This package does not include API keys or credentials. Do not paste account tokens or payment keys into chat. Discover live tool names and schemas on the connected host; prefixes can differ. Refresh catalog limits at runtime.

## What the skill covers

**Five ad types** (see [references/ad-types.md](references/ad-types.md)):

| Type | Typical use | Default model |
|---|---|---|
| A. Brand TVC (multi-shot or long-take) | Brand film, launch, story | Seedance |
| B. 9:16 feed ad (15 / 30 / 45 s) | Douyin / TikTok / Reels | Seedance |
| C. Review / demo | Feature proof, comparison | Seedance |
| D. Beauty / lifestyle mood film | Texture, atmosphere, realism | Seedance |
| E. E-commerce detail-page set and posters | Hero stills, detail-page art | Seedream 5.5 |

**Seven special-shot recipes** (see [references/special-shots.md](references/special-shots.md)): aerial, underwater, macro, crane/slider, product motion tracking, timelapse, and surreal / post compositing. Pick one to three as memory points; do not style every shot.

**Budget-safe flow:** quote → wait for a numeric spend cap → run 1–2 low-resolution Drafts of the riskiest shots → QC → re-quote production and get a second confirmation → upgrade to 1080p. "OK" or approving a storyboard is not spending approval. Do not retry a job that is still pending. Do not steer anyone to buy credits.

Worked storyboards live in [examples/](examples/). MCP tool and catalog notes are in [references/kivo-mcp.md](references/kivo-mcp.md); treat those figures as a dated snapshot and re-read the live catalog before quoting.

## Example prompts

Install the skill and connect Kivo MCP, then talk to the agent in plain language. You can name the skill, invoke it with `/kivo-ad-shots` in Claude Code, or just describe the ad.

**You type:**

> Use kivo-ad-shots: a 30-second 9:16 feed ad for a bottled sparkling tea, hook with a macro splash, then a rooftop timelapse. Quote first and wait for my spend cap.

**The agent should:** pick type B, write a timecode storyboard, quote one or two 480p Drafts of the riskiest shots (usually the macro or timelapse), show model, duration, resolution, count and credits, then stop until you set a numeric cap. It should not create a job yet.

**You type:**

> /kivo-ad-shots 45-second 16:9 sneaker TVC, FPV aerial open, product tracking, surreal scene changes. Start with a Draft of the hardest shot only.

**The agent should:** pick type A plus the matching special-shot recipes, propose a clip plan, and quote a small first Draft (often a short FPV segment) against your cap. After QC, it re-quotes any production upgrade and waits for a second confirmation.

**You type:**

> Make a 3:4 skincare poster in Seedream. Keep the pack shot exact and leave room for typography. Quote and wait.

**The agent should:** pick type E, quote a single still, wait for a numeric cap, and only then generate one image. On-image claims, prices and logos that you did not supply stay off the frame (type is usually added in post).

## Package

```text
kivo-ad-shots-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── .gitignore
├── references/
│   ├── ad-types.md
│   ├── special-shots.md
│   └── kivo-mcp.md
└── examples/
    ├── 01-drink-feed-30s-9x16.md
    ├── 02-sneaker-tvc-45s-16x9.md
    └── 03-skincare-poster-3x4.md
```

## License

[MIT](LICENSE), Copyright (c) 2026 miraga-kivo (Kivo Studio).

## Boundaries

- Paid generation needs an authorized Kivo connector, an authorized project, and an explicit numeric spend cap from the project payer. Creative approval of a board, prompt or Draft is not spending approval.
- Catalog prices, reference limits, tool schemas and model IDs change. Check them live. Do not invent a video price if a quote fails.
- The skill does not promise conversion, views, or a first-take success rate, and it is not an official Kivo or ByteDance offering.
- Project IDs, job IDs, asset IDs, signed URLs and account balances must stay out of any public document.

## 中文简介

用 [Kivo Studio](https://kivst.com) MCP 做五类广告（品牌 TVC 含长镜头版、9:16 信息流、测评/演示、美妆/生活方式氛围片、电商详情页套图与海报），并提供七类特殊镜头配方（航拍、水下、微距、摇臂/滑轨、产品动态跟踪、延时、超现实合成）。把本包装进代理的 skills 目录并命名为 `kivo-ad-shots`，在 Claude Code 用 `/kivo-ad-shots` 调用。必须先报价、等数字上限，再跑 1–2 条低分辨率 Draft，质检通过后重新报价并二次确认，才升级 1080p 成片。本仓库是独立整理的工作方法，不是 Kivo 或字节的官方产品，不保证画质或效果。
