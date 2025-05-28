# N1904addons - Feature: morph_ttr

Feature group | Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`statistic`](README.md#feature-group-statistic) | `Node` |`str` | `book` `chapter` `verse` `sentence` `group` `wg` `phrase` `subphrase` `clause` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature short description

Type to Token Ratio based on morph-tags for all word nodes under this node.

## Feature values

A float number *stored as a string* representing a ratio in the range 0 to 1 (inclusive) where the dot denotes a decimal point, not a thousands separator.

## Detailed feature description

This feature provides the Morph-to-Token Ratio (MTR), which is a measure for morph diversity. It is defined as:

$$
  \text{MTR} 
    = \frac{|\{\text{unique morphs in the text}\}|}{N}
$$

## See also

Related features:

  - [text_ttr](text_ttr.md): Type to Token Ratio based on wordforms for all word nodes under this node.
  - [lemma_ttr](lemma_ttr.md): Type to Token Ratio based on lemma for all word nodes under this node.

## Data source

The production notebook can be found on [this repository](https://tonyjurg.github.io/Create-TF-stat-features/).