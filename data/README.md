# Data

## Source

This project uses the **Enquête Conditions de Travail 2016** (Working Conditions Survey), conducted by DARES (French Ministry of Labour) and DREES.

- **Official name:** Enquête CT-RPS 2016 (Conditions de Travail et Risques Psychosociaux)
- **Producer:** DARES / DREES
- **Year:** 2016
- **Access:** Available upon request via [ADISP-PROGEDO](https://data.progedo.dev/studies/doi/10.13144/lil-1232?tab=details) or the French data catalogue [Réseau Quetelet](https://www.reseau-quetelet.cnrs.fr/)

## Why the data is not included

The raw data file (`ao_panel_2016.csv`) is **not included** in this repository because it is subject to a data access agreement and cannot be redistributed publicly.

To reproduce the analysis:
1. Request access to the CT-RPS 2016 survey via ADISP-PROGEDO
2. Place the file `ao_panel_2016.csv` in the root directory of this repository
3. Run `burnout_analysis.ipynb` from top to bottom

## Variable documentation

Full variable descriptions and codebook are available in the official survey documentation provided with the dataset upon access request.
