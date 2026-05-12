# omni-scrna benchmark

an universal single-cell benchmark, implemented as a collection of reusable [omnibenchmark](https://omnibenchmark.org) modules

**Plan:** https://github.com/omni-scrna/split-stages-plan

## Modules

| Stage     | Repository                                   | Tags                                    |
|-----------|----------------------------------------------|-----------------------------------------|
| Data      | https://github.com/omni-scrna/1-data         | `data`                                  |
| Filter    | https://github.com/omni-scrna/2-filter       | `methods`, `preprocessing`              |
| Normalize | https://github.com/omni-scrna/3-normalize    | `methods`, `preprocessing`              |
| Select    | https://github.com/omni-scrna/4-select       | `methods`, `preprocessing`              |
| Multiple  | https://github.com/omni-scrna/scanpy         | `methods`, `pca`, `graph`, `clustering`, `python` |
| Metrics   | https://github.com/omni-scrna/metrics        | `metrics`                               |


## Contributing

See the [COOKBOOK](https://github.com/omni-scrna/cookbook)! tl;dr:

1. Fork repo  
2. Create branch (`feat/<name>`)  
3. Follow module contracts
4. Add tests/examples  
5. Open PR with clear description  

### Add Method

- Decide which stage the module runs in
- Decide whether it's a tool-centric module, a language-centric module, or a new entrypoint on an existing module. This matters for how you organize the code in your repo.
- Follow the I/O schema for that stage 
- Handle your dependencies with pixi
- Export a conda environment in `envs/`

### Add Dataset

- Add to `1-data`
- Use [omni-data](https://github.com/btraven00/omni-data) if possible
- Include provenance + license in CITATION.cff for the data module
