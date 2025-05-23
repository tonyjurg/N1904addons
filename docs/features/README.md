# Overview features

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). Text-Fabric is a powerful platform for analyzing biblical texts with linguistic and structural detail.

The following features are provided:

Feature group | Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---|---
`Morpheus`| [betacode](betacode.md)| `string`| `word` | The Greek unicode word in betacode | `*)ihsou=` `*xristou=`
`Morpheus`| [mm_raw_bc](mm_raw_bc.md)| `string`| `word` | Betacode representation of the raw: field of Morpheus for this word node | `*)ihsou=` `*xristou=`
`Morpheus`| [mm_raw_uc](mm_raw_uc.md)| `string`| `word` | Unicode representation of the raw: field of Morpheus for this word node | `Ἰησοῦς`
`Morpheus`| [mm_num_lemmas](mm_num_lemmas.md)| `int`| `word` | Number of different lemmas returned by the Morpheus analytic blocks for this word node | `1`  `3`
`Morpheus`| [mm_num_blocks](mm_num_blocks.md)| `int`| `word` | Total number of analytic Morpheus blocks return for this word node | `1` `9` `11`
`Morpheus`| [ms{num}_block_nums](ms{num}_block_nums.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing a list with the associated blocknumbers. | `1/2` `4/5/6`
`Morpheus`| [ms{num}_morph](ms{num}_morph.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing a list of morphs | `N-GSM/N-VSM/N-PRI` `V-IEI-2S`
`Morpheus`| [ms{num}_morph_sim](ms{num}_morph_sim.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing a list of morps similairties to the N1904-TF morph | `100/93/56` `56`
`Morpheus`| [ms{num}_lemma](ms{num}_lemma.md)| `string`| `word` | Summary feature for grouped analysis #{num} providing the lemma | `πρὸς` `Λόγος`
`Morpheus`| [ms{num}_num_blocks](ms{num}_num_blocks.md)| `int`| `word` | Summary feature for grouped analysis #{num} providing the number of analytic blocks it summarizes | `3`  `2` 
`statistic`| [lemma_entr](lemma_entr.md)| `string`| `word` | Entropy of the lemma as predictor of its parent phrase function | number ranging from 0 to 2.5503
`statistic`| [text_entr](text_entr.md)| `string`| `word` | Entropy of the surface level wordform as predictor of its parent phrase function | number ranging from 0 to 2.5850
`statistic`| [morph_entr](morph_entr.md)| `string`| `word` | Entropy of a morph-tag as predictor of its parent phrase function | number ranging from 0 to 2.7271
`crossref`| [osis_id](osis_id.md)| `string`| `word` | Book name accoring to the OSIS (Open Scriptural Information Standard) ID | `2Thess` `Phlm`  


