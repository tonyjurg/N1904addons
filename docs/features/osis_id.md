# N1904addons - Feature: osis_id

Feature group |Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`Crossref`](README.md#feature-group-cross-reference) | `Node` | `str` | `book` `chapter` `verse` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature description

Book name according to the OSIS (Open Scriptural Information Standard) ID.

According to [wiki.crosswire.org/OSIS_Bibles](https://wiki.crosswire.org/OSIS_Bibles#OSIS):

> OSIS is an XML Schema definition for Bibles and other Biblical research texts, which enables ministries and other organizations to collaborate more easily. Traditionally, these organizations have stored their documents in disparate, proprietary markups, making it difficult when they wish to share in service with each other. OSIS provides a common markup for multiple visions.

## See also

  - The N1904-TF feature [`bookshort`](https://centerblc.github.io/N1904/features/bookshort.html) provides access to the abbreviated book names (e.g., `MRK` or `ROM`). These match the ones used in tools like [Paratext](https://paratext.org/).

## References:

  - [OSIS resource index](https://ebible.org/osis/)
  
## Data source

See the Jupyter notebook on [this repository](https://tonyjurg.github.io/Create_OSIS_ID_feature_for_TF/).
  
