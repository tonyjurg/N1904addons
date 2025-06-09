# Using the Morpheus features 

This page first presents an overview of how Morpheus features are logically organized into classes. It then shows how that structure supports a practical workflow, guiding you from a high-level meta view, through a concise summary, and finally to a detailed inspection of the Morpheus data.

## Morpheus feature classes

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

## Guide: working with Morpheus feature-set in Text-Fabric

This section (which is also available as a [downloadable Jupyter Notebook](notebooks/example_usage.ipynb)) will provide you a compact overview of how the concept of [Morpheus TF feature classes](morpheus_tf_feature_classes.md) is helpfull. The example below shows you how to begin at the meta level, drill down to the summary level, and—when needed—inspect the full, detailed analytic blocks. Everything happens within a single environment that brings together the core N1904-TF dataset, the N1904addons module, and optionaly a set of detailed functions when desired.

### Step 1: Load N1904-TF with the Morpheus “standard” features

```python
from tf.app import use
A = use( "CenterBLC/N1904", version="1.0.0", mod="tonyjurg/N1904addons/tf/", hoist=globals())
```

The `mod` argument above pulls the feature files straight from the GitHub repository behind N1904addons so no manual download is needed.


### Step 2: Start at the meta level (`mm*`)

Suppose we want to understand how many wordforms be derived from a different lemmas. The first step could be to just create a frequency table:

```Python
F.mm_num_lemmas.freqList()
>>> ((1, 78324),     # (number of lemmas, frequency)
>>> (2, 29104),
>>> ...
>>> (12, 6),
>>> (11, 1))
```

Now lets assume we would like to examine the wordforms that migth be derived from - say - exactly 9 lemmas.
With a very simple TF Query template we can obtain a list of all wordnodes that provide us access to all these wordforms:

```python
multiLemmaList=A.search("word mm_num_lemmas=9")
>>> 0.09s 42 results
```
The TF Query returns a list with 1-tuples which we now can examine further. So the next step is to get a frequency table of the surface forms:

```python
from collections import Counter
cnt = Counter(
    F.mm_raw_uc.v(wordNode)              # surface form Morpheus analysed
    for (wordNode,) in multiLemmaList    # wordNodeList is a list of 1-tuples: [(wordNode,),]
)
```

Printing `cnt` shows 4 different wordforms: Διὰ (36 times), περάτων (twice), and the following words each once:  ἀπόλωνται, Δία, διαπονηθεὶς, and διακονιῶν. Now assume we would like to dig deeper into the last wordform, διακονιῶν. 

This means that we are looking at an unique occurence of a wordform. There are various methods to identify the value of its wordNode, which is the key to unlock all the data we would like to see. This one is a quick and easy one:

```python
wordNodeList=A.search("word mm_raw_uc=διακονιῶν")
>>> 0.09s 1 result
```

As expected this returns a list with just one tuple. Now we can print some more details:

```python
for (wordNode,) in wordNodeList:        # wordNodeList is a list of 1-tuples: [(wordNode,),]
    print(f'surface form Morpheus used: {F.mm_raw_uc.v(wordNode)}') 
    print(f'lemma groups found: {F.mm_num_lemmas.v(wordNode)}')
    print(f'Total number of analytic blocks: {F.mm_num_blocks.v(wordNode)}')
>>> surface form Morpheus used: διακονιῶν
>>> lemma groups found: 9
>>> Total number of analytic blocks: 15
```

### Step 3: Explore at the summary level (`ms*`)

To examine these 9 lemmas and their respective grammatical details (like morph code) in detail we need to turn to the summary features. This can easily be done using simple Python code. The real trick in there is the use of a variable name that is constructed dynamicaly in combination with using Text-Fabric's `Fs('fff')` method:

First we exploit the power of the summary features by printing for each lemma the associated morphological tags which provide a very consise summary of all the grammatical detailed created by Morpheus.

