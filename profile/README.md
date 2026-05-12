# omni-scrna benchmark

an universal single-cell benchmark, implemented as a collection of reusable [omnibenchmark](https://omnibenchmark.org) modules

**Plan:** https://github.com/omni-scrna/split-stages-plan

## Modules

| Stage     | Repository                                   | Tags                                    |
|-----------|----------------------------------------------|-----------------------------------------|
| Data      | https://github.com/omni-scrna/1-data         | `data`                                  |
| Filter    | https://github.com/omni-scrna/2-filter       | `methods`, `preprocessing`              |
| Normalize | https://github.com/omni-scrna/3-normalize    | `methods`, `preprocessing`              |
| Select    | https://github.com/omni-scrna/4-select       | `methods`, `preprocessing`, `r`         |
| Select    | https://github.com/omni-scrna/4-select-py    | `methods`, `preprocessing`, `python`    |
| Multiple  | https://github.com/omni-scrna/scanpy         | `methods`, `pca`, `graph`, `clustering`, `python` |
| Multiple  | https://github.com/omni-scrna/scrapper       | `methods`, `pca`, `r`                   |
| Multiple  | https://github.com/omni-scrna/rapids-singlecell | `methods`, `pca`, `graph`, `clustering`, `python`, `gpu`    |
| Metrics   | https://github.com/omni-scrna/metrics        | `metrics`                               |


## Contributing

### Add/Change Method

- Decide which stage the module runs in
- Decide whether it's a tool-centric module, a language-centric module, or a new entrypoint on an existing module. This matters for how you organize the code in your repo.
- Follow the I/O schema for that stage

### Add Dataset

- Add to `1-data`
- Use [omni-data](https://github.com/btraven00/omni-data) if possible
- Include provenance + license in CITATION.cff for the data module

### Test changes in the benchmark

1. Pick an [open task](https://github.com/orgs/omni-scrna/projects/1)
2. Fork the plan repo
3. Create branch (`feat/<name>`). Ideally, same branch name across all the linked PRs.
4. Follow module contracts for I/O
5. Open [a PR to the plan](https://github.com/omni-scrna/split-stages-plan/pulls) with clear description  
