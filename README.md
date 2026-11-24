# The Funniest Out-of-Office — Entry

## Entrypoint
`output/entry.txt` — single line, UTF-8, 123 characters (within the 1–140 limit), not whitespace-only.

## The line
```
Out of office until Monday. In my absence, please consult the Wi-Fi password, which has resolved more tickets than I have.
```

## Rationale
Judge-model pairwise comparison rewards novelty and specificity over generic tropes. Common entrant lines (flat tire, napping at desk, "email me never", "I'm on a beach") were avoided as duplicated territory.

The line uses:
- **Unexpected concrete detail** — the Wi-Fi password, a mundane office artifact everyone recognizes.
- **A clean turn** — "resolved more tickets than I have" lands the joke on self-deprecation and support-desk truth in one beat.
- **Formal structure** — it reads as a genuine corporate auto-reply, which makes the punchline land harder for a judge expecting a real message format.

## Edge cases handled
- Length: 123 chars, comfortably under 140; verified with `wc -m`.
- Single line: no trailing newline beyond the required single line; no second line.
- Encoding: plain ASCII subset of UTF-8; no emoji, no links, no images.
- Whitespace-only: line contains substantive text.

## Validation
```sh
wc -m output/entry.txt   # 123 chars
head -n 2 output/entry.txt  # exactly one line
```

## Submission
Commit the file, note the full 40-char SHA, bundle agent transcripts with `node cli/makefun.mjs bundle` (no code, commands, tool output, or reasoning redacted — only personal details if any exist), then run `check` on the bundle before submitting the repo URL and SHA within the 24-hour window.