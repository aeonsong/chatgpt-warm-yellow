# Lazy Chat Userscripts

Two lightweight userscripts for long AI chats:

- **ChatGPT Lazy Chat++** — detach-based DOM virtualization, HARD PAUSE during streaming, lightweight TOC, search, pinned navigation, lazy heading index, and a low-contrast UI.
- **Gemini Lazy Chat++** — TOC-first navigation with conservative conditional detach only for longer chats, plus HARD PAUSE during generation.

These were **vibe coded** for my own day-to-day use: ChatGPT is the primary target, Gemini is secondary. The design goal is practical rather than ambitious — keep long chats responsive and make old turns easy to navigate without constantly scanning or rendering the whole conversation.

## Install

Use a userscript manager such as Tampermonkey.

### ChatGPT

Raw install/source:

`https://raw.githubusercontent.com/aeonsong/chatgpt-warm-yellow/main/userscripts/chatgpt-lazy-chat.user.js`

Target:

`https://chatgpt.com/*`

### Gemini

Raw install/source:

`https://raw.githubusercontent.com/aeonsong/chatgpt-warm-yellow/main/userscripts/gemini-lazy-chat.user.js`

Target:

`https://gemini.google.com/*`

## Design notes

### ChatGPT version

The ChatGPT script keeps a small recent window connected to the DOM and detaches older turns. It also keeps a lightweight in-memory TOC so old user turns can still be located without restoring the entire conversation. During streaming, the lazy-chat DOM work is paused.

### Gemini version

The Gemini script is intentionally more conservative. The TOC is always available, while detach only activates after the currently loaded DOM reaches a threshold. This avoids needlessly fighting Gemini's own Angular rendering lifecycle on shorter conversations.

## References / acknowledgements

This work was heavily informed by these projects:

- [AlexSHamilton/chatgpt-lazy-chat-plusplus](https://github.com/AlexSHamilton/chatgpt-lazy-chat-plusplus) — the key reference for long-chat lazy rendering / detach modes, HARD PAUSE during streaming, idle batching, and the original ChatGPT Lazy Chat++ approach. The ChatGPT userscript here is a modified/extended derivative and retains GPL-3.0-or-later licensing.
- [lyw123www/GptToc](https://github.com/lyw123www/GptToc) — reference for the UX idea of a question TOC, clickable navigation, and optional answer sub-headings. I used it as a design reference rather than copying its extension code; the repository does not currently expose a LICENSE file.

The integrated implementation combines those ideas around a single principle: **the TOC should understand the virtualization layer instead of running as a separate full-DOM scanner.**

## Privacy / network behavior

The scripts do not intentionally make external network requests and do not include token estimation. They operate on the current page DOM and keep only small navigation metadata in memory/local browser storage where needed.

## Maintenance warning

Both ChatGPT and Gemini change their web DOM frequently. Selectors can break. Treat these as practical personal tools rather than stable platform APIs.

## License

- `chatgpt-lazy-chat.user.js`: GPL-3.0-or-later.
- `gemini-lazy-chat.user.js`: GPL-3.0-or-later.

The existing Warm Yellow UserStyle in the repository keeps its own licensing terms.