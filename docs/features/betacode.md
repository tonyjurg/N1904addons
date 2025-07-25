# N1904addons - Feature: betacode

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-analyses-meta-and-summary) | `Node` | `str` | `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

The Greek unicode surface level word in <a href="https://stephanus.tlg.uci.edu/encoding/BCM.pdf" target="_blank">Beta Code</a>. It is important to realize that this feature is **not** a transliteration of N1904-TF's <a href="https://centerblc.github.io/N1904/features/unicode.html" target="_blank">`unicode`</a>. The feature can be rather considered a translateration of the <a href="https://centerblc.github.io/N1904/features/unicode.html" target="_blank">`text`</a> feature. The following image shows the relation between the various lexographic features in the N1904-TF dataset. 

<IMG SRC="images/details_surface_features.png" WIDTH="400">

For instance, where feature `unicode` would contain 'Ἀβραάμ.' in our conversion to `betacode` we will map it to '*)abraa/m', so without transliterating the trailing period.  

Beta Code is used in specific applications like <a href="https://github.com/perseids-tools/morpheus" target="_blank">Morpheus morphological tagging</a>.

## Usage in TF queries and Python

When working with string values for feature betacode in Text-Fabric, you may encounter characters that interfere with your queries or code. The type of interference differs between using betacode in a Text-Fabric query template or a 'plain Python' environment. In a Text-Fabric query template the `|` functions as `OR` operator, while in plain Python the backslash `\` is normaly used to signify an escape. 

**Text-Fabric Query Template:**

Here it is adviced to escape the `|` character (that is replace it with `\|`). A raw string indicator `r` should also be added before the query template definition to prevent warning messages. To examine all constraints see <a href="https://annotation.github.io/text-fabric/tf/about/searchusage.html#additional-constraints" target="_blank">TF searchusage</a>. In example 1 the query template is defined to locate occurences of the Beta Code `a)pokatalla/ch|`. This query correctly retrieves the single occurrence of ἀποκαταλλάξῃ, found in Ephesians 2:16.

```Python
# Example 1: Text-Fabric query template
betaCodeQuery=r"""
word betacode=a)pokatalla/ch\|
"""
```
**Plain Python**

However, when performing a *'plain Python'* compare do not escape the `|` character. Instead, escape the backslash `\` character by replacing it with a double backslash `\\`. Failure to escape these inherent backslashes can lead to silent errors, except when the backslash is the last character in the betacode (e.g., `kai\`, which will result in an unterminated string). See also example 2 and 3 below.

```Python
# Example 2: Plain Python string compare
for wordNode in F.otype.s('word'):
    if F.betacode.v(wordNode)=='a)pokatalla/ch|': print (wordNode)

# Example 3: Escaping backslash in plain Python
for wordNode in F.otype.s('word'):
    if F.betacode.v(wordNode)=="kai\\": print (wordNode)
```

## See also

- [Beta Code encoding](https://stephanus.tlg.uci.edu/encoding.php).
- [Python library for handling Betacode (beta-code-py)](https://github.com/perseids-tools/beta-code-py).

## Data source

 - [Github repository](https://tonyjurg.github.io/Create_TF_feature_betacode/)
