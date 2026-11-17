# caraway

A site that collects papers, news, standards, and safety case documents on
autonomous driving and physical AI, lets one editor pick what matters, and
organizes how they relate by topic.

`caraway` is a working name and may change.

The project is at the requirements stage. There is no code yet.

The documents are in Japanese. Start at [docs/ja/index.md](docs/ja/index.md).
They follow the format of
[cumin-trace](https://github.com/cloveclovedev/cumin-trace), and
`cumin-trace check` runs on every pull request.

## Planned stack

Go (standard library first), PostgreSQL, `html/template` with htmx, and Docker
Compose. The reasons are in
[docs/ja/requirements/technology.md](docs/ja/requirements/technology.md).

## Work on the documents

```sh
cumin-trace check            # checks the format of the requirement documents
scripts/render-diagrams.sh   # renders every PlantUML diagram to SVG (needs Docker)
```
