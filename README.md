# Imagen Search

Find article illustrations with your AI assistant. Search [Imagen Chat](https://imagen.chat/skills/imagen-search) and return numbered Markdown images; ask to replace image 2 while preserving the other placements.

[中文使用指南](https://imagen.chat/zh/skills/imagen-search) · [English guide](https://imagen.chat/en/skills/imagen-search) · [Privacy](https://imagen.chat/privacy)

## Install

Requires **Node.js 22+**. This Skill has no npm runtime dependencies.

```sh
npx skills add liu-cn/imagen-search --skill imagen-search
```

Alternatively, ask your AI assistant:

> Read https://imagen.chat/install/imagen-search.md and install Imagen Search. Verify the published ZIP hash before installing.

Direct download (unzip and place `imagen-search` in your assistant's supported Skill directory):

```sh
curl -fL 'https://imagen.chat/downloads/imagen-search.zip?source=github' -o imagen-search.zip
```

The [release manifest](https://imagen.chat/downloads/imagen-search-release.json) contains the current version, immutable download URL, ZIP SHA-256 and per-file hashes. The optional Python installer stages upgrades, checks hashes, retains a backup and preserves external credentials and user files. The AI attempts one update check on first use in a conversation unless you decline or request offline operation. It shows release changes and offers an upgrade; checks do not run in the background or block search on failure. Installed files change only with your upgrade authorization.

## First search

Ask: “Find images for an article about ancient Rome; number each placement so I can replace one later.”

Or from this installed folder:

```sh
node scripts/imagen.mjs start --query "ancient Rome" --out /absolute/path/to/new-first-search
node scripts/imagen.mjs search --query "Roman aqueduct" --limit 6
node scripts/imagen.mjs version
node scripts/imagen.mjs version --check
```

The new output folder contains candidates, a reusable image manifest and numbered Markdown. Say “replace image 2” to update that slot. Images are AI illustrations; assess relevance and do not treat them as documentary evidence. Remote image rendering depends on the host. Public links can be embedded in compatible webpages; local downloads are available when requested.

## Free images and original access

- **Free:** anonymous watermarked search, public watermarked links and downloads. Preserve watermarks and follow each image's usage terms.
- **Originals:** create an Imagen API key on the website. A new unlock costs 1 credit; already unlocked images do not cost another unlock credit. Download grants remain subject to daily quotas.
- Original links are temporary (normally about five minutes), not permanent hosting. Download originals into your project or separately authorized hosting for long-lived use.
- Configuring a key does not authorize spending. The assistant must follow the user's credit budget. Store credentials outside this Skill and never paste them in prompts, issues or public files.
- Optional loopback-only selection and account panel; search does not require opening it.

## Privacy

Searches send only necessary terms to Imagen, not the full article or conversation. Version 1.2.0 uses a dedicated uncached endpoint with anonymous operational counters (requests, version, errors, result counts and latency) retained for 90 days, without query text, IPs, accounts, keys or persistent visitor identifiers as analytics fields. **Keyword retention defaults off**. Only explicit human opt-in enables successful short-term aggregates for up to 30 days; basic sensitive-data filtering is incomplete, so never send secrets. View preferences with `node scripts/imagen.mjs analytics`; after consent use `analytics --keywords on --confirm`; turn off with `analytics --keywords off`. Preferences remain outside the package and survive upgrades. Turning off stops future term retention; existing anonymous aggregates expire on schedule and cannot be located by person. An hourly task prunes expired records in batches. There is no extra analytics beacon or installation identifier. Operational metrics count requests, not users, installs or image adoption. Optional unmet-demand submissions require a preview and explicit user consent. The official website records coarse ZIP delivery statistics (UTC time, country/region codes, file, client category and source label), without storing raw IPs, accounts, full user agents or referrer URLs in these records. Third-party installers may have their own installation telemetry; consult their policies. Downloads from mirrors cannot be counted by the Imagen website.

## 中文说明

让 AI 为文章搜索配图，输出带编号的 Markdown，支持“图 2 换一个”。水印图免费搜索、使用链接和下载；原图需要 API Key 和积分，返回临时链接或下载文件。API Key 不要粘贴到聊天或公开文件。是否合适由用户判断；本地网页只是可选的比较与选择能力。新版基础搜索指标保留 90 天；关键词统计默认关闭，明确同意后才保留最长 30 天，随时可关闭。每个会话首次使用尝试检查新版，升级前获得授权；不会后台轮询或擅自覆盖文件。安装与升级详见官网指南。

## License and service terms

Skill code is licensed under **MIT-0**; see [LICENSE](LICENSE). This code license does not license Imagen catalog images, trademarks or the hosted API. Image usage permissions, account credits and hosted service terms remain separate: [terms](https://imagen.chat/terms), [image license](https://imagen.chat/content-license).

This repository contains only the public Skill, with no website/backend source, customer data or credentials. Registry listing does not imply endorsement. Report issues here without secrets or temporary original-image links.
