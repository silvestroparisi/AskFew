# AskFew

**A private AI, right in your browser — no cloud, no account, nothing uploaded.**

AskFew is part of the **Few** toolkit, alongside [FirstFew](https://github.com/silvestroparisi/FirstFew), [FixFew](https://github.com/silvestroparisi/FixFew) and [MaskFew](https://github.com/silvestroparisi/MaskFew).
It runs a real language model entirely on your own device, so you can use AI without sending a single word to anyone.

It's a single, self-contained web page. No backend, no build step, no upload, no tracking.

🔗 **Live:** https://silvestroparisi.github.io/AskFew/

> Want AI without the cloud? Ask the one that never leaves your browser.

## Why

Every prompt you type into a cloud AI leaves your device — it's sent to a server, often stored, sometimes used to train the next model. The private alternatives (Ollama, LM Studio, llama.cpp) are powerful, but built for technical users: terminals, downloads, configs. So most people end up choosing between privacy and AI.

AskFew removes that choice. It opens like any web page and runs a model **locally**, on your computer's own graphics hardware, using WebGPU. Your questions and the model's answers never leave the browser.

## Private by default

- The model runs **entirely in your browser's memory**, on your GPU. There is no server, no account, and nothing you type is uploaded.
- The only thing that comes *in* is the model itself, downloaded once from a public CDN and then cached — after that it can run offline.
- Don't trust the claim? You don't have to — it's open source. Open your browser's DevTools → Network: you'll see the model download once, and after that nothing about your conversation ever leaves your device.

## What it can do

Drafting and rewriting text, summarizing something you paste in, answering everyday questions, brainstorming. It's a small local model, so it won't match a giant cloud AI on hard reasoning — but for a lot of daily tasks it's more than enough, and completely private.

## The honest trade-off

A model small enough to run in a browser is **not** as capable as a frontier cloud model, and **the more powerful your computer, the faster it runs** — that's the price of keeping everything local. The first reply may be slow while the model warms up. Treat its answers as a helpful first draft, and verify anything that matters: a small local model can be confidently wrong.

## Requirements

- A browser with **WebGPU** — desktop **Chrome or Edge** work best. Support in Safari and Firefox is improving; on phones it's still limited. If your browser can't run it, AskFew tells you so instead of failing silently.
- Room for the model: the first load downloads it once (from **~0.9 GB** for the smallest), then keeps it cached.

## How to use

1. Open the page in a WebGPU browser.
2. Pick a model size — **Small** (fast, runs on most laptops), **Medium** (balanced), or **Large** (needs a strong GPU / PC).
3. Click **Load model**. The first time it downloads the model (one-time); after that it loads almost instantly from cache.
4. Chat. Everything stays on your device.

## Models

AskFew uses the open-source [WebLLM](https://github.com/mlc-ai/web-llm) engine with prebuilt MLC model builds — by default small **Llama 3.2 / Llama 3.1 Instruct** models. The bigger the model, the more capable it is and the more hardware it needs; pick the size that matches your machine.

## Run it yourself

It's one file. Open `index.html` over `http(s)://` (not `file://`, so WebGPU and the on-demand library import work), or host it for free:

1. Create a repository named `AskFew`.
2. Add `index.html` to the repository root.
3. Enable **GitHub Pages** (deploy from branch `main`, folder `/root`).

## Tech

Vanilla HTML / CSS / JavaScript, no framework, no build.
In-browser inference: [WebLLM](https://github.com/mlc-ai/web-llm) (MLC) over WebGPU, loaded on demand from a CDN; model weights are fetched once and cached. Bilingual (IT/EN), dark/light themes.

## The Few toolkit

- [**FirstFew**](https://github.com/silvestroparisi/FirstFew) — prioritize the few that matter
- [**FixFew**](https://github.com/silvestroparisi/FixFew) — verify and remediate
- [**MaskFew**](https://github.com/silvestroparisi/MaskFew) — anonymize a file before you share it
- **AskFew** — a private AI that runs in your browser

## License

[MIT](LICENSE) © 2026 Silvestro Parisi
