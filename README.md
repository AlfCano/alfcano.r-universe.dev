# AlfCano's R-Universe Registry

![R-Universe](https://alfcano.r-universe.dev/badges/:total)
![Build Status](https://github.com/AlfCano/alfcano.r-universe.dev/actions/workflows/sync.yml/badge.svg)
[![Universe Status](https://alfcano.r-universe.dev/badges/:name)](https://alfcano.r-universe.dev/)

This repository serves as the configuration registry for **[alfcano.r-universe.dev](https://alfcano.r-universe.dev)**. 

It hosts a comprehensive, constantly updating collection of **RKWard GUI plugins** and R packages for statistics, data wrangling, and visualization. Downloading from this R-Universe ensures faster installations (via pre-compiled binaries) and completely avoids GitHub API rate limit errors (HTTP 403).

---

## 📦 Available Packages

This universe currently serves a massive suite of **62+ packages**, transforming RKWard into a state-of-the-art graphical environment. Highlights include:

*   **Statistics & Modeling:** `rk.bayesian`, `rk.psych`, `rk.lavaan`, `rk.weibull`, `rk.efa`
*   **Data Wrangling:** `rk.janitor`, `rk.data.wrangling`, `rk.subset.tidy`, `rk.haven`
*   **Survey Analysis:** `rk.survey.design`, `rk.survey.wrangling`, `rk.questionr`
*   **Visualization & Maps:** `rk.storytelling.data`, `rk.rnaturalearth`, `rk.gganimate`
*   **Publishing:** `rk.gtsummary`, `rk.flextable`, `rk.quarto`

[**👉 View the full interactive dashboard and package list**](https://alfcano.r-universe.dev)

---

## 🚀 Installation Guide

You can install packages directly from this universe without needing a GitHub account or token. 

### Method 1: The `rk.universe` Meta-Package (Recommended)
Inspired by the `tidyverse` philosophy, `rk.universe` is a master package designed to install, load, and synchronize the entire RKWard GUI ecosystem in one go. Instead of installing dozens of plugins individually, this handles all dependencies and seamlessly integrates every graphical menu into your interface.

#### 🌟 Key Features
*   **One-Line Installation:** Pulls all 62+ specialized GUI plugins directly from the servers.
*   **Automatic GUI Registration:** Features a smart `.onAttach` hook. When loaded inside RKWard, it automatically searches for and registers every `.pluginmap` file in the ecosystem. No manual XML configuration required.
*   **Clean Console Output:** Uses the `cli` package to print a beautiful, non-obtrusive summary of loaded tools and activated menus.

**Run this in your RKWard console:**
```R
# 1. Enable the AlfCano R-Universe repository
options(repos = c(
  alfcano = "https://alfcano.r-universe.dev",
  CRAN = "https://cloud.r-project.org"
))

# 2. Install the master meta-package
install.packages("rk.universe")

# 3. Load the suite to instantly activate all menus!
library(rk.universe)
```

### Method 2: Install Specific Plugins (A la Carte)
If you prefer a minimalist setup and only want specific tools, simply add the repository to your options and install what you need:

```R
# Enable the universe
options(repos = c(
  alfcano = "https://alfcano.r-universe.dev",
  CRAN = "https://cloud.r-project.org"
))

# Install specific packages
install.packages("rk.janitor")
install.packages("rk.rnaturalearth")
install.packages("rk.gtsummary")
```

---

## 🛠️ How to add new packages to this Registry

This registry is automated and controlled by the `packages.json` file in this repository. To add a new package to the universe:

1.  Edit the `packages.json` file.
2.  Add the Git URL of your new package repository.
3.  Commit and push the changes. R-Universe will automatically detect it, build the binaries, and publish it within an hour.

---
*Maintained by [AlfCano](https://github.com/AlfCano)*
