# Overview features

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). Text-Fabric is a powerful platform for analyzing biblical texts with linguistic and structural detail.

The features of this package can be grouped as follows:

### Feature group: Morpheus (Analyses, meta and summary)

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[betacode](betacode.md)| `str`| `word` | The Greek unicode word in betacode | `*)ihsou=` `*xristou=`
[mm_raw_bc](mm_raw_bc.md)| `str`| `word` | Betacode representation of the raw: field of Morpheus for this word node | `*)ihsou=` `*xristou=`
[mm_raw_uc](mm_raw_uc.md)| `str`| `word` | Unicode representation of the raw: field of Morpheus for this word node | `Ἰησοῦς`
[mm_num_lemmas](mm_num_lemmas.md)| `int`| `word` | Number of different lemmas returned by the Morpheus analytic blocks for this word node | `1`  `3`
[mm_num_blocks](mm_num_blocks.md)| `int`| `word` | Total number of analytic Morpheus blocks return for this word node | `1` `9` `11`
[ms{num}_block_nums](ms{num}_block_nums.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing a list with the associated blocknumbers. | `1/2` `4/5/6`
[ms{num}_lem_base_bc](ms{num}_lem_base_bc.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing the base lemma (clean; without suffixes) encoded in betacode | `ku/rios` `*solomw/n`
[ms{num}_lem_base_uc](ms{num}_lem_base_uc.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing the base lemma (clean; without suffixes) encoded in unicode | `φανάω` `ἀνά-διδράσκω`
[ms{num}_lem_full_bc](ms{num}_lem_full_bc.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing the full lemma incl. homonym or pl-suffix identifiers, if any) encoded in betacode | `*daui/dhs-pl` `h)/2`
[ms{num}_lem_full_uc](ms{num}_lem_full_uc.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing the full lemma incl. homonym or pl-suffix identifiers, if any) encoded in unicode | `Ἰησοῦσ-πλ` `λέγω2`
[ms{num}_morph](ms{num}_morph.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing a list of morphs | `N-GSM/N-VSM/N-PRI` `V-IEI-2S`
[ms{num}_morph_sim](ms{num}_morph_sim.md)| `str`| `word` | Summary feature for grouped analysis #{num} providing a list of morps similairties to the N1904-TF morph | `100/93/56` `56`
[ms{num}_num_blocks](ms{num}_num_blocks.md)| `int`| `word` | Summary feature for grouped analysis #{num} providing the number of analytic blocks it summarizes | `3`  `2` 

### Feature group: Morpheus (Details)

Feature name | Data type | Available on node | Description 
---|---|---|---
[md{num}\_{inf_elem}](md{num}_{inf_elem}.md)  | `str` | `word` | Overview of features providing access to data from individual Morpheus analytic blocks

### Feature group: Statistic

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[lemma_entr](lemma_entr.md)| `str`| `word` | Absolute entropy of the lemma as predictor of its parent phrase function in bits | number ranging from 0 to 2.5503
[lemma_entr_norm](lemma_entr_norm.md)| `str`| `word` | Normalized entropy of the lemma as predictor of its parent phrase function | number ranging from 0 to 1
[lemma_ttr](lemma_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on lemma for all word nodes under this node | `0.10438939` `0.06539666`
[morph_entr](morph_entr.md)| `str`| `word` | Absolute entropy of a morph-tag as predictor of its parent phrase function | number ranging from 0 to 2.7271
[morph_entr_norm](morph_entr_norm.md)| `str`| `word` | Normalized entropy of a morph as predictor of its parent phrase function | number ranging from 0 to 1
[morph_ttr](morph_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on lemma for all word nodes under this node | `0.11847122` `0.36065573`
[num_words](num_words.md)| `int` | `book` `chapter` `verse` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Number of word nodes below this node | `2` `15643`
[text_entr](text_entr.md)| `str`| `word` | Absolute entropy of the surface level wordform as predictor of its parent phrase function | number ranging from 0 to 2.5850
[text_entr_norm](text_entr_norm.md)| `str`| `word` | Normalized entropy of a surface level wordform as predictor of its parent phrase function | number ranging from 0 to 1
[text_ttr](text_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on wordform for all word nodes under this node | `0.30498177` `0.37854251`

### Feature group: Cross reference

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[osis_id](osis_id.md)| `str`| `book` `chapter` `verse` | Book name accoring to the OSIS (Open Scriptural Information Standard) ID | `2Thess` `Phlm`  

### Feature group: Miscellaneous

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[penntree](penntree.md)| `str`| `sentence` | Penntree like syntax tree  |  
