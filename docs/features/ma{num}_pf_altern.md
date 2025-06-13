# N1904addons - Feature: ma{num}_pf_altern

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node`| `int` | `phrase` | [🆗](featurestatus.md#Reasonable "Reasonable")

## Feature description

for {numb}=0: Phrase function alternatives based on morphological tagging according to base N1904-TF.

for {numb} in range [1,12], inclusive: Phrase function alternatives based on Morpheus tag permutation {numb}.



This is a Morpheus analysis data feature.

## Feature values

An integer.

## Programmatic access

See [this document](../using_the_morpheus_features.md) for more details.

## Notes

Because Morpheus does not generate analysis blocks for every word node, some words never receive a morphological tag. If a phrase contains one of these untagged words, the data needed to populate this feature are missing, so the feature is left blank.

The probability values shown by this feature were trained on the entire Greek New Testament (GNT). They therefore represent how often each sequence of morphological tags occurs within the N10904-TF corpus. The underlying grammar is closed: it filters out impossible tag combinations (wanted behaviour), but it also fails to recognise legitimate sequences that simply do not appear in the GNT.

## Data source