# N1904addons - Feature: ma{ind}_pf_altern

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node`| `str` | `phrase` | [🆗](featurestatus.md#Reasonable "Reasonable")

## Feature description

for {ind}=0: Phrase function alternatives based on morphological tagging according to base N1904-TF.

for {ind} in range [1,12], inclusive: Phrase function alternatives based on Morpheus tag permutation {numb}.



This is a Morpheus analysis data feature.

## Feature values

A string containing a specific sequence of morphs with a probality indication for the resulting phrase function. 

For example for the feature `ma1_pf_altern`, the value

```
  T-ASM+N-ASM+P-GSM=o:88/s:12
```
This can be understood as:

 1. The '1' in `ma1` tells us this is the first alternative combination of morph-tags.
 2. The tag sequence `T-ASM+N-ASM+P-GSM` means the phrase consists of an article followed by a noun and a personal pronoun with the speficied grammatical properties.
 3. The part after the  '=', in this case `o:88/s:12` gives the distribution of phrase functions:
    * `o:88` means 88 % of occurrences of this exact morph-sequence are labeled as an object phrase.
    * `s:12` means 12 % are labeled as a subject phrase.


## Programmatic access

See [this document](../using_the_morpheus_features.md) for more details.

## Notes

Because Morpheus does not generate analysis blocks for every word node, some words never receive a morphological tag. If a phrase contains one of these untagged words, the data needed to populate this feature are missing, so the feature is left blank.

The probability values shown by this feature were trained on the entire Greek New Testament (GNT). They therefore represent how often each sequence of morphological tags occurs within the N10904-TF corpus. The underlying grammar is closed: it filters out impossible tag combinations (wanted behaviour), but it also fails to recognise legitimate sequences that simply do not appear in the GNT.

## Data source

GitHub repository [Create_morpheus_TF_dataset](https://tonyjurg.github.io/Create_morpheus_TF_dataset/).
