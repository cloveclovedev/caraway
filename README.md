# cardamap

A site that curates and organizes research, safety cases, and standards on
autonomous driving and physical AI.

The project is at the requirements stage. There is no code yet.

The documents are in Japanese, under [docs/ja/](docs/ja/). They follow the
format of [cumin-trace](https://github.com/cloveclovedev/cumin-trace), and
`cumin-trace check` runs on every pull request.

Files named `*.ref.md` are reference drafts, not decisions. Each one is
removed once the document beside it is written.

```sh
cumin-trace check            # checks the format of the requirement documents
scripts/render-diagrams.sh   # renders every PlantUML diagram to SVG (needs Docker)
```
