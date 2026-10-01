# Uzo docs

Source for [docs.uzolabs.xyz](https://docs.uzolabs.xyz), the developer docs for Uzo Labs. Built with [Mintlify](https://www.mintlify.com).

Uzo Labs is an independent project and is not affiliated with or endorsed by BOT Chain.

## Run locally

You need Node.js 20.17 or newer.

```bash
npm i -g mint
mint dev
```

The site opens at http://localhost:3000.

Before you open a pull request, run the same checks CI runs:

```bash
mint validate
mint broken-links
```

## Add a page

1. Create an `.mdx` file. Its path is its URL, for example `guides/data/multicall.mdx` is served at `/guides/data/multicall`.
2. Add frontmatter with `title`, `description` (one sentence, under 160 characters) and, optionally, a Lucide `icon`.
3. Add the path, without `.mdx`, to the right group in `docs.json`. Don't add, move or rename pages without agreeing it in an issue first.

## Status snippets

Pages about products that are not live import a snippet from `snippets/`, so a status change is one edit:

| Snippet | Use on |
| --- | --- |
| `status-in-development.mdx` | SDK and template pages |
| `status-planned.mdx` | Planned services, such as Uzo RPC and Uzo Index |
| `not-affiliated.mdx` | Home page and disclaimer |
| `testnet-only.mdx` | Pages where every example uses testnet |

## Style rules

The full guide is on the [contributing page](https://docs.uzolabs.xyz/reference/contributing). The short version:

- Plain, direct and friendly. Second person, short sentences.
- No em dashes. No marketing language.
- Every code block has a language. Examples run on testnet as written.
- Never commit a private key, mnemonic or API key. Read secrets from environment variables.
- Never present a planned product as live.

## Licence

Text is licensed under CC BY 4.0. Code snippets are licensed under MIT. See [LICENSE](LICENSE).
