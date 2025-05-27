# Using the dataset

## Text-Fabric

To use this dataset, you first need to have Text-Fabric installed in your Python environment. You can either start with the [official Text-Fabric documentation](https://annotation.github.io/text-fabric/tf/about/install.html#tf.about.install) or by using the [tutorial on the N1904-TF website](https://centerblc.github.io/N1904/tutorial/index.html#start).

Next you need to import the N1904-TF dataset, simply because the features in this 'addon' do depend on them.

## Loading the feature set 

Once you have set up your environment, you can import the Text-Fabric libraries:  

```python
# Loading the Text-Fabric code
from tf.fabric import Fabric
from tf.app import use
```

When loading the N1904TF dataset, by default, the additional features are not loaded. To include them, use the `mod` option during invocation, as shown below:

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


## Loading the detailed database

The 600+ features providing access to numerous part of the Morpheus analytic blocks are **not** loaded by default (for obvious reasons). To get access to these, you need to invoke the dataset like:

```
A = use ("CenterBLC/N1904", version="1.0.0", silence="terse", mod=["tonyjurg/N1904addons/tf/", "tonyjurg/N1904addons/detailed_set"], hoist=globals()) 
```

In this case the option silense="terse" may be realy helpfull in order to supress the huge output during loading and compiling of the large number of features. 