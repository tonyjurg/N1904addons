# N1904addons - Feature: md{num}_{inf_elem}

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Morpheus`](README.md#feature-group-morpheus-details) | `Node` | `str` | `word` | [🆗](featurestatus.md#Reasonable "Reasonable")

## Feature description

Value for property {inf_elem} reported by Morpheus analysis block #{num}.

## Feature names and values

This page documents **about 750** Text-Fabric features named like `md3_case`, `md17_end_codes`, `md12_lem_full_uc` or `md1_morph`. They collectively form the class of Morpheus detail features ([more info](morpheus_tf_feature_classes.md)).

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
      <td></td>
    </tr>
    <tr>
      <td>morph_flags</td>
      <td><code>str</code></td>
      <td>List of morp flags provided by Morpheus</td>
      <td><code>indeclform</code> <code>ind/nu_movable</code></td>
    </tr>
    <tr>
      <td rowspan="14">Wordform</td>
      <td>aug1_bc</td>
      <td><code>str</code></td>
      <td>(:aug) Augment mapping in betacode</td>
      <td><code>i)>ei)</code> <code>a)>h)</code></td>
    </tr>
    <tr>
      <td>aug1_uc</td>
      <td><code>str</code></td>
      <td>(:aug) Augment mapping in unicode</td>
      <td><code>ἰ>εἰ</code> <code>ἐ>ἠ</code></td>
    </tr>
    <tr>
      <td>end_bc</td>
      <td><code>str</code></td>
      <td>(:end) Wordform ending in betacode</td>
      <td><code>ous</code> <code>ws</code> <code>en</code></td>
    </tr>
    <tr>
      <td>end_uc</td>
      <td><code>str</code></td>
      <td>(:end) Wordform ending in unicode</td>
      <td><code>ες</code> <code>να</code> <code>εν</code></td>
    </tr>
    <tr>
      <td>lem_base_bc</td>
      <td><code>str</code></td>
      <td>(:lem) Base lemma in betacode</td>
      <td><code>*bi/blos</code> <code>ui(o/s</code></td>
    </tr>
    <tr>
      <td>lem_base_uc</td>
      <td><code>str</code></td>
      <td>(:lem) Base lemma in unicode</td>
      <td><code>ἀδελφός</code> <code>γεννάω</code></td>
    </tr>
    <tr>
      <td>lem_full_bc</td>
      <td><code>str</code></td>
      <td>(:lem) Full lemma in betacode (incl. homonym or pl marker)</td>
      <td><code>*bi/blos</code> <code>ge/nesis</code></td>
    </tr>
    <tr>
      <td>lem_full_uc</td>
      <td><code>str</code></td>
      <td>(:lem) Full lemma in unicode (incl. homonym or pl marker)</td>
      <td><code>Βίβλος</code> <code>γένεσις</code></td>
    </tr>
    <tr>
      <td>lem_homonym</td>
      <td><code>str</code></td>
      <td>(:lem) Set to '1' if this is a homonym lemma</td>
      <td><code>1</code> &lt;empty&gt;</td>
    </tr>
    <tr>
      <td>lem_pl_suffix</td>
      <td><code>str</code></td>
      <td>(:lem) PL suffix of lemma (if '1' often proper or geographic name) </td>
      <td><code>1</code> &lt;empty&gt;</td>
    </tr>
    <tr>
      <td>prvb_bc</td>
      <td><code>str</code></td>
      <td>(:prvb) **Space** separated list of prepositions in betacode</td>
      <td><code>meta/ a)na/</code> <code>su/n</code></td>
    </tr>
    <tr>
      <td>prvb_uc</td>
      <td><code>str</code></td>
      <td>(:prvb) Slash separated list of prepositions in unicode</td>
      <td><code>ἐκ/ἐπί</code> <code>πρός</code></td>
    </tr>
    <tr>
      <td>stem_bc</td>
      <td><code>str</code></td>
      <td>(:stem) Stem in betacode</td>
      <td><code>meta/ a)na/</code> <code>su/n</code></td>
    </tr>
    <tr>
      <td>stem_uc</td>
      <td><code>str</code></td>
      <td>(:stem)Stem in unicode</td>
      <td><code>ἐκ ἐπί</code> <code>πρός</code></td>
    </tr>
    <tr>
     <td rowspan="4">Codes and flags</td>
      <td>end_codes</td>
      <td><code>str</code></td>
      <td>(:end) list of codes for ending (mainly references to endtables in stemlib)</td>
      <td><code>os_ou</code> <code>os_ou/os_ou</code></td>
    </tr>
    <tr>
      <td>end_flags</td>
      <td><code>str</code></td>
      <td>(:end)list of flags for ending (mainly additional morphological properties)</td>
      <td><code>nu_movable</code> <code>contr</code></td>
    </tr>
    <tr>
      <td>stem_codes</td>
      <td><code>str</code></td>
      <td>(:stem) listed morph codes for stem  (mainly references to endtables in stemlib)</td>
      <td><code>os_h_on</code> <code>aor1/aw_denom</code></td>
    </tr>
    <tr>
      <td>stem_flags</td>
      <td><code>str</code></td>
      <td>(:stem) listed morph flags for stem (mainly additional morphological properties)</td>
      <td><code>..</code> <code>indeclform</code></td>
    </tr> 
    <tr>
      <td rowspan="2">Derived</td>
      <td>morph</td>
      <td><code>str</code></td>
      <td>Slash separated list of derived morphtag(s) following Sandborg-Petersen morphology (like feature <a href="https://centerblc.github.io/N1904/features/morph.html#start">morph</a> in N1904-TF)</td>
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

