# N1904addons feature: betacode

Feature type | Data type | Available for node types
---  | --- | --- 
`Node`|`String`|`word`

## Feature description

The Greek unicode word in Betacode. Betacode is used in specific applications like [Morpheus morphological tagging](https://github.com/perseids-tools/morpheus).

## Note

This feature is **not** a literal representation of N1904-TF's [unicode](https://centerblc.github.io/N1904/features/unicode.html#start) feature. For instance, the unicode 'Ἀβραάμ.' will map to '*)abraa/m', so without transliterating the trailing '.' into betacode. 

## See also

- [Beta Code encoding](https://stephanus.tlg.uci.edu/encoding.php).
- [Python library for handling Betacode (beta-code-py)](https://github.com/perseids-tools/beta-code-py).
- [Details on the conversion process](https://github.com/tonyjurg/GNT-greek2betacode).
