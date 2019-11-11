# Deception Detection (Work-in-Progress)

# Summary thus far

## Lemmatization
Lemmatized Statements (removed whitespaces, puncuation, stopwords, special characters; converted to lowercase)

## Tagged Text
POS (part of speech): Is this word an adjective, noun, something else?

NER (named entity recognition tagging): tags the kind of noun--person, place, organization, etc.--among other things

SD (syntatic dependency): the relation between tokens

## Feature Engineered variables
No. of characters

No. of words

Avg. length of words

Readability score

## Statistics

### Significantly higher for Truth
Statement Count: Character & Word count

General (15 tags) POS tagging: adj., conjunction+ (i.e., "of", "about", "to", etc.), noun, number, & determiner (i.e., "a", "an", "the")

Specific (52 tags) POS tagging: ### cardinal numbers, determiners, conjunctions(subordinating or preposition), adjective(comparative), noun(singular or mass)

NER: references to dates, percentages, numbers

SD: adjectival modifier, determiner, numeric modifier, object of preposition, & prepositional modifier

### Significantly higher for Falsehoods
Statement Length: Average word length

Specific (52 tags) POS tagging: verb (modal auxiliary), superfluous punctuation

NER: references to people

SD: clausal complement & clausal subject

