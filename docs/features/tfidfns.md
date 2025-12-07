# N1904addons - Feature: tfidfns

Feature group | Feature type | Data type | Available for node types | Feature status
---  | --- | --- | --- | ---
[`statistic`](README.md#feature-group-statistic) | `Node` |`str` |  `word` | [✅](featurestatus.md#Trustworthy "Trustworthy")

## Feature short description

TF-IDF score (x 1,000,000) for this token, calculated using only non-stopword tokens in the GNT corpus, aggregated per book.

## Feature values

A scaled by 1,000,000 positive float number *stored as a string*.

## Detailed feature description

The Term Frequency-Inverse Document Frequency (TF-IDF) feature treats each book as a 'document' and providing the TF-IDF scores per normalized token, and then map those scores back to each node in the corpus. This allows to identify book-specific vocabulary and to use these weights for further quantitative or visualization-oriented analyses.

This feature excludes all stop words (any token with a [part-of-speech](https://centerblc.github.io/N1904/features/sp.html#start) value of 'intj', 'prep', 'art', 'conj'); all values for these token are set to zero.

It follows the information provided in the [TF-IDF explanation on GeeksforGeeks](https://www.geeksforgeeks.org/machine-learning/understanding-tf-idf-term-frequency-inverse-document-frequency/) and uses scikit-learn's [TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html) for computations.

## See also

Related features:

  - [tfidf](tfidf.md): TF-IDF score (x 1,000,000) for this token, calculated using all tokens in the GNT corpus, aggregated per book

## Data source

GitHub repository [Create_TF-IDF_Text-Fabric_features](https://github.com/tonyjurg/Create_TF-IDF_Text-Fabric_features).