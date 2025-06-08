# Morpheus TF feature classes

The total number of distinct Text-Fabric features related to the Morpheus morphological analysis is currently around 900. Without a logical taxonomy this would be unable to handle. Therefore, the Morpheus related Text-Fabric features are devided into three main groups:

Class | Naming patern | Function and maps to datatype
--- | --- | --- 
[Meta](README.md#meta-data) | mm_{feature} | These features contain  meta data like details on number of lemmas returned for the analysis of a single word. This group also contains features that allow easy programmatic access to the summary features.
[Summary](README.md#summary-data) | ms{num}_{feature} | These features contain a summary per lemma of all related analytic blocks returned by Morpheus. This group also contains features that allow easy programmatic access to the detailed features.
[Detail](README.md#detail-data) | md{num}_{feature} | These features provide access to (almost) all details in the Morpheus analytical blocks

The following image shows the general patern:

<img src="images/morpheus_feature_classes.png">

From the table and the image it is clear that the majority of feature will belong the to 'detailed class. In many cases the level of detail therein is not required, since the summary of them is readily made available by means of the summary features. Therefore, the features in class 'detail' are not loaded by default when loading the N1904addons. If access is required, they can simply be loaded together with the N1904addons, using the following Python code: 

```Python
A = use ("CenterBLC/N1904", version="1.0.0", silence="terse", mod=["tonyjurg/N1904addons/tf/", "tonyjurg/N1904addons/detailed_set"], hoist=globals()) 
```

In this case the option silense="terse" may be realy helpfull in order to supress the huge output during loading and compiling of the large number of features. Take note that althoug loading may take some time, once loaded Text-Fabric is not significant slowed down by the huge number of features.

