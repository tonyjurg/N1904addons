[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)

# N1904addons

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). All  features are provided **"as is"** under the [Creative Commons Attribution 4.0 International (CC BY 4.0) license](https://github.com/tonyjurg/N1904addons/blob/main/LICENSE.md). Please take special notice to the flags provided under the header ‘Feature status’, as some features may not be stable yet.

## Features

The dataset N1904addons contains the following feature groups which are included in the 'standard' set: 

Feature group | Description
---|---
[Morpheus (Analyses, meta and summary)](features/README.md#feature-group-morpheus-analyses-meta-and-summary) | Morpheus morphological analyser summary, meta and analytic features.
[Statistic](features/README.md#feature-group-statistic) | Statistic features like entropy and TTR
[Crossreference](features/README.md#feature-group-cross-reference) | Cross reference features like OSIS ID
[Miscellaneous](features/README.md#feature-group-miscellaneous) | Miscellaneous features like Penn Tree 

An additional set of features from the 'detailed' set can optionaly be loaded: 

Feature group | Description
---|---
[Morpheus (Details)](features/README.md#feature-group-morpheus-details) | Extensive set of features (more than 600) providing access to information elements in each Morpheus analytic block. 

## Adding the features

See [this page](using_the_dataset.md).

## Tools used

The standard set of tools ([Python documentation](https://www.python.org/doc/), tech sites like [stackoverflow](https://stackoverflow.com/), and Python syntax checkers like [Pythonium](https://pythonium.net/linter)) were used to create this package. Furthermore, for the creation of a subset of features, also the [Anaconda Assistant](https://www.anaconda.com/capability/anaconda-assistant) (using [OpenAI](https://openai.com/) as backend) and/or [GitHub Copilot](https://github.com/features/copilot) in Visual Studio were used to debug and/or optimize parts of the code. See the individual notebooks for details.

## License

This software and data are provided 'as-is' under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/) license. It comes without any express or implied warranty. In no event shall the authors be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.

See also [LICENSE.md](https://github.com/tonyjurg/N1904addons/blob/main/LICENSE.md) on the GitHub repository.


## Citation

When citing this dataset, please use following BibTeX:

```
@software{Jurg_N1904addons_-_Additional_2025,
author = {Jurg, Tony},
doi = {TBD},
month = apr,
title = {{N1904addons - Additional features for N1904 Text Fabric dataset}},
url = {https://github.com/tonyjurg/N1904addons},
version = {0.1},
year = {2025}
}
```
