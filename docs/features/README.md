# Overview features

This repository offers a set of features built specifically for use with the [N1904 Text-Fabric dataset](https://CenterBLC.github.io/N1904/). Text-Fabric is a powerful platform for analysing biblical texts with linguistic and structural detail.

The features of this package can be grouped as follows:

### Feature group: Morpheus

#### Meta data

These features describe the Morpheus analysis per word-node ([more info](../using_the_morpheus_features.md#morpheus-feature-classes)). 

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[mm_gram_dif](mm_gram_dif.md)| `str`| `word` | Summary feature for agrammatical difference against N1904-TF  ([fieldmap](using_gram_dif.md)) | `lpc.gtmv.` `l.cng....`
[mm_raw_bc](mm_raw_bc.md)| `str`| `word` | Betacode representation of the raw: field of Morpheus for this word node | `*)ihsou=` `*xristou=`
[mm_raw_uc](mm_raw_uc.md)| `str`| `word` | Unicode representation of the raw: field of Morpheus for this word node | `Ἰησοῦς`
[mm_num_lemmas](mm_num_lemmas.md)| `int`| `word` | Number of different lemmas returned by the Morpheus analytic blocks for this word node | `1`  `3`
[mm_num_blocks](mm_num_blocks.md)| `int`| `word` | Total number of analytic Morpheus blocks return for this word node | `1` `9` `11`
[mm_num_morphs](mm_num_morphs.md)| `int`| `word` | Total number of returned different morph tags | `1` `2` `4`
[mm_max_sim](mm_max_sim.md)| `int`| `word` | Maximum similarity with N1904-TF morph tag for *any* lemma | `100` `90` `11`

#### Summary data

These features summarize the Morpheus analysis grouped per lemma ([more info](../using_the_morpheus_features.md#morpheus-feature-classes)).

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[ms{*ind*}_block_nums](ms{ind}_block_nums.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing a list with the associated blocknumbers. | `1/2` `4/5/6`
[ms{*ind*}_gram_dif](ms{ind}_gram_dif.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing grammatical difference against N1904-TF  ([fieldmap](using_gram_dif.md)) | `lpc.gtmv.` `....g..v.`
[ms{*ind*}_lem_base_bc](ms{ind}_lem_base_bc.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing the base lemma (clean; without suffixes) encoded in betacode | `ku/rios` `*solomw/n`
[ms{*ind*}_lem_base_uc](ms{ind}_lem_base_uc.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing the base lemma (clean; without suffixes) encoded in unicode | `φανάω` `ἀνά-διδράσκω`
[ms{*ind*}_lem_full_bc](ms{ind}_lem_full_bc.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing the full lemma incl. homonym or pl-suffix identifiers, if any) encoded in betacode | `*daui/dhs-pl` `h)/2`
[ms{*ind*}_lem_full_uc](ms{ind}_lem_full_uc.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing the full lemma incl. homonym or pl-suffix identifiers, if any) encoded in unicode | `Ἰησοῦσ-πλ` `λέγω2`
[ms{*ind*}_lem_homonym](ms{ind}_lem_homonym.md)| `str` | `word` | lemma homonym indicator for grouped analysis #*ind* | 
[ms{*ind*}_lem_pl_suff](ms{ind}_lem_pl_suff.md)| `str` | `word` | lemma pl suffix indicator for grouped analysis #*ind* |
[ms{*ind*}_morph](ms{ind}_morph.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing a list of morphs | `N-GSM/N-VSM/N-PRI` `V-IEI-2S`
[ms{*ind*}_morph_sim](ms{ind}_morph_sim.md)| `str`| `word` | Summary feature for grouped analysis #*ind* providing a list of morphs similairties to the N1904-TF morph | `100/93/56` `56`
[ms{*ind*}_num_blocks](ms{ind}_num_blocks.md)| `int`| `word` | Summary feature for grouped analysis #*ind* providing the number of analytic blocks it summarizes | `3`  `2` 

#### Detail data

These features provide access to detailes of each individual Morpheus analysis block ([more info](../using_the_morpheus_features.md#morpheus-feature-classes)).

Feature name | Data type | Available on node | Description |Examples
---|---|---|---|---
[md{*ind*}_gram_dif](md{ind}_gram_dif.md)| `str`| `word` | Detailed feature for agrammatical difference against N1904-TF ([fieldmap](using_gram_dif.md)) | `lpc.gtmv.` `l.cng....`
[md{*ind*}\_{inf_elem}](md{ind}_{inf_elem}.md)  | `str` | `word` | Overview of features providing access to data from individual Morpheus analytic blocks | *morphological and lexical properties*

#### Analytic data

These features provide access to features based upon analysis of the Morpheus data in connection with N1904-TF morphosyntactic tagging ([more info](../using_the_morpheus_features.md#morpheus-feature-classes)).

Feature name | Data type | Available on node | Description 
---|---|---|---
[ma{*ind*}\_pf_altern](ma{ind}_pf_altern.md)  | `str` | `phrase` | Phrase function alternatives based on morphological tagging according to base N1904-TF (*ind*=0) or Morpheus (*ind* in range 1,12)
[ma{*ind*}\_pf_flip](ma{ind}_pf_flip.md)  | `int` | `phrase` | Max function flip potential for phrase according to morphological tagging according to base N1904-TF (*ind*=0) or Morpheus (*ind* in range 1,12)
[ma_pf_max_flip](ma_pf_flip_max.md)  | `int` | `phrase` | Max function flip potential for both N1904-TF and Morpheus based tagging.



### Feature group: Statistic

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[lemma_entr_mbit](lemma_entr_mbit.md)| `int`| `word` | Absolute entropy of the lemma as predictor of its parent phrase function in mili-bits | number ranging from 0 to 2550
[lemma_entr_norm](lemma_entr_norm.md)| `int`| `word` | Normalized entropy of the lemma as predictor of its parent phrase function (scale 0-1000) | number ranging from 0 to 737
[lemma_ttr](lemma_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on lemma for all word nodes under this node | `0.10438939` `0.06539666`
[morph_entr_mbit](morph_entr_mbit.md)| `int`| `word` | Absolute entropy of a morph-tag as predictor of its parent phrase function in mili-bits| number ranging from 0 to 2727
[morph_entr_norm](morph_entr_norm.md)| `int`| `word` | Normalized entropy of a morph as predictor of its parent phrase function (scale 0-1000)| number ranging from 0 to 788
[morph_ttr](morph_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on lemma for all word nodes under this node | `0.11847122` `0.36065573`
[num_words](num_words.md)| `int` | `book` `chapter` `verse` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Number of word nodes below this node | `2` `15643`
[text_entr_mbit](text_entr_mbit.md)| `int`| `word` | Absolute entropy of the surface level wordform as predictor of its parent phrase function in mili-bits| number ranging from 0 to 2584
[text_entr_norm](text_entr_norm.md)| `int`| `word` | Normalized entropy of a surface level wordform as predictor of its parent phrase function (scale 0-1000)| number ranging from 0 to 747
[text_ttr](text_ttr.md)| `str` | `book` `chapter` `sentence` `group` `wg` `phrase` `subphrase` `clause` | Type to Token Ratio based on wordform for all word nodes under this node | `0.30498177` `0.37854251`

### Feature group: Cross reference

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[betacode](betacode.md)| `str`| `word` | The Greek unicode word in betacode | `*)ihsou=` `*xristou=`
[osis_id](osis_id.md)| `str`| `book` `chapter` `verse` | Book name accoring to the OSIS (Open Scriptural Information Standard) ID | `2Thess` `Phlm`  

### Feature group: Miscellaneous

Feature name | Data type | Available on node | Description | Examples
---|---|---|---|---
[formaltag](formaltag.md)| `str`| `word` | The "form-oriented" morphological tag from GBI nodes data | `V-AAI-3S`
[orig_order](orig_order.md)| `int`| `word` | Word order as it is found in the XML Low Fat Tree implementation of the corpus | `567` `1043`
[penntree](penntree.md)| `str`| `sentence` | Penntree like syntax tree  |  



