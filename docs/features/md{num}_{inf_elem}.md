# N1904addons - Feature: md{num}_{inf_elem}

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-details) | `Node` | `str` | `word` | [🆗](featurestatus.md#Reasonable "Reasonable")

## Feature description

Value for property {inf_elem} reported by Morpheus analysis block #{num}.

## Feature names and values

This page documents **over 600** Text-Fabric features named like `md3_case`, `md1_gender` or `md21_morph_flags`. 

The labels {num} and {inf_elem} are placeholders, which stand for:
 - `{num}`: The sequence number of a Morpheus analysis block, ranging from 1 to 24 (the maximum number of returned analysis blocks).
 - `{inf_elem}`: One of the properties listed in the table below.

 
<table style="border-collapse: collapse; border: 1px solid black;">
  <thead>
    <tr>
      <th>Category</th>
      <th>{inf_elem}</th>
      <th>Data type</th>
      <th>Description</th>
      <th>Examples</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="7">Grammatical</td>
      <td>case</td>
      <td><code>str</code></td>
      <td>List with grammatical case(s)</td>
      <td><code>nom</code> <code>gen</code> <code>nom/voc/acc</code></td>
    </tr>
    <tr>
      <td>degree</td>
      <td><code>str</code></td>
      <td>Grammatical degree</td>
      <td><code>comparative</code></td>
    </tr>
    <tr>
      <td>gender</td>
      <td><code>str</code></td>
      <td>List with grammatical gender(s)</td>
      <td><code>masc</code> <code>neut</code> <code>masc/fem</code></td>
    </tr>
    <tr>
      <td>mood</td>
      <td><code>str</code></td>
      <td>Verb mood</td>
      <td><code>indicative</code> <code>participle</code></td>
    </tr>
    <tr>
      <td>number</td>
      <td><code>str</code></td>
      <td>Grammatical number</td>
      <td><code>sg</code> <code>dual</code> <code>pl</code></td>
    </tr>
    <tr>
      <td>tense</td>
      <td><code>str</code></td>
      <td>Verb tense</td>
      <td><code>aorist</code> <code>present</code></td>
    </tr>
    <tr>
      <td>voice</td>
      <td><code>str</code></td>
      <td>Verb voice</td>
      <td><code>active</code> <code>middle/passive</code></td>
    </tr>
    <tr>
      <td rowspan="3">Additional details</td>
      <td>dialect</td>
      <td><code>str</code></td>
      <td>List of dialect(s)</td>
      <td><code>attic</code>  <code>doric/aeolic</code></td>
    </tr>
    <tr>
      <td>morph_codes</td>
      <td><code>str</code></td>
      <td>List of morp codes provided by Morpheus</td>
      <td><code>article</code> <code>os_ou/os_ou</code></td>
    </tr>
    <tr>
      <td>morph_flags</td>
      <td><code>str</code></td>
      <td>List of morp flags provided by Morpheus</td>
      <td><code>indeclform</code> <code>ind/nu_movable</code></td>
    </tr>
    <tr>
      <td rowspan="12">Wordform</td>
      <td>aug1_bc</td>
      <td><code>str</code></td>
      <td>Augment in betacode</td>
      <td>—</td>
    </tr>
    <tr>
      <td>aug1_uc</td>
      <td><code>str</code></td>
      <td>Augment in unicode</td>
      <td>—</td>
    </tr>
    <tr>
      <td>ending_bc</td>
      <td><code>str</code></td>
      <td>Wordform ending in betacode</td>
      <td>—</td>
    </tr>
    <tr>
      <td>ending_uc</td>
      <td><code>str</code></td>
      <td>Wordform ending in unicode</td>
      <td>—</td>
    </tr>
    <tr>
      <td>lem_base_bc</td>
      <td><code>str</code></td>
      <td>Base lemma in betacode</td>
      <td><code>*bi/blos</code> <code>ge/nesis</code></td>
    </tr>
    <tr>
      <td>lem_base_uc</td>
      <td><code>str</code></td>
      <td>Base lemma in unicode</td>
      <td><code>Βίβλος</code> <code>γένεσις</code></td>
    </tr>
    <tr>
      <td>lem_full_bc</td>
      <td><code>str</code></td>
      <td>Full lemma in betacode</td>
      <td><code>*bi/blos</code> <code>ge/nesis</code></td>
    </tr>
    <tr>
      <td>lem_full_uc</td>
      <td><code>str</code></td>
      <td>Full lemma in unicode</td>
      <td><code>Βίβλος</code> <code>γένεσις</code></td>
    </tr>
    <tr>
      <td>lem_homonym</td>
      <td><code>str</code></td>
      <td>Homonym of the lemma</td>
      <td><code>1</code> &lt;empty&gt;</td>
    </tr>
    <tr>
      <td>lem_pl_suffix</td>
      <td><code>str</code></td>
      <td>PL suffix of lemma</td>
      <td><code>1</code> &lt;empty&gt;</td>
    </tr>
    <tr>
      <td>prvb_list_uc</td>
      <td><code>str</code></td>
      <td>List of prepositions in unicode</td>
      <td></td>
    </tr>
    <tr>
      <td>prvb_list_bc</td>
      <td><code>str</code></td>
      <td>List of prepositions in unicode</td>
      <td><code>1</code> &lt;empty&gt;</td>
    </tr>
    <tr>
      <td rowspan="2">Derived</td>
      <td>morph</td>
      <td><code>str</code></td>
      <td>List of derived morphtag(s)</td>
      <td><code>V-AAI-3S</code> <code>N-NDF/N-VDF/N-ADF</code></td>
    </tr>
    <tr>
      <td>pos</td>
      <td><code>str</code></td>
      <td>Determined part of speech</td>
      <td><code>verb</code> <code>preposition</code></td>
    </tr>
  </tbody>
</table>


## Using these features

<div class="alert alert-important">
  <strong>IMPORTANT</strong><br>
  The .tf files for these features are located at <a href="https://github.com/tonyjurg/N1904addons/tree/main/detailed_set/1.0.0">"N1904addons/detailed_set"</a> and not standard part of the N1904addons. To use these features you need to load <em>both</em> the N1904addons and the detailed feature set.
</div>

To load both the 'standard' N1904addon features and the detailed_set, you need to invoking Text-Fabric like:

```
A = use ("CenterBLC/N1904", version="1.0.0", silence="terse", mod=["tonyjurg/N1904addons/tf/", "tonyjurg/N1904addons/detailed_set"], hoist=globals())
```

The following image shows an example of a Morpheus analyses block.

<IMG SRC="images/morpheus_block_example.png">

## Data source

