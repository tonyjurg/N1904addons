# N1904addons - Feature: ma{num}_pf_flip

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node`| `int` | `phrase` | [?](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

for {numb}=0:

    Max function flip potential for base phrase according N1904-TF morphological tags.

for {numb} in range [1,12], inclusive:

     Max function flip potential for phrase based on Morpheus tag permutation {numb}.

{numb} can be in the range [0-12] inclusive.

This is a Morpheus analysis data feature.

## Feature values

An integer.

## Programmatic access

See [this document](../using_the_morpheus_features.md) for more details.


## Data source