[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)  [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17091708.svg)](https://doi.org/10.5281/zenodo.17091708) [![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

# N1904addons

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). Text-Fabric is a powerful platform for analyzing biblical texts with linguistic and structural detail.

Go to the [documentation section](docs/README.md) or the [GitHub pages site](https://tonyjurg.github.io/N1904addons/) to examine the features provided by this dataset.

## Adding the features

First you need to load the TF software and make `use` available:

```python
# Loading the Text-Fabric code
from tf.fabric import Fabric
from tf.app import use
```

When loading N1904TF, by default, any additional features are not loaded. To include them, use the `mod` option during invocation, as shown below:

```python
# Load the N1904-TF app and data with the additional features
A = use ("CenterBLC/N1904", version="1.0.0", mod="tonyjurg/N1904addons/tf/", hoist=globals())
```

To use this functionality, the Text-Fabric package must support downloading files from GitHub. If Text-Fabric was installed without GitHub functionality, you might encounter errors like the following when trying to load the additional features:

```
The requested data is not available offline
	~/text-fabric-data/github/tonyjurg/N1904addons/tf/1.0.0 not found
Backend provider github not supported.
Cannot reach online data on github
Try installing text-fabric one of the following:
pip install text-fabric[github]
pip install text-fabric[all]
```

To resolve this issue, ensure that GitHub support is added to Text-Fabric by running:

```
!pip install text-fabric[github]
```

Since GitHub implemented a API rate limit of 60 requests per hour, it is recommended to use a personal access token to increase this rate limit. Refer to the following resources for guidance:
- [Jupyter Notebook: Increase GitHub API Rate Limit](https://nbviewer.org/github/CenterBLC/N1904/blob/main/docs/tutorial/Increase_GitHub_rate_limit.ipynb)
- [Text-Fabric Documentation: Using GitHub Tokens](https://annotation.github.io/text-fabric/tf/advanced/repo.html#token-in-environment-variables)

## Tools used

The standard set of tools ([Python documentation](https://www.python.org/doc/), tech sites like [stackoverflow](https://stackoverflow.com/), and Python syntax checkers like [Pythonium](https://pythonium.net/linter)) were used to create this package. Furthermore, for the creation of a subset of features, also the [Anaconda Assistant](https://www.anaconda.com/capability/anaconda-assistant) (using [OpenAI](https://openai.com/) as backend) and/or [GitHub Copilot](https://github.com/features/copilot) in Visual Studio were used to debug and/or optimize parts of the code. See the individual notebooks for details.

## BibTeX

```
@software{Jurg_N1904addons_-_Additional_2025,
author = {Jurg, Tony},
doi = {10.5281/zenodo.17091708},
month = aug,
title = {N1904addons - Additional features for N1904 Text Fabric dataset},
url = {https://github.com/tonyjurg/N1904addons},
version = {v1.0.0},
year = {2025}
}
```
