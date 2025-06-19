# N1904addons - Feature: formaltag

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Miscellaneous`](README.md#feature-group-miscellaneous) | `Node` | `str` | `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

The "form-oriented" morphological tag.

## Feature values

A morphological tag according to Sandborg-Petersen morphology.

Some examples `T-DSN` and `V-AAI-3S`.  These codes can be decoded using the following tool:

 <script>
    function openMinimalWindow() {
      window.open(
        'https://centerblc.github.io/N1904/features/SP-Morph-decode.html',
        '_blank',
        'toolbar=no,location=no,status=no,menubar=no,scrollbars=yes,resizable=yes,width=450,height=400'
      );
    }
  </script>
  
<button onclick="openMinimalWindow()">Open Morph decoder</button>

## Notes

For detailed information on the definiton of this morphology see [biblicalhumanities/Nestle1904/morph/parsing.txt](https://github.com/biblicalhumanities/Nestle1904/blob/master/morph/parsing.txt).


The difference between this feature `formaltag` and feature [`morph`](https://centerblc.github.io/N1904/features/morph.html) in N1904-TF is best explained by the following comments from [github.com/biblicalhumanities](https://github.com/biblicalhumanities/Nestle1904/tree/master/morph#morphological-analysis), with three explanatory notes inserted between brackets:

> Two morphological tags are provided: One which is more "functional" (note 1: feature `morph`), and one which is more "form-oriented" (note 2: this feature `formaltag`). The differences between the two only exist in the description of the verbal system (note 3: for 2144 verbal instances). The form-oriented system is very careful not to make morphological distinctions which are not warranted by the form. For example, the present indicative does not exhibit any formal characteristics which allows the distinction between the middle and the passive voice, hence present indicative verbs are always described as being middle/passive in the "form-oriented" tag. The "functional" tag, on the other hand, sometimes makes a distinction between the middle and the passive, even in the tenses where this is not formally distinguished by the forms. This is so as to be sensitive to the semantics of the verb.

## Data source

This feature was copied from [`functionaltag` in Nestle 1904 GNT](https://tonyjurg.github.io/Nestle1904GBI/features/functionaltag.html). 
Ultimately the data was taken from the (optional) XML attribute FormalTag for each element node representing a word in the [GBI nodes XML data](https://github.com/Clear-Bible/macula-greek/tree/main/Nestle1904/nodes).

Also (from [github.com/Clear-Bible](https://github.com/Clear-Bible/macula-greek/blob/1f3e7c91e12970d47e4faf7b92d676aa57685f7b/SBLGNT/README.md?plain=1#L36)):
> The N1904 contains `FunctionalTag` and `FormalTag` attribute information recording word-level
morphological information. This information originates with the [Biblical Humanities edition of the
N1904](https://github.com/biblicalhumanities/Nestle1904/).
