# N1904addons - Feature: ms{num}_lemma

Feature group |Feature type | Data type | Available for node types
---  | --- | --- | ---
`Morpheus` | `Node`|`int`|`word`

## Feature description

Summary feature for grouped analysis #{num} providing the lemma

This is a Morpheus Summary (ms) feature.

The following Python code demonstrates how to programaticaly obtain details like lemma and morphological tags per grouped analysis blocks.

```Python
wordNodes = F.otype.s("word")
for wordNode in wordNodes:
    for blockNumber in range(1, 9):
        # dynamically get F.ms{blockNumber}_lemma & morph
        lemma = Fs(f"ms{blockNumber}_lemma").v(wordNode)
        if not lemma: continue
        morph_string = Fs(f"ms{blockNumber}_morph").v(wordNode)
        morph_sim_string = Fs(f"ms{blockNumber}_morph_sim").v(wordNode)
        # decompose on the slash
        parts = morph_string.split("/")
        # print what was found
        print(f"node={wordNode}, number={blockNumber} → lemma={lemma}, tags: {parts}")

node=1, number=1 → lemma=Βίβλος, tags: ['N-NSM']
node=1, number=2 → lemma=βίβλος, tags: ['N-NSF']
node=2, number=1 → lemma=γένεσις, tags: ['N-GSF']
node=3, number=1 → lemma=Ἰησοῦς, tags: ['N-GSM', 'N-VSM', 'N-PRI']
...
```