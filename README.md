# dev_mgmt

The development-management system used in the books:

- **Vol. 1** — 『LLMで100万行のソフトウェア開発への道』
  (*The Road to One Million Lines of Software with LLMs*)
  The approach and the system: how a development is tied into one chain.
- **Vol. 2** — 『LLM で 100 万行のソフトウェア開発 II — Windows と Android のオセロを同時に作る』
  Building Othello for Windows and Android with this system, from requirements to tests.

1 巻は、この系の考え方と仕組み。2 巻は、この系でオセロを Windows と Android で作る本です。

## What it does

Every artifact is tied into one chain:

    REQ → DD (design doc) → Code → TS (test spec) → TC (test code) → TR (test result)

When an upstream item changes, everything downstream is automatically marked non-current.
"Pretend it passed", "empty test" and "skip the parent" are rejected by a gate at registration
time, or exposed by an audit afterwards.

要求から設計書、コード、試験仕様、試験コード、試験結果までを 1 本の鎖に結び、
捏造・二重化・版ズレが起きないようにします。

## Related repositories (Vol. 2)
- Othello built with this system: https://github.com/skogita/Othello-Game
- Donut Othello (Vol. 2 appendix): https://github.com/skogita/Donut-Othello-Game

## Requirements
- Python 3.11+ and `pip install jsonschema`
- Windows dashboard: Kotlin/Compose

## Start
See `docs/manuals/USER_MANUAL.md` and `docs/manuals/SYSTEM_MANUAL.md` (Japanese).
