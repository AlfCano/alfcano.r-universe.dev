# AlfCano's R-Universe Registry

![R-Universe](https://alfcano.r-universe.dev/badges/:total)
![Build Status](https://github.com/AlfCano/alfcano.r-universe.dev/actions/workflows/sync.yml/badge.svg)

This repository serves as the configuration registry for **[alfcano.r-universe.dev](https://alfcano.r-universe.dev)**. 

It hosts a comprehensive collection of **RKWard plugins** and R packages for statistics, data wrangling, and visualization. Using R-Universe ensures faster installation (pre-compiled binaries) and avoids GitHub API rate limit errors (HTTP 403).

## 📦 content

This universe contains over 40 packages, including:
*   **Statistics:** `rk.bayesian`, `rk.psych`, `rk.six.sigma`, `rk.weibull`
*   **Data Wrangling:** `rk.janitor`, `rk.data.wrangling`, `rk.fastdummies`
*   **Survey Analysis:** `rk.survey.design`, `rk.survey.wrangling`, `rk.ggsurvey`
*   **Visualization & Maps:** `rk.storytelling.data`, `rk.rnaturalearth`, `rk.map.localities`

[**View full dashboard and package list**](https://alfcano.r-universe.dev)

## 🚀 Installation

You can install packages directly from this universe without needing a GitHub token.

### Option A: Install Everything (Full Suite)
Run the following code in your R console (or RKWard) to install the complete collection of plugins:

```r
local({
  # 1. Lista de paquetes
  pkgs <- c(
    "rk.aiken_v", "rk.apyramid", "rk.bayesian", "rk.cartographr", "rk.class.lists",
    "rk.codebook", "rk.cSplit", "rk.ctables", "rk.data.wrangling", "rk.dates",
    "rk.doe", "rk.dplyr", "rk.flextable", "rk.forcats", "rk.ggsurvey",
    "rk.googlesheets4", "rk.gsub.sub", "rk.gtsummary", "rk.janitor", "rk.lavaan",
    "rk.lookup", "rk.lubridate", "rk.mult.resp", "rk.names.labels", "rk.pivot.reshape",
    "rk.psych", "rk.qcc", "rk.questionr", "rk.shiny.plugins", "rk.six.sigma",
    "rk.stringr", "rk.survey.design", "rk.survey.wrangling", "rk.survival",
    "rk.svyplot", "rk.tidyr", "rk.transpose.df", "rk.weibull", "rk.storytelling.data",
    "rk.storytelling.survey", "rk.fastdummies", "rk.ddi.import",
    "rk.rnaturalearth", "rk.map.localities", "rk.map.globalities"
  )

  # 2. Configurar R para usar tu Universo
  options(repos = c(
    alfcano = "https://alfcano.r-universe.dev",
    CRAN = "https://cloud.r-project.org"
  ))

  # 3. Instalar
  message(">>> Instalando desde tu R-Universe personal...")
  install.packages(pkgs)
})
```

### Option B: Install Specific Packages
If you only want to install specific plugins, add the repository to your options and install as usual:

```r
# Enable the universe
options(repos = c(
  alfcano = "https://alfcano.r-universe.dev",
  CRAN = "https://cloud.r-project.org"
))

# Install specific packages
install.packages("rk.janitor")
install.packages("rk.rnaturalearth")
```

## 🛠️ How to add new packages

This registry is controlled by the `packages.json` file in this repository. To add a new package to the universe:

1.  Edit `packages.json`.
2.  Add the Git URL of the new package.
3.  R-Universe will automatically build and publish it within an hour.
