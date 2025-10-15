# Loading the N1904addons dataset

Below is a step-by-step guide to getting the N1904addons feature set up and running.

## Install Text-Fabric

To load and use this dataset, first of all you need a working Python environment plus the Text-Fabric (TF) library.  If this still needs to be done, you can either start by consulting the [official Text-Fabric documentation](https://annotation.github.io/text-fabric/tf/about/install.html#tf.about.install) or by using the [tutorial on the N1904-TF website](https://centerblc.github.io/N1904/tutorial/index.html#start).

## Import Text-Fabric in Python

Once you have Python and Text-Fabric installed, you can import the relevant Text-Fabric libraries into your Python environment:  

```python
# Loading the Text-Fabric code
from tf.app import use
```

## Load the core dataset with standard N1904addons

Next you can load a Text-Fabric dataset (the dataset and its application code). The N1904addons should be loaded together with the base N1904-TF dataset. 
To include the addons (everything *except* the detailed Morpheus `md*` features)), we use the [`use()`](https://annotation.github.io/text-fabric/tf/about/usefunc.html) function with the  `mod` option during invocation, as shown below. In this example we will only load the standard N1904addons (all features excluding the detailed Morpheus features `md*`):

```python
# Load the N1904-TF app and data with the additional features
A = use ("CenterBLC/N1904", version="1.0.0", mod="tonyjurg/N1904addons/tf/", hoist=globals())
```

## GitHub access issues?

When running this code, Text-Fabric package tries to download all required files from GitHub. If Text-Fabric was installed without GitHub functionality, you might encounter errors like the following when trying to load the additional features:

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

GitHub’s unauthenticated API is capped at 60 requests / hour.  Therefore it is recommended to aquire a personal access token in order to raise that limit. See the following resources for guidance:

- [Jupyter Notebook: Increase GitHub API Rate Limit](https://nbviewer.org/github/CenterBLC/N1904/blob/main/docs/tutorial/Increase_GitHub_rate_limit.ipynb)
- [Text-Fabric Documentation: Using GitHub Tokens](https://annotation.github.io/text-fabric/tf/advanced/repo.html#token-in-environment-variables)


## (Optional) Load the detailed Morpheus features

Hundreds of extra `md*` features expose virtualy every information element pressent in the Morpheus analytic block. They are not loaded by default, but you can load them alongside the standard addon in the following manner:

```
A = use ("CenterBLC/N1904", version="1.0.0", silence="terse", mod=["tonyjurg/N1904addons/tf/", "tonyjurg/N1904addons/detailed_set"], hoist=globals()) 
```

Please note that here we do pass multiple modules as a list to the `mod` argument. This mechanism could also be used by including even more modules, for example the [BOLcomplement](CenterBLC/N1904/BOLcomplement/tf/) which contains a number of features that are  particular relevant in relation to Morpheus, like [`bol_verb_type`](https://centerblc.github.io/N1904/additions/bol_verb_type.html) or [`bol_noun_declension`](https://centerblc.github.io/N1904/additions/bol_noun_declension.html). 
