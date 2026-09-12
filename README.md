# chessnote-plug-repertoire

A standalone SilverBullet plug: indexes `tags: repertoire` pages' `pgn`
blocks as repertoire lines, and drills them with an SM-2 spaced-repetition
scheduler ("Chess: Ôn tập khai cuộc" command) — extracted from
[ChessNote](https://github.com/covuaduongsinh/chessnote) (a chess-focused
SilverBullet fork).

## Install

**Install 2 dependencies first, in this order** (each is its own standalone
plug — see its README for its own install URL):

1. [`chessnote-plug-db`](https://github.com/covuaduongsinh/chessnote-plug-db)
2. [`chessnote-plug-core`](https://github.com/covuaduongsinh/chessnote-plug-core) (which itself needs `chessnote-plug-themes` and `chessnote-plug-engine` first)

Then, in SilverBullet, run the **"Library: Install"** command and paste this
URL:

```
https://raw.githubusercontent.com/covuaduongsinh/chessnote-plug-repertoire/main/chess-repertoire-library.md
```

This pulls in `chess-repertoire.plug.js` (the compiled plug) along with the
library page. After installing, run **"Plugs: Reload"** if it doesn't load
automatically.

## What it provides

- Indexes every ```pgn``` block on a `tags: repertoire` page as one
  repertoire line, reading `side`/`eco`/`openingName` from the page's own
  frontmatter and `[Variation "..."]` per block.
- "Chess: Ôn tập khai cuộc" — quizzes you move-by-move on due lines and
  reschedules the next review via SM-2 based on mistakes made.

See `libraries/Library/Chess/Templates/Opening_Repertoire.md` in the main
[chessnote](https://github.com/covuaduongsinh/chessnote) repo for the
expected page template.

## Development

Source lives here **and** as `plugs/chess-repertoire/` in the main
[chessnote](https://github.com/covuaduongsinh/chessnote) monorepo, which is
where `chess-repertoire.plug.yaml` actually gets compiled during ChessNote's
own build (`npm run build:plugs`). This repo's `chess-repertoire.plug.js` is
a manually-published snapshot — after changing the source here (or there),
rebuild and re-copy the compiled `.plug.js` to keep this repo's install URL
up to date.

To compile it yourself from this repo directly, you'll need SilverBullet's
plug-compile tooling (see [Plug
Development](https://silverbullet.md/Plugs/Development) docs) pointed at
`chess-repertoire.plug.yaml`, with the 2 dependency plugs above already
installed in the target Space (this plug only calls their syscalls by name
at runtime — it doesn't need their source to build).
