# edets for Cursor

Generate edets Max and edets Motion clips from a still, over hosted Streamable HTTP.

Prepaid seconds. Not takes. Mint a Bearer key at [edets.com/api/keys](https://edets.com/api/keys).

## Installation

### Cursor Marketplace

Not listed yet. After listing, install from [Cursor Marketplace](https://cursor.com/marketplace) by searching **edets**.

### From source (local)

Cursor scans `~/.cursor/plugins/local/<name>/` for local plugins:

```bash
git clone https://github.com/Mikey-Rodriguez/edets-cursor-plugin.git
mkdir -p ~/.cursor/plugins/local
rsync -a --delete --exclude='.git' edets-cursor-plugin/ ~/.cursor/plugins/local/edets/
```

Reload Cursor: `Cmd-Shift-P` then Developer: Reload Window.

1. Customize → Plugins lists **edets**.
2. Plugins → Configure, set `EDETS_API_KEY` to your `edets_live_…` key.
3. Customize → MCPs shows `edets`. `tools/list` should return five video tools.

## Connect

- Protocol URL: `https://edets.com/api/mcp`
- Header: `Authorization: Bearer ${EDETS_API_KEY}`
- Mint once at https://edets.com/api/keys. The secret is shown once.

Never commit a live key.

## Tools

| Tool | What it does |
| --- | --- |
| `check_balance` | Remaining prepaid seconds |
| `generate_video` | Still URL + sentence → generation id |
| `check_status` | Poll until clip URL |
| `create_campaign` | Multi-shot IG/TT/FB (does not auto-compose) |
| `compose_campaign` | Stitch master and packs |

`quality=max` is edets Max (`size=720` is 768P). `quality=motion` is edets Motion. Public sizes 480 and 720. Length 5–15 seconds, burned 1:1.

## Docs

- Marketing: https://edets.com/mcp
- Setup: https://edets.com/docs/mcp
- REST: https://edets.com/api
- Privacy: https://edets.com/privacy
- Terms: https://edets.com/terms

## License

MIT. See [LICENSE](./LICENSE).

## Support

- Issues: https://github.com/Mikey-Rodriguez/edets-cursor-plugin/issues
- Product: https://edets.com
