# N1904addons feature: lemma_entr

Feature type | Data type | Available for node types
---  | --- | --- 
`Node`|`String`|`word`

## Feature description

Entropy of a morph(-tag of a word) as predictor of its parent phrase function

## Note

In our syntactic annotated Text-Fabric dataset, we define entropy as a measure of the uncertainty or variability of how an element (such as a surface level word, its morph, or its lemma) predicts or aligns with the syntactic functions (like Subject, Object, etc.) of the phrase it belongs to.

Entropy reflects the extent to which such an element's syntactic behavior is predictable. High entropy values indicate that a form is ambiguous, as it appears in multiple syntactic functions with similar probabilities. In contrast, low entropy values signify that a form is strongly associated with a single syntactic function, making it a reliable indicator of that role within the parent phrase.

## See also

Related features
 - [lemma_entr](lemma_entr.md): Entropy of a lemma (of a word) as predictor of its parent phrase function
 - [text_entr](text_entr.md): Entropy of the surface level wordform (text) as predictor of its parent phrase function

Descriptive document:
 - [About entropy an N1904-TF](../entropy_feature.md).

## Source

[Github repository](https://github.com/tonyjurg/Create-TF-entropy-features).

