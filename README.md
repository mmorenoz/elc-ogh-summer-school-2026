# Mining existing land cover products for ensemble classification

OpenGeoHub Summer School 2026 — hands-on tutorial.

## About

Multiple global and regional land cover products already exist — yet they often disagree in accuracy, legend, resolution, and format. This tutorial treats existing products as inputs to combine, rather than picking a single "best" one.

Two complementary strategies are covered:

- **Part 1 — Data-driven ensemble.** A classifier is trained on labeled reference points to learn which land cover products to trust, and in which combinations, for each class.
- **Part 2 — Rule-based ensemble.** A human expert writes explicit if-then rules, in priority order, that combine several products directly. No training data required, fully transparent and auditable.

## Getting started

Open `tutorial.ipynb` in Google Colab:

[![Open In Colab](https://colab.research.google.com/drive/1rk4SKFF-tJCfQearcAGW9iXO30DNt5do#scrollTo=1996d79f)

Or clone the repo and run it locally with Jupyter:

```bash
git clone https://github.com/mmorenoz/elc-ogh-summer-school-2026.git
cd elc-ogh-summer-school-2026
pip install -r requirements.txt
jupyter notebook tutorial.ipynb
```

## Data

The tutorial uses:

- The [GELC harmonized reference dataset](https://zenodo.org/records/15594682) (OpenGeoHub, Zenodo)
- Global 30m land cover products: GLanCE, GLC-FCS30D, GLAD-GLCLUC, NLCD
- ESA WorldCereal (maize) and Global Pasture Watch (GPW) layers, for Part 2

Data required to run the tutorial is downloaded automatically by the notebook's setup cells and is not stored in this repository. See the notebook for source URLs.

## Requirements

See `requirements.txt`. GDAL command-line tools (`gdalwarp`, `gdalbuildvrt`) are also required for the raster clipping/alignment steps — install with `apt-get install -y gdal-bin` on Debian/Ubuntu-based systems (already available on Google Colab).


## Acknowledgments

This research was supported by multiple grants, primarily by the [**Land
& Carbon Lab Global Pasture Watch**](https://landcarbonlab.org/) grant from the Bezos Earth
Fund and [Time2Graze grant](https://www.globalmethanehub.org/2025/09/10/the-global-methane-hub-launches-international-project-to-develop-satellite-guided-grazing-to-cut-livestock-emissions/) from Global Methane Hub.

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