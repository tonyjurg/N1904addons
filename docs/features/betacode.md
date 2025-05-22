# N1904addons feature: betacode

Feature group |Feature type | Data type | Available for node types
---  | --- | --- | ---
`Morpheus` | `Node`|`String`|`word`

## Feature description

The Greek unicode word in Betacode. Betacode is used in specific applications like [Morpheus morphological tagging](https://github.com/perseids-tools/morpheus).

## Note

This feature is **not** a transliteration of N1904-TF's [`unicode`](https://centerblc.github.io/N1904/features/unicode.html) feature but a translateration of the [`text`](https://centerblc.github.io/N1904/features/unicode.html) feature. The following image shows the relation between the various lexographic features in the N1904-TF dataset. 

<IMG SRC="/images/details_surface_features.png" WIDTH="400">

For instance, wher feature `unicode` would contain 'Ἀβραάμ.' in our conversion to `betacode` we will map it to '*)abraa/m', so without transliterating the trailing period.  

## See also

- [Beta Code encoding](https://stephanus.tlg.uci.edu/encoding.php).
- [Python library for handling Betacode (beta-code-py)](https://github.com/perseids-tools/beta-code-py).

## Data source

 - [Github repository](https://github.com/tonyjurg/create_TF_feature_betacode)
