# pratchett_vocabulary_analysis
For my master's thesis, I investigated the effects of a subtype of Alzheimer's Disease, posterior cortical atrophy (PCA) on writing. I analyzed a corpus of 35 books by Terry Pratchett, a well-known author with PCA. 
This repository specifically contains Jupyter notebooks relevant to the vocabulary analysis section of my master's thesis. I investigated longitudinal trends in the proportions of words from five different lexico-semantic word categories (spatial prepositions, colors, numbers, adjectives of form, and function words). I drew these word categories from Shebani et al.'s 2017 paper "Semantic word category processing in semantic dementia and posterior cortical atrophy". 

 Below is a description of each of these notebooks:

`0-data_preparation`: I loaded TEI XML files containing Pratchett's books and their respective metadata, such as Prachett's age at publication, the novel's date of publication, whether a novel was a young adult novel (young adult novels ended up being excluded from analysis in the final verion), wordcount, cleaned and tokenized texts, and raw texts.

`1a-semantic_wordcategory`: For each novel, I extracted rates of tokens from each of the lexico-semantic word categories: spatial preposition (e.g., 'inside'), form (e.g. 'round'), color (e.g., 'red'), number (e.g., 'twelve'), and function word (e.g. 'also'). "Number" is the only lexico-semantic word category with no pre-defined list - instead, number tokens are counted using the StandfordNLP features tagger. I constructed the function word token list by retrieving 300 most common words from all of Pratchett's novels (stored in the file mostcommon300list.txt) and manually removing content words from this list.

Rates of spatial preposition, color, form, number, and function word tokens from full texts are stored in 1a-lexicosemantic_wordcategory.csv.

`1b-semantic_wordcategory_sigtesting`: I tested rates of tokens from each lexico-semantic word category as predictors of age at publication in a multivariate linear regression model. Kendall's tau was also calculated between age at publication and each of the lexico-semantic word token rates.
