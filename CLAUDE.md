# caraway

caraway is a site for one editor. It collects bibliographic records of papers,
news, standards, and safety case documents on autonomous driving and physical
AI, lets the editor accept or decline each candidate, and organizes the
accepted documents by topic and by the relations between them. Readers come
later. `caraway` is a working name and may change.

## Read first

All documents are in Japanese under `docs/ja/`. Start at `docs/ja/index.md`
and read every document that your task touches before you change code.

- `docs/ja/requirements/overview.md` holds the goal, scope, and phases.
- Each area has its requirements page under `docs/ja/requirements/<area>/`.
- `docs/ja/requirements/technology.md` names each technology and why.
- `docs/ja/requirements/backlog.md` lists what is out of scope for now. Do not
  build those things.
- `docs/ja/architecture/overview.md` holds the package layout, the dependency
  rule, and how each layer is tested.
- Use the `cumin-trace-docs` skill before you write a requirement or design
  document.

## Rules that you must not break

- Do not change anything under `docs/ja/requirements/` without the
  Maintainer's approval in the conversation.
- Do not commit to `main`. Create a branch for every change.
- Do not read or print secret values: API keys, tokens, `.env` files.
- This repository is public. Never write personal circumstances, home network
  details, or local absolute paths in documents, code, tests, fixtures,
  commits, or pull requests.
- Never copy the text of a standard (ISO, SAE, UL, UNECE, and others) or the
  body of a paper or a news article into the repository, fixtures, or seed
  data. Keep bibliographic records, your own summaries, and links.

## How we work

- Requirement first. Every behavior traces to a requirement such as
  `CRW-SOURCE-003`. If no requirement covers a behavior, ask.
- Test first. A requirement verified by `test` gets a test that proves it.
- Verify external services (arXiv and other sources, Claude) in their official
  documentation before use, including their terms of use and rate limits, and
  say which page you checked.

## Code

- Go, standard library first, and built-in PostgreSQL features first. Module
  path: `github.com/cloveclovedev/caraway`.
- Feature packages under `internal/<feature>/` with `domain.go`, `service.go`,
  `store.go`, and `handler.go`; shared provider-neutral code in
  `internal/core/`; shared provider-specific code in `internal/platform/`;
  wiring in `cmd/`. Provider types stop at the adapter boundary.
- Pass dependencies through constructors and wire them only in `cmd/`. A
  service declares the small interfaces that it needs. No web framework, no
  ORM, no DI container.
- Read the time from an injected clock, not from `time.Now`.
- Code, comments, test names, commit messages, and pull requests are in
  English. Documents under `docs/ja/` are in Japanese.
- Do not write requirement IDs in code, comments, test names, or
  configuration files. Name them in issues and pull requests.

## Documents

- Requirements follow the cumin-trace format. Run `cumin-trace check` and
  `scripts/render-diagrams.sh` before you open a pull request.
- Diagrams are PlantUML with English labels; commit the `.puml` and the
  rendered `.svg` together.

## Commits and pull requests

- Conventional Commits, one purpose per pull request.
- A pull request says what changed, how it was checked, and whether documents
  changed.
