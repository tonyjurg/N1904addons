# About entropy an N1904-TF

In our syntactic annotated Text-Fabric dataset, we define entropy as a measure of the uncertainty or variability of how an element (such as a surface level word, its morph, or its lemma) predicts or aligns with the syntactic functions (like Subject, Object, etc.) of the phrase it belongs to.

Entropy reflects the extent to which such an element's syntactic behavior is predictable. High entropy values indicate that a form is ambiguous, as it appears in multiple syntactic functions with similar probabilities. In contrast, low entropy values signify that a form is strongly associated with a single syntactic function, making it a reliable indicator of that role within the parent phrase.

## Formal Definition

The feature value was calculated using Shannon entropy, defined as:

$$
H(f|d) = -\sum_{f \in F} P(f|d) \cdot \log_2 P(f|d)
$$

Where:

* $H(f|d)$ represents the entropy of a datatype form $d$ given a syntactic function $f$.
* $d$ represents a specific datatype like morph (e.g., "N-NSM"), text (e.g, "λόγος") or lemma. 
* $f$ represents a specific syntactic function of the parent phrase (like "Subj", "Objc", etc.)
* $P(f|d)$ = the probability that datatype form $d$ leads to function $f$ measured over the complete N1904-TF dataset.

This gives a measure (in bits) of how unpredictable the function is for a given morph.

## Example from the N1904-TF dataset

To demonstrate how the entropy is determined, let's consider the wordform "λόγος" (N-NSM; a Nominative Singular Masculine Noun).

We know that there are 63 occurenses of the form "λόγος" in the N1904-TF dataset.  According to the current syntactic annotation, these occurense of the word "λόγος" are part of a set of possible phrase functions:

  * 55 instances are part of a `Subject` phrase
  * 3 instances are part of a `Predicate Complement` phrase 
  * 2 instances are part of a `Conjunction` phrase  {this is under investigation}
  * 2 instances are part of phrases labeled as 'Unknown' {this is under investigation}
  * 1 instance is part of a `Predicate` phrase

Based on this distribution, we can calculate the probabilities of a *randomly chosen* instance of the wordform "λόγος" to belong to a phrase with a specific phrase function:

- $P(Subj|\text{λόγος}) = 55 / 63 = 0.873015873015873$
- $P(PreC|\text{λόγος}) = 3 / 63 ≈ 0.047619047619047616$
- $P(Pred|\text{λόγος}) = 1 / 63 ≈ 0.015873015873015872$
- $P(Conj|\text{λόγος}) = 2 / 63 ≈ 0.031746031746031744$
- $P(Unkn|\text{λόγος}) = 2 / 63 ≈ 0.031746031746031744$

Next we can compute the entropy: 

$$ Entropy = - (P(Subj|\text{λόγος}) \cdot \log_2 P(Subj|\text{λόγος}) + P(PreC|\text{λόγος}) \cdot \log_2 P(PreC|\text{λόγος}) + P(Conj|\text{λόγος}) \cdot \log_2 P(Conj|\text{λόγος}) + P(Unkn|\text{λόγος}) \cdot \log_2 P(Unkn|\text{λόγος}) + P(Pred|\text{λόγος}) \cdot \log_2 P(Pred|\text{λόγος})) $$

If we calculate each term we get: 

- For $P(Subj|\text{λόγος}) = 0.873015873015873$, $\log_2 0.873015873015873 \approx -0.1905$. So, $0.873015873015873 \cdot -0.1905 \approx -0.1663$.
- For $P(PreC|\text{λόγος}) = 0.047619047619047616$, $\log_2 0.047619047619047616 \approx -4.392$. So, $0.047619047619047616 \cdot -4.392 \approx -0.2093$.
- For $P(Conj|\text{λόγος}) = 0.031746031746031744$, $\log_2 0.031746031746031744 \approx -4.974$. So, $0.031746031746031744 \cdot -4.974 \approx -0.1581$.
- For $P(Unkn|\text{λόγος}) = 0.031746031746031744$, same as above, $-0.1581$.
- For $P(Pred|\text{λόγος}) = 0.015873015873015872$, $\log_2 0.015873015873015872 \approx -6.322$. So, $0.015873015873015872 \cdot -6.322 \approx -0.1004$.

So the final entropy can be calculated as:

$$ Entropy ≈ - (-0.1663 - 0.2093 - 0.1581 - 0.1581 - 0.1004) $$
$$ Entropy ≈ - (-0.7922) $$
$$ Entropy ≈ 0.7922 $$

This matches what was found by the calculations performe in our notebook, which used float numbers (instead of the rounded ones above):

```python
>>> entropies_by_datatype['text']['λόγος']
'0.7910'
```

The low entropy value (0.7910) indicates that the wordform (i.e, "λόγος") is strongly associated with one specific phrasefunction.  Hence a *random* occurence of the wordform “λόγος” is strongly predictive of it being part of a subject phrase.

It is important to realize that each words entropy is measured against the whole of the N1904-TF corpus (which is 'hidden' in the $P(f|m)$ of the formal definition). It is likely that the values for entropy of the same morp are different when considered within another corpus.

