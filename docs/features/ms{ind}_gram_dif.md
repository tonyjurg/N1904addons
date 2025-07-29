# N1904addons - Feature: ms{ind}_gram_dif

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node` | `str` | `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

Maximum grammatical difference of any Morpheus analysis summarized by this index against N1904-TF grammtical properties.

## Feature values

A fixed-length string of 9 characters indicating differing grammatical properties. Characters are drawn from:

* A dot (`.`) when Morpheus and N1904-TF agree (including when both values are `None`).
* A letter (one of `l p c n g t m v d`) when Morpheus differs, indicating which category is mismatched.
* The character positions correspond to the canonical order of morphological features shown in the following table.

| Position | Field Key | Grammatical Property 
| :------: | :-------: | :------------------: 
|     0    |    `l`    |         Lemma        
|     1    |    `p`    |        Person        
|     2    |    `c`    |         Case         
|     3    |    `n`    |        Number        
|     4    |    `g`    |        Gender        
|     5    |    `t`    |         Tense        
|     6    |    `m`    |         Mood         
|     7    |    `v`    |         Voice        
|     8    |    `d`    |        Degree        


## See also

[Using this feature](using_gram_dif.md).

## Data source

GitHub repository [Create_morpheus_TF_dataset](https://tonyjurg.github.io/Create_morpheus_TF_dataset/).
