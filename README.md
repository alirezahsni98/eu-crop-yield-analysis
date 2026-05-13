# Land-Use Efficiency and Crop Yield Trends in the European Union

A data-driven assessment of agricultural sustainability in the EU using FAOSTAT data (1995-2024).

![Yield Trend Example](figures/north_south_yield_gap.png)

## Motivation

Sustainable biomass production is essential for the EU Green Deal and the European Bioeconomy Strategy. This project investigates how crop yields and land use have evolved across six EU agricultural producers (Germany, France, Italy, Spain, Portugal, and the Netherlands) over three decades. The analysis aims to identify which countries have achieved productivity gains without expanding their agricultural land, and whether the historical yield gap between Northern and Southern producers has narrowed over time.

## Research Questions

1. How have crop yields evolved in the EU over the last 30 years?
2. Which EU countries achieve higher yields without expanding agricultural land?
3. Are Southern EU countries converging or diverging from Northern EU yield levels?

## Key Findings

- **Convergence in grapes and maize:** The Southern producers have closed the yield gap with the North. In maize, Spain has overtaken the Northern average since around 2015.
- **Persistent divergence in sugar beet and wheat:** The Northern yields remain considerably higher, and the gap is structural rather than narrowing.
  
**Efficiency gains differ across crops:**

- **Grapes:** Spain, Portugal, and Italy improved yields while simultaneously reducing harvested area.
- **Maize:** Spain and Portugal increased yields while reducing harvested area. Italy and France also reduced their harvested area, but their yield improvements were relatively modest.
- **Sugar beet:** All countries, except Portugal, achieved higher yields alongside reductions in harvested area. Portugal was excluded from this comparison due to missing values from 2017 onward.
- **Wheat:** Italy and Portugal increased yields while reducing harvested area. Spain also recorded a substantial yield increase; however, the reduction in harvested area was minimal.
  
## Methods

- Data cleaning and interpolation of missing values within each country-crop-element group.
- Weighted regional yield computed as the sum of production divided by the sum of area harvested. This approach ensures that larger producers contribute proportionally to the regional figure.
- Three-year averages and rolling means to separate structural trends from year-to-year noise.
- Visualisation with Seaborn (`relplot`, faceted scatter and line charts).

## Tools

Python, pandas, Seaborn, Matplotlib, NumPy, Jupyter.

## How to Reproduce

```bash
git clone https://github.com/yourusername/eu-crop-yield-analysis.git
cd eu-crop-yield-analysis
pip install -r requirements.txt
jupyter lab
```

Then run the notebooks in order (01 to 04).

## Project Structure

```
eu-crop-yield-analysis/
├── data/
│   ├── raw/
│   │   └── FAOSTAT_data_en_1-8-2026.csv
│   └── processed/
│       ├── eu_stat_cleaned.csv
│       └── eu_stat_joined.csv
├── notebooks/
│   ├── 01_data_loading_cleaning.ipynb
│   ├── 02_yield_trends.ipynb
│   ├── 03_yield_efficiency.ipynb
│   └── 04_north_south_gap.ipynb
├── figures/
│   ├── grapes_yield_evolution.png
│   ├── maize_corn_yield_evolution.png
│   ├── sugar_beet_yield_evolution.png
│   ├── wheat_yield_evolution.png
│   ├── yield_vs_area_change_by_crop.png
│   └── north_south_yield_gap.png
├── README.md
├── LICENSE
└── requirements.txt
```

## Data Source

FAO. 2026. *FAOSTAT Statistical Database*. Accessed 8 January 2026. https://www.fao.org/faostat/. Licence: CC BY-4.0.

## Discussion: implications for sustainable biomass production

The findings indicate that the EU's productivity gains are unevenly distributed across crops. Two crops (grapes and maize) show genuine convergence, which suggests that productivity-enhancing technology and practices have transferred southward effectively. Conversely, two crops (wheat and sugar beet) show persistent gaps that are likely climatic in origin and unlikely to close through technology alone. Therefore, a sustainable EU biomass strategy should differentiate by crop. It should invest in Southern productivity for crops where convergence is achievable, and rely on regional specialisation where it is not.


## References

The following peer-reviewed sources and institutional reports informed
the discussion and interpretation of findings in this project.

**On EU crop yield trends and climate fingerprints:**

Moore, F. C., & Lobell, D. B. (2015). The fingerprint of climate trends
on European crop yields. *Proceedings of the National Academy of Sciences*,
*112*(9), 2670-2675. https://doi.org/10.1073/pnas.1409606112

Toreti, A., Deryng, D., Tubiello, F. N., Müller, C., Kimball, B. A.,
Moser, G., Boote, K., Asseng, S., Pugh, T. A. M., Vanuytrecht, E.,
Pleijel, H., Webber, H., Durand, J. L., Dentener, F., Ceglar, A.,
Wang, X., Badeck, F., Lecerf, R., Wall, G. W., ... Zhu, C. (2020).
*Analysis of climate change impacts on EU agriculture by 2050* (PESETA IV,
Task 3). European Commission, Joint Research Centre.
https://doi.org/10.2760/121115

**On maize C4 physiology and temperature thresholds:**

Crafts-Brandner, S. J., & Salvucci, M. E. (2002). Sensitivity of
photosynthesis in a C4 plant, maize, to heat stress. *Plant Physiology*,
*129*(4), 1773-1780. https://doi.org/10.1104/pp.002170

Schlenker, W., & Roberts, M. J. (2009). Nonlinear temperature effects
indicate severe damages to US crop yields under climate change.
*Proceedings of the National Academy of Sciences*, *106*(37), 15594-15598.
https://doi.org/10.1073/pnas.0906865106

**On climate change impacts on European viticulture:**

Fraga, H., García de Cortázar Atauri, I., Malheiro, A. C., & Santos,
J. A. (2016). Modelling climate change impacts on viticultural yield,
phenology and stress conditions in Europe. *Global Change Biology*,
*22*(11), 3774-3788. https://doi.org/10.1111/gcb.13382

van Leeuwen, C., Sgubin, G., Bois, B., Ollat, N., Schultz, H. R.,
Zavaglia, V., & Quénol, H. (2024). Climate change impacts and
adaptations of wine production. *Nature Reviews Earth and Environment*,
*5*, 258-275. https://doi.org/10.1038/s43017-024-00521-5

**On EU grain production and technology-driven yield gains:**

Pinke, Z., & Lövei, G. L. (2022). Climate change and modernization drive
structural realignments in European grain production. *Scientific Reports*,
*12*, 8056. https://doi.org/10.1038/s41598-022-10670-6

## Tools and Acknowledgements

AI assistance (Claude, Anthropic) was utilised for code review, optimisation suggestions, and visualisation refinement. The research design, methodology, and interpretation are my own work.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact

Alireza Hossseini  
LinkedIn: https://www.linkedin.com/in/alirezahs
Email: seyedalireza.hosseini@uni-hohenheim.de


