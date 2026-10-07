# Uzo docs: rules for agents and automations

This file is the style guide for anyone, human or agent, who edits these docs. Mintlify automations (grammar, broken links, style guide, SEO, code changes, changelog) must follow it. The public version is `reference/contributing.mdx`. If the two disagree, this file wins and the public page should be fixed.

These are developer docs for Uzo Labs on BOT Chain, served at https://docs.uzolabs.xyz. Uzo Labs is independent and not affiliated with BOT Chain.

## Hard rules

Break none of these. If a fix would need to break one, leave the text alone and say so in the pull request.

1. **Never invent facts.** No made-up numbers, endpoints, addresses, prices, partners, sponsors, prizes or dates. If a fact can't be checked against a source repo or a live network, leave it out.
2. **Never present a planned Uzo product as live.** Pages about products that aren't live import a status snippet from `snippets/` (`status-planned`, `status-in-development`, `status-early-release`, `status-template-in-development`, `status-template-ready`). Don't remove them or change their wording.
3. **Never include secrets.** No private keys, mnemonics or API keys in pages, examples or commits. Examples read secrets from environment variables.
4. **Never copy text from BOT Chain's docs** (dev-docs.botchain.ai is "All rights reserved"). Facts such as chain IDs, URLs and addresses are fine. Write everything else in your own words and link to the source.
5. **No em dashes or en dashes anywhere**, including frontmatter, code comments and alt text. Use commas, colons, full stops or parentheses.
6. **Never add, move or rename pages.** Every page path must match `docs.json` exactly. Don't edit `docs.json` navigation.
7. **Keep pages focused.** If a page goes over about 1,500 words of prose, propose a split in the pull request instead of adding more.
8. **Never use Nsibidi or other sacred symbols** in images or decoration.

## Voice and tone

- Plain, direct and kind, for someone at a hackathon at 2 a.m.
- Second person ("you"). Keep sentences short, with one idea per paragraph.
- Start each page with what the reader will be able to do.
- No marketing language ("blazing fast", "seamless", "revolutionary", "cutting-edge").
- Avoid "simply", "just", "easy" and "obviously" when they tell the reader something is easy.
- "The user" is fine when it means the end user of the reader's app, such as the person signing a transaction.

## Spelling and naming

- **American English:** behavior, color, license, defense, math, organize, customize, canceled.
- Product names, exactly as written here: BOT Chain, BOT Chain Testnet (in network names and wallet UI), BOT, tBOT, WBOT, USDT, BDEX, BDEX V2, BDEX V3, BOTScan, Uzo, Uzo Labs, `@uzolabs/sdk`, dApp, MetaMask, Phantom, viem, wagmi, ethers, Foundry, Hardhat, Remix, Blockscout, Multicall3, Parlia, EIP-712, ERC-20, ERC-721.
- Don't expand "UNN".
- Dates: "October 3, 2026" in prose and changelog labels. "2026-10-01" is fine in "checked 2026-10-01" notes.

## Grammar and typo fixes: don't change these

Treat these as correct even if a spell checker flags them: tBOT, WBOT, BDEX, BOTScan, bohr, botchain, Parlia, wagmi, viem, ethers, anvil, cast, forge, giget, tsx, npx, Multicall3, Blockscout, Ponder, Pinata, paymaster, paymasters, relayer, relayers, keystore, calldata, nonce, nonces, ABI, ABIs, RPC, EOA, EVM, NFT, UNN, dApp, mainnet, testnet, on-chain, typechecked, upgradeable, unwrap, Nile, Sepolia, Tronscan, ajo, esusu.

Never change anything inside code blocks, inline code, URLs, addresses, transaction hashes, frontmatter keys or component props for grammar reasons.

## Frontmatter and SEO

- Every page has `title` and `description`. Keep any `sidebarTitle` and `icon` that are there.
- `title`: sentence case, under 60 characters, unique across the site.
- `description`: one sentence, 50 to 160 characters, unique, saying what the reader can do or learn. Name BOT Chain or the product where it fits naturally. No keyword stuffing.
- No `# H1` in the body (the title is the H1). Headings go `##` then `###` without skipping levels.
- Every image has descriptive `alt` text that says what the screenshot shows.
- Don't add `canonical`, `noindex` or other SEO keys without a reason stated in the pull request.

## Links

- Internal links are root-relative without the extension: `/get-started/quickstart`, not `../quickstart.mdx` or a full `https://docs.uzolabs.xyz/...` URL.
- Anchor links use Mintlify's heading slugs.
- External links use `https`.
- When an external link breaks, replace it with the new location of the same content. If there is none, remove the link and keep the text. Never point a link at a different source that says something else.

## Code

- Every code block has a language and a title: ` ```bash Terminal`, ` ```ts src/main.ts`, ` ```text Output`. Diagrams use ` ```mermaid` alone.
- Show alternatives with `<CodeGroup>`.
- Examples run on testnet as written, with no `...` gaps.
- Use testnet values by default: chain ID 968, RPC `https://rpc.bohr.life`, explorer `https://scan.bohr.life`, symbol tBOT. Show mainnet (chain ID 677) only on production pages, with a warning.
- Testnet USDT is `0x75edC9335175Fc0552D51D48439F229c10420fe3` with 6 decimals. Never use `parseEther` for USDT.

## Page shapes

| Page type | Shape |
| --- | --- |
| Concept | One-line summary, why it matters, how it works, related pages as cards |
| How-to | What you'll build, prerequisites, steps, how to check it worked, troubleshooting, next steps |
| Reference | Short intro, then tables or parameter fields. No narrative |

## Updating from code changes

Source repos: `uzolabs/uzo-sdk` (SDK pages under `sdk/`) and `uzolabs/templates` (template pages under `templates/`).

- Only document what is merged on `main` and released or published. Never document an unreleased branch as available.
- Keep exported names, function signatures, package versions and addresses exactly as the source has them.
- If a change can't be tested, don't present it as tested. Never touch the "Tested on testnet" tables or transaction links except to remove one that no longer applies.
- When a product changes status (for example a template ships), change the status snippet import. Don't hand-write a status line.

## Changelog

- Site changelog: `changelog.mdx`. SDK changelog: `sdk/reference/changelog.mdx`, which follows `CHANGELOG.md` in `uzolabs/uzo-sdk`.
- One `<Update label="Month D, YYYY" description="Short summary">` per entry, newest first.
- List user-visible changes only, grouped and linked to the pages that changed. No internal refactors, no hype.
- Only list changes that are merged. Never invent a release date or version.
