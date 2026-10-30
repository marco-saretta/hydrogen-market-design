# Towards European Hydrogen Market Design: Perspectives from Transmission System Operators

[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.enpol.2026.115634-blue)](https://doi.org/10.1016/j.enpol.2026.115634)
[![Code license: MIT](https://img.shields.io/badge/code%20license-MIT-green)](LICENSE)
[![Paper license: CC BY 4.0](https://img.shields.io/badge/paper%20license-CC%20BY%204.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)

This repository contains the figures, data, scripts, survey questionnaire and supplementary material for the paper:

> Marco Saretta, Enrica Raheli, Jalal Kazempour (2027).
> **Towards European hydrogen market design: Perspectives from transmission system operators.**
> *Energy Policy*, 220, 115634. <https://doi.org/10.1016/j.enpol.2026.115634>

The article is open access.

## Overview

Only a small share of renewable hydrogen projects in Europe have reached final investment decision, partly because it is unclear how future hydrogen markets will be designed and operated. This study asks how far hydrogen market design can be adapted from existing EU natural gas markets, and which challenges early hydrogen markets must address.

The analysis is based on a structured survey of **seven European gas Transmission System Operators (TSOs) from six countries** (Belgium, Denmark, France, Germany, Lithuania and the Netherlands). It covers five areas: market and regulatory design, trading, capacity allocation, tariffs, and balancing.

### Key findings

- Core design principles, such as **entry-exit systems, virtual trading points and over-the-counter trading**, transfer from natural gas.
- **Capacity allocation** needs targeted adaptation to couple better with electricity markets.
- **Tariffs** need intertemporal cost allocation to protect early network users.
- **Balancing** needs redesign: three Member States chose three different models. A hydrogen balancing Network Code is needed before networks interconnect.
- Main challenges for early markets: variable renewable supply against stable industrial demand, limited flexibility (scarce storage, low linepack), fragmented regional clusters, and regulatory uncertainty.

## Repository structure

```
├── data/                     # Input data for the plots
├── figures/                  # Figures from the paper and supplementary material
├── paper/                    # Published article (open access)
├── scripts/                  # Python scripts for data download and plots
├── supplementary_material/   # Background on EU gas market concepts
└── survey/                   # Questionnaire sent to the TSOs
```

## Reproducing the plots

The scripts need Python 3.12 or later. Dependencies are managed with [uv](https://github.com/astral-sh/uv):

```bash
pip install uv   # if uv is not installed yet
uv sync          # install dependencies from pyproject.toml / uv.lock
```

Then run any script, for example:

```bash
uv run scripts/plot_capacity.py
uv run scripts/plot_SBS.py
uv run scripts/plt_ttf_prices.py
```

Plots are saved to `figures/`. Notes:

- `plt_ttf_prices.py` downloads TTF prices from Yahoo Finance (via `yfinance`) for the last 10 years, so the result changes with the run date.
- `api_pipelines.py` queries the online Hydrogen Infrastructure Map and overwrites `data/pipeline_project.csv`.

## Survey data and anonymity

The questionnaire is in [`survey/`](survey/). The individual survey responses are **not** published. In line with the paper's data availability statement, they are available from the corresponding author on request.

Anonymity was guaranteed both to the TSOs and to individual respondents. Results are reported at country level only.

## Citation

If you use this material, please cite the article:

```bibtex
@article{saretta2027hydrogen,
  title   = {Towards European hydrogen market design: Perspectives from transmission system operators},
  author  = {Saretta, Marco and Raheli, Enrica and Kazempour, Jalal},
  journal = {Energy Policy},
  volume  = {220},
  pages   = {115634},
  year    = {2027},
  doi     = {10.1016/j.enpol.2026.115634}
}
```

To cite the repository itself, use the metadata in [`CITATION.cff`](CITATION.cff) (or the "Cite this repository" button on GitHub).

## Acknowledgements

This work is part of the Industrial PhD project "Commoditizing green hydrogen in Europe: from efficient market design to optimal contracting and investment", funded by Innovation Fund Denmark (grant 4297-00039B), Ramboll Fonden and Ramboll Denmark A/S. We thank all the European gas TSOs who took part in the survey.

## License

- **Code** (`scripts/`): [MIT](LICENSE).
- **Paper and figures**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), as published in *Energy Policy*.

## Contact

Marco Saretta, Technical University of Denmark: <mcsr@dtu.dk>
