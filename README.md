# chessnote-plug-repertoire

ChessNote's opening repertoire plug: indexes `tags: repertoire` pages'
`pgn` blocks as repertoire lines, and drills them with an SM-2 spaced-
repetition scheduler ("Chess: Ôn tập khai cuộc" command).

## ⚠️ Not independently installable

This is a **mirrored source snapshot** of `plugs/chess-repertoire/` from the
main [chessnote](https://github.com/covuaduongsinh/chessnote) monorepo, kept
as a separate repository for clearer version tracking of this one feature
area.

It is **not** a standalone, installable SilverBullet plug:

- It depends on `chessSql` — a custom syscall backed by an embedded SQLite
  WASM database that exists only in ChessNote's own client build (see
  `client/data/chess_sql_store.ts` in the main repo), not in vanilla
  SilverBullet.
- It also calls chess-core's `chess.isRepertoirePage` syscall.
- The actual build (compiling this into a `.plug.js`, registering it in
  `plugs/builtin_plugs.ts`) happens in the main chessnote repo, not here.

To use or modify this code, work in the main
[chessnote](https://github.com/covuaduongsinh/chessnote) repo instead — this
repo exists for reference and history, not standalone development.
