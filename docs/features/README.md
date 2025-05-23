# Overview features

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). Text-Fabric is a powerful platform for analyzing biblical texts with linguistic and structural detail.

The following features are provided:

Feature group | Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---|---
`Morpheus`| [betacode](features/betacode.md)| `string`| `word` | The Greek unicode word in betacode | `*)ihsou=` `*xristou=`
`Morpheus`| [mm_raw_bc](features/mm_raw_bc.md)| `string`| `word` | Betacode representation of the raw: field of Morpheus for this word node | `*)ihsou=` `*xristou=`
`Morpheus`| [mm_raw_uc](features/mm_raw_uc.md)| `string`| `word` | Unicode representation of the raw: field of Morpheus for this word node | `Ἰησοῦς`
`Morpheus`| [mm_num_lemmas](features/mm_num_lemmas.md)| `int`| `word` | Number of different lemmas returned by the Morpheus analytic blocks for this word node | `2`  `1/2/3`
`Morpheus`| [mm_num_blocks](features/mm_num_blocks.md)| `int`| `word` | Total number of analytic Morpheus blocks return for this word node | `1` `9` `11`
`Morpheus`| [ms{num}_block_nums](features/ms{num}_block_nums.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing a list with the associated blocknumbers. | `1/2` `4/5/6`
`Morpheus`| [ms{num}_morph](features/ms{num}_morph.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing a list of morphs | `N-GSM/N-VSM/N-PRI` `V-IEI-2S`
`Morpheus`| [ms{num}_morph_sim](features/ms{num}_morph_sim.md)| `int`| `word` | Summary feature for grouped analysis #{num} providing a list of morps similairties to the N1904-TF morph | `100/93/56` `56`
`Morpheus`| [ms{num}_num_blocks](features/ms{num}_num_blocks.md)| `int`| `word` | Summary feature for grouped analysis #{num} providing the number of analytic blocks it summarizes | `3`  `2` 
`statistic`| [lemma_entr](features/lemma_entr.md)| `string`| `word` | Entropy of the lemma as predictor of its parent phrase function | number ranging from 0 to 2.7196
`statistic`| [text_entr](features/text_entr.md)| `string`| `word` | Entropy of the surface level wordform as predictor of its parent phrase function | number ranging from 0 to 2.5651
`statistic`| [morph_entr](features/morph_entr.md)| `string`| `word` | Entropy of a morph-tag as predictor of its parent phrase function | number ranging from 0 to 2.7196