```python
for (wordNode,) in wordNodeList:        # wordNodeList is a list of 1-tuples: [(wordNode,),]
    # How many lemma-groups does this word actually have
    n_lemmas = int(F.mm_num_lemmas.v(wordNode) or 0)

    # loop over the existing groups 1 … n_lemmas
    for index in range(1, n_lemmas + 1):
        lemma   = Fs(f"ms{index}_lem_base_uc").v(wordNode)  # e.g. "ms1_lem_base_uc"
        morph   = Fs(f"ms{index}_morph").v(wordNode)      
        sim     = Fs(f"ms{index}_morph_sim").v(wordNode)   
        print(f"#{index}: lemma={lemma:12}  morph={morph} sim={sim}")
>>> #1: lemma=διακονία      morph=N-GPF sim=100
>>> #2: lemma=διακόνιον     morph=N-GPN sim=92
>>> #3: lemma=διά-ἀκονάω    morph=V-PAP-NSM sim=49
>>> #4: lemma=διά-κονέω     morph=V-PAP-NSM sim=49
>>> ...
>>> #8: lemma=διά-κονιάζω   morph=V-FAP-VSM/V-FAP-NSN/V-FAP-VSN/V-FAP-ASN/V-FAP-NSM sim=49/49/49/49/49
>>> #9: lemma=διακονέω      morph=V-PAP-NSM sim=49
```

### Step 4 : Deep dive at the detail level (`md*`) 

When we want to dig one level deeper, we should dump the data in feature [`ms{num}_block_nums`](ms{num}_block_nums.md), as this allows us to map the summary features (which are numbered) with their related detailed features (which are also numbered but with a different key). 
```python
for (wordNode,) in wordNodeList:        # wordNodeList is a list of 1-tuples: [(wordNode,),]
    # How many lemma-groups does this word actually have
    n_lemmas = int(F.mm_num_lemmas.v(wordNode) or 0)

    # loop over the existing groups 1 … n_lemmas
    for index in range(1, n_lemmas + 1):
        feat = f"ms{index}_block_nums"          # e.g. "ms1_block_nums"
        block_nums = Fs(feat).v(wordNode)        # Text-Fabric feature lookup
        if block_nums:                          # skip empty slots
            print(f"lemma #{index} uses blocknumbers {block_nums}")
>>> lemma #1 uses blocknumbers 1
>>> lemma #2 uses blocknumbers 2
>>> ...
>>> lemma #7 uses blocknumbers 7/8/9/10/11
>>> lemma #8 uses blocknumbers 12/13/14
>>> lemma #9 uses blocknumbers 15

Now we can pull from the Morpheus analytic blocks any detailed grammatical property we would like to evaluate.
But in order to be able to use these detailed features, we need to load them first. For this we reload again with inclusion on the detailed dataset:

```python
# reload with detailed_set ------------------------------------
A = use( "CenterBLC/N1904", version="1.0.0", mod=["tonyjurg/N1904addons/tf/", "tonyjurg/N1904addons/detailed_set"], hoist=globals(), silence="terse",)
```

Now we can create tables using specific part of the Morpheus output. For example aspects like preposition, stem, lemma and ending for each analysis block:

```python
wordNodeList=A.search("word mm_raw_uc=διακονιῶν")   # we have to re-do this since we reloaded!

for (wordNode,) in wordNodeList:        # wordNodeList is a list of 1-tuples: [(wordNode,),]
    # How many lemma-groups does this word actually have
    n_lemmas = int(F.mm_num_lemmas.v(wordNode) or 0)

    # loop over the existing groups 1 … n_lemmas
    for index in range(1, n_lemmas + 1):
        feat = f"ms{index}_block_nums"          # e.g. "ms1_block_nums"
        block_nums = Fs(feat).v(wordNode)        # Text-Fabric feature lookup
        block_list = split(block_nums,'/')
		print(f'index={index}  blocks={block_nums}')
		for block in block_list:
		    lem_base_uc = Fs(f"md{block}_lem_base_uc").v(wordNode)
            prvb_uc = Fs(f"md{block}_prvb_uc").v(wordNode)
			stem_uc = Fs(f"md{block}_stem_uc").v(wordNode)
			ending_uc = Fs(f"md{block}_ending_uc").v(wordNode)

```

This three-tier approach keeps the usual workflow fast and lightweight (meta + summary only) while it still giving you the option to dive deep whenever your research question demands it.

