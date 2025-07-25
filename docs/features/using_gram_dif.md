# Using feature set  `m*_gram_dif`

## Introduction

The `m*_gram_dif` features quantify grammatical differences between the Morpheus analyses and the N1904-TF annotations, which in this context is regarded the reference. Each feature in this group annotates a wordnode with a 9-character string indicating whether Morpheus’s analysis  **differs** from the reference. Differences are indicated using a `letter` while matches are indicated usint a dot (`.`). 

## Related features

Feature(s) | Description
---|---
[md{ind}_gram_dif](md{ind}_gram_dif) | grammatical difference against N1904-TF, with num in the range (1-24), inclusive.
[ms{ind}_gram_dif](ms{ind}_gram_dif.md) | grammatical difference against N1904-TF, with num in range (1-12), inclusive.
[mm_gram_dif](mm_gram_dif.md) | grammatical difference against N1904-TF 


## Data Format

Each value for a feature `m*_gram_dif` produces a fixed-length string of 9 characters. Characters are drawn from:

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

## Example usage

