# N1904addons - Feature: ma{num}_pf_flip

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node`| `int` | `phrase` | [🆗](featurestatus.md#Reasonable "Reasonable")

## Feature description

for {numb}=0: Max function flip potential for base phrase according N1904-TF morphological tags.

for {numb} in range [1,12], inclusive: Max function flip potential for phrase based on Morpheus tag permutation {numb}.

{numb} can be in the range [0-12] inclusive.

This is a Morpheus analysis data feature.

## Feature values

An integer.

## Programmatic access

See [this document](../using_the_morpheus_features.md) for more details.

## Notes

Because Morpheus does not generate analysis blocks for every word node, some words never receive a morphological tag. If a phrase contains one of these untagged words, the data needed to populate this feature are missing, so the feature is left blank.

The probability values shown by this feature were trained on the entire Greek New Testament (GNT). They therefore represent how often each sequence of morphological tags occurs within the N10904-TF corpus. The underlying grammar is closed: it filters out impossible tag combinations (wanted behaviour), but it also fails to recognise legitimate sequences that simply do not appear in the GNT.

## Data source

[See this repository](https://tonyjurg.github.io/Create_morpheus_TF_dataset/).
