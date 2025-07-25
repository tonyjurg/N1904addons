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

## Some notes on interpretation

The compare will mark as a difference any grammatical property that *can* be interpreted differently. In the following case the Morpheus parsing does return the tag from N1904-TF, but also another one. This is due to underspecification (the ending ος can be either masculine or feminine). 
<img src="https://raw.githubusercontent.com/tonyjurg/N1904addons/main/docs/features/images/angelos.png">

In case the morphological tag differs between N1904-TF and the Morpheus derived data, this feature can still report `.........`, in case the tag difference is due to e.g., dialect. See the following example:

<img src="https://raw.githubusercontent.com/tonyjurg/N1904addons/main/docs/features/images/paralabein.png">

The situation may be even more tricky. For the following wordform the N1904-TF has morphologicaly tagged Isaak as `N-PRI`, just as it was done on the Morpheus based dataset. However, the is a mismatch reported on the grammatical case. This occurs because all TF features in the *_gram_dif group are computed by comparing each grammatical property in a Morpheus analytic block with its counterpart in the N1904-TF dataset. As is clear from the Morpheus analytic block in Figure 20, no information about grammatical case is provided. As a result, the compare function flags this as a difference, since such information is present in the N1904-TF dataset. This can be easily seen when comparing the N1904-TF data with the raw data from Morpheus.

<img src="https://raw.githubusercontent.com/tonyjurg/N1904addons/main/docs/features/images/isaak.png">

