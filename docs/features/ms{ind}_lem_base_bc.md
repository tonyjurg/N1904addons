# N1904addons - Feature: ms{ind}_lem_base_bc

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node` | `int` | `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

Summary feature for grouped analysis #{ind} providing the base lemma (clean; without suffixes) encoded in betacode.

This is a Morpheus [summary data feature](../using_the_morpheus_features.md#morpheus-feature-classes).

## Feature values

The lemma string in Unicode.

## Coding

The following Python code demonstrates how to programaticaly obtain details like lemma and morphological tags per grouped analysis blocks.

**NEED TO CHECK**

```Python
wordNodes = F.otype.s("word")
for wordNode in wordNodes:
    for blockNumber in range(1, 9):
        # dynamically get F.ms{blockNumber}_lemma & morph
        lemma = Fs(f"ms{blockNumber}_lem_").v(wordNode)
        if not lemma: continue
        morph_string = Fs(f"ms{blockNumber}_morph").v(wordNode)
        morph_sim_string = Fs(f"ms{blockNumber}_morph_sim").v(wordNode)
        # decompose on the slash
        parts = morph_string.split("/")
        # print what was found
        print(f"node={wordNode}, number={blockNumber} → lemma={lemma}, tags: {parts}")

node=1, number=1 → lemma=Βίβλος, tags: ['N-NSM']
node=1, number=2 → lemma=βίβλος, tags: ['N-NSF']
node=2, number=1 → lemma=γένεσις, tags: ['N-GSF']
node=3, number=1 → lemma=Ἰησοῦς, tags: ['N-GSM', 'N-VSM', 'N-PRI']
...
```

The snippet below dynamicaly builds a list of names of 'numbered' Morpheus 
feature names. This allows to easily pass this list as an option to A.show() 

```python
# Dynamically generate feature names for all morphology sets
morphFeatureList = (
    [f'ms{ind}_lemma'      for ind in range(1, 9)]
  + [f'ms{ind}_morph'      for ind in range(1, 9)]
  + [f'ms{ind}_morph_sim'  for ind in range(1, 9)]
)
# Display the query results with the Morpheus features
A.show(QueryResult, extraFeatures=morphFeatureList)
```

The image below shows a syntax tree with the display of these features enabled.

<IMG SRC="images/show_morpheus_features.png" WIDHT=600>

## Data source

GitHub repository [Create_morpheus_TF_dataset](https://tonyjurg.github.io/Create_morpheus_TF_dataset/).
