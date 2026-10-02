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

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 (GPL-3.0).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md). **If you distribute what you changed, you must publish it under the same terms.**
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code** (the tests and the code are generated from them). When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (for example the Java runtime and libraries inside the release ZIPs) remain under their own original licenses.
- Provided "as is", without warranty — as the GPL-3.0 text says.
