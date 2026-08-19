# Mining existing land cover products for ensemble classification

OpenGeoHub Summer School 2026 — hands-on tutorial.

## About

Multiple global and regional land cover products already exist — yet they often disagree in accuracy, legend, resolution, and format. This tutorial treats existing products as inputs to combine, rather than picking a single "best" one.

Two complementary strategies are covered:

- **Part 1 — Data-driven ensemble.** A classifier is trained on labeled reference points to learn which land cover products to trust, and in which combinations, for each class.
- **Part 2 — Rule-based ensemble.** A human expert writes explicit if-then rules, in priority order, that combine several products directly. No training data required, fully transparent and auditable.

## Getting started

Open `tutorial.ipynb` in Google Colab:

![Open In Colab](https://colab.research.google.com/github/mmorenoz/elc-ogh-summer-school-2026/blob/main/tutorial.ipynb)

Or clone the repo and run it locally with Jupyter:

```bash
git clone https://github.com/mmorenoz/elc-ogh-summer-school-2026.git
cd elc-ogh-summer-school-2026
pip install -r requirements.txt
jupyter notebook tutorial.ipynb
```
## Repository structure

```
elc-ogh-summer-school-2026/
├── README.md
├── LICENSE
├── requirements.txt
├── tutorial.ipynb
├── data/                # reference points and pre-clipped land cover products
└── results/             # output placeholder
```

## Data

The tutorial uses:

- The [GELC harmonized reference dataset](https://zenodo.org/records/15594682) (OpenGeoHub, Zenodo)
- Global 30m land cover products: GLanCE, GLC-FCS30D, GLAD-GLCLUC, NLCD
- ESA WorldCereal (maize) and Global Pasture Watch (GPW) layers, for Part 2

The data required to run the tutorial is automatically downloaded by the notebook's setup cells and is not stored in this repository. See the notebook for source URLs.

## Requirements

See `requirements.txt`. GDAL command-line tools (`gdalwarp`, `gdalbuildvrt`) are also required for the raster clipping/alignment steps.

- **Google Colab**: already available, no setup needed.
- **Linux (Debian/Ubuntu)**: `sudo apt-get install -y gdal-bin`
- **macOS**: `brew install gdal`
- **Windows**: `conda install -c conda-forge gdal`

## Acknowledgments

This research was supported by multiple grants, including the IFAD grant
“Capitalising on Earth Obser vation Data to support Project
Design, Implementation and Evaluation”.

**[EarthMonitor.org](https://EarthMonitor.org/)** project has received
funding from the European Union’s Horizon Europe research an innovation
programme under grant agreement
**[No. 101059548](https://cordis.europa.eu/project/id/101059548)**.

**[GeoAI toolbox for Epidemic Intelligence](https://GeoAI4EI.eu/)** has
received funding from the European Union’s Horizon Europe research an
innovation programme under grant agreement
**[No. 101287260](https://cordis.europa.eu/project/id/101287260)**.

## License

Code in this repository is released under the MIT License — see `LICENSE`.

Underlying land cover products and the GELC reference dataset each carry their own licenses from their original providers. Consult each source before reuse.