# N1904addons - Feature: lemma_ttr

Feature group | Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`statistic`](README.md#feature-group-statistic) | `Node` |`str` | `book` `chapter` `verse` `sentence` `group` `wg` `phrase` `subphrase` `clause` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature short description

Type to Token Ratio based on lemma for all word nodes under this node.

## Feature values

A float number *stored as a string* representing a ratio in the range 0 to 1 (inclusive) where the dot denotes a decimal point, not a thousands separator.

## Detailed feature description

This feature provides the Lemma-to-Token Ratio (LTR), which is a measure for lemma diversity. It is defined as:

$$
  \text{LTR} 
    = \frac{|\{\text{unique lemmas in the text}\}|}{N}
$$

## Visualizing

The following plot compares the Text-to-Token Ratio measured over wordform (TTR), lemma (LTR) and morph (MTR) per book of the New Testament. The immage clearly shows that shorter books generaly are resulting in higher ratio (even while TTR is already a ratio).

<img src="images/ttr_ltr_mtr_per_book.png">

## See also

Related features:

  - [morph_ttr](morph_ttr.md): Type to Token Ratio based on morph-tag for all word nodes under this node.
  - [text_ttr](text_ttr.md): Type to Token Ratio based on wordform for all word nodes under this node.

## Data source

The production notebook can be found on [this repository](https://tonyjurg.github.io/Create-TF-stat-features/).