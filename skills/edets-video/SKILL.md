---
name: edets-video
description: Generate edets video clips and campaigns with prepaid seconds. Use when the user wants a clip from a still, edets Max or edets Motion, a multi-shot campaign, or remaining seconds. Do not describe seconds as complimentary.
---

# edets video

## When to generate a clip

Use `generate_video` when the user has (or can give) a still URL and a full-sentence motion prompt. A mood word is not enough. Call `check_balance` first if remaining prepaid seconds are unknown.

Do not generate when the user only wants REST docs, key minting, or a status poll.

## Seconds

Currency is prepaid seconds of clip time. One generated second burns one second. This is not takes and not casino chips. Failed jobs return seconds to the pool. Do not describe prepaid seconds as complimentary.

## edets Max vs edets Motion

- `quality: "max"` — edets Max. Higher fidelity. `size=720` is 768P.
- `quality: "motion"` — edets Motion. Faster motion path. `size=720` is 720P.
- Public sizes are `480` and `720` only. Aspect is `9:16`, `1:1`, or `4:5`. Length is 5–15 seconds.

## Tools

1. `check_balance` — remaining prepaid seconds and dollar equivalent.
2. `generate_video` — still URL + prompt + quality + seconds. Returns a generation id.
3. `check_status` — poll that id until succeeded or failed.
4. `create_campaign` — multi-shot IG/TT/FB. Campaigns do not auto-compose.
5. `compose_campaign` — stitch master and packs after shots succeed.

Connect at `https://edets.com/api/mcp` with `Authorization: Bearer` and an `edets_live_…` key from https://edets.com/api/keys.
