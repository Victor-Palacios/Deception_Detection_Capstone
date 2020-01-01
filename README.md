# Deception Detection Summary

## Problem 1
    How does a liar's speech vary from a truth-teller?
    
## Approach for Problem 1
### Create features to analyze from raw statements:
No. of characters

No. of words

Avg. length of words

Readability score

POS (part of speech): Is this word an adjective, noun, something else?

NER (named entity recognition tagging): tags the kind of noun--person, place, organization, etc.--among other things

SD (syntatic dependency): the relation between tokens

## Results of Problem 1

### Significantly higher for Truth
Statement Count: Character & Word count

General (15 tags) POS tagging: adj., conjunction+ (i.e., "of", "about", "to", etc.), noun, number, determiner (i.e., "a", "an", "the")

Specific (52 tags) POS tagging: cardinal numbers, determiners, conjunctions(subordinating or preposition), adjective(comparative), noun(singular or mass)

NER: references to dates, percentages, numbers

SD: adjectival modifier, determiner, numeric modifier, object of preposition, prepositional modifier

### Significantly higher for Falsehoods
Statement Length: Average word length

Specific (52 tags) POS tagging: verb (modal auxiliary), superfluous punctuation

NER: references to people

SD: clausal complement, clausal subject

## Problem 2
    Can verbal deception be predicted with machine learning?

## Approach for Problem 2
### 5 datasets for machine learning
    The standard in natural language processing is to normalize text, i.e., distill content in statements by
    removing frequent words (i.e., stopwords), punctuation, etc.
    But, given the statistics from the data analysis revealed that the frequency of stopwords, punctuation, etc.
    varied with statistical difference in lies versus truth, 
    I hypothesize that normalization may lower the ability for machine learning algorithms to predict deception.
    To test this hypothesis, I will compare the raw statements, 3 normalized permutations of the raw statements, 
    and a dataframe composed of statistics about the raw statements (number of words, nouns, etc.)
#### Raw statements
    The statements as they are (i.e., without any alteration)
#### Lightly normalized statements
    Statement words were converted to lowercase, and the following were removed: 
    whitespaces and html tags
#### Lightly norm-lemmatized statements
    "Lightly normalized statements" were lemmatized
#### Fully normalized statements
    "Lightly normalized and lemmatized statements" had the following removed: 
    punctuation, stopwords, special characters
#### Statistical Features
    In the exploratary analysis, over 100 features were created based on word count, number of nouns, etc.;
    this will be the basis for the final model that does not use statements, 
    instead it uses statistics about the statements.

## Results of Problem 2
### Comparing the 5 datasets
#### raw statements vs normalized statements
    performed best on train set (62% accuracy) : lightly normalized statements
#### BoW, n-GRAM=1-4, TF-IDF
    performed comparably well on train set (62% accuracy) : n-gram size 1-2 and tfidf
#### Multinomial Naive Bayes (mnb), Logistic Regression (lgr), Random Forests
    performed comparably well on train set (62% accuracy) : mnb and lgr
#### Best accuracy on hold-out set from the above groups
    57% accuracy on the hold-out set: lightly normalized statements, ngram_range = (1,2), mnb 
#### Engineered Features
    comparable results to the above: 57% accuracy on the hold out set using mnb
