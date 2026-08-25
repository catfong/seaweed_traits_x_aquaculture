# Aquaculture × traits — publication materials

Open `aqua_traits.Rproj` in RStudio so this folder is the working directory. All `read.csv` / `write.table` paths are relative to this folder.

## Knit / run order

1. `species selection.Rmd` — FAO production → species list / volume tables  
2. `table data.Rmd` — value, volume, countries farming  
3. `aquaculture_x_traits.Rmd` — trait space, NMDS, SIMPER, multinomial trait axes  

Scripts 1–2 are independent of 3. Script 3 only needs `aqua_traits.csv`, `uses.csv`, and `all_spp.csv`.

## Inputs included

| File | Used by |
|------|---------|
| `aqua_traits.csv`, `uses.csv`, `all_spp.csv` | `aquaculture_x_traits.Rmd` |
| `fao_spp_code.csv` | `species selection.Rmd` |
| `species_codes.csv`, `fao_value.csv`, `fao_volume.csv`, `Aquaculture_Value.csv`, `un_country_codes.csv` | `table data.Rmd` |

Large FAO data may need to be downloaded directly from FAO website.

## Packages

Core: `tidyverse`, `vegan`, `cluster`, `ggplot2`, `ggpubr`, `ggrepel`, `nnet`, `DescTools`, `RVAideMemoire`

Also loaded in `aquaculture_x_traits.Rmd` (some may be unused leftovers): `Rtsne`, `factoextra`, `FD`, `mlogit`, `NbClust`, `viridis`, `ecodist`, `effects`, `visreg`

Install missing packages once in R, e.g. `install.packages(c("vegan", "DescTools", "ggrepel", ...))`. Do not leave `install.packages()` inside analysis chunks.

## Notes

- NMDS (`metaMDS`) is stochastic; add `set.seed(...)` before those calls if you need matching axes across machines.
- Intermediate outputs (`species.csv`, `volume.csv`, `value_and_volume.csv`, `groups.csv`, `xaxis.nmds*.csv`, etc.) are written when you run the scripts; they are not shipped as inputs.
