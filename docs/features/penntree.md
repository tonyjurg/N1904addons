# N1904addons - Feature: penntree

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Miscellaneous`](README.md#feature-group-miscellaneous) | `Node` | `str` | `sentence` | [⚠️](featurestatus.md#Caution "Caution")

## Feature description

Penn tree like syntax tree.


## Feature values

A penn tree like string.

<div class="alert">
  <strong>IMPORTANT</strong><br>
  This is Work In Progress. The format of these penntrees may be changed in the future (when new insights arise).
</div>

## Example usage

The trees can be printed using packages like [nltk](https://www.nltk.org/).

```txt
from nltk import Tree
ptbString=F.penntree.v(sentenceNode)
tree = Tree.fromstring(ptbString)
tree.pretty_print()  # console-style print   
                                               S                                 
                                               |                                  
                                               WG                                
            ___________________________________|_________________                 
           CL                                                    |               
    _______|________________                                     |                
   |                      NP-SBJ                                 |               
   |        ________________|_____________                       |                
   |       |       |                      CL                     |               
   |       |       |         _____________|____                  |                
  VP-V     |       |       VP-V              PP-ADV              CL              
   |       |       |        |         _________|______       ____|____________    
  VERB    NOUN   PUNCT     VERB     PREP      NOUN  PUNCT  NOUN PRON  NOUN  PUNCT
   |       |       |        |        |         |      |     |    |     |      |   
ἐγένετο ἄνθρωπος   ,   ἀπεσταλμένος παρὰ      θεοῦ    ,   ὄνομα αὐτῷ ἰωάνης   ·  

```

## Data source

[Github repostiory tonyjurg/Create_penntree_feature_for_TF ](https://tonyjurg.github.io/Create_penntree_feature_for_TF/)
