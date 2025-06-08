# N1904addons - Feature: mm_raw_uc

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node` | `str` | `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

Unicode representation of the raw: field of Morpheus for this word node

This is a Morpheus meta data feature ([more info](morpheus_tf_feature_classes.md)).

## Feature values

The raw form of the word in `unicode, as it was inputted. 

Note that this may include ellipsis (indicated with '). [Crane provides as example ἐπέμπετ᾽](https://github.com/gregorycrane/Homerica/blob/1ad202eec627414e7153f5512d6cb43abc22e308/Tb%2BMorpheus#L77), which could stand for ἐπέμπετε ("you [pl] were sending") or ἐπέμπετο ("s/he was being sent").

The following image shows an example of a Morpheus analyses block and the position of the raw: field.

<IMG SRC="images/morpheus_block_example.png">

## Data source
