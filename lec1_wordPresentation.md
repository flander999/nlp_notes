# Word representation

## Using **wordnet**
Cannot allways believe. If we try to chain these words, and we finally find a totally different meaning.
1. missing nuance
2. minssing new meaning of words
3. subjective
4. requires human labor to create and adapt
5. cannot compute accurate word similarity.

## Count-based Word Representation

### One-hot Encoding
1. Regard words as discrete symbols.
2. Words be represented by **one-hot vectors**

***problem***:
1. No similarity representation among words
2. Inefficiencey(imagine 1e10 words need a huge number of a huge array)

**PS:** vector dimension is the number of words in vocabulary.

### Bag of Words(BOW)
This approach is describing the occurrence of words(onlu concern whether and how many times that the word appear in a document). It do not concern the order or sturcture or where the words appear in the document.

***Problem***:
1. Ignore the context and in turn meaning of words in the documents. (**semantics**)


### Term Frequency-Inverse Document Frequency (TF-IDF)
It is a way of representing how important a word is to a document in a collection or corpus.
$$w_{i,j} = tf_{i,j} \times \log{\frac{N}{df_i}}$$

Where: 
$w_{i,j}$ = weight of term i in document j
$tf_{i,j}$ = number of occurences of term i in document j
$N$ = total number of documents
$df_i$ = number of documents containing term i

#### Term frequency
The count of how many times a word occurs in a given document. (same as bag of words)

#### Document Frequency
The number of times a word occurs in a corpus of documents.

***KEY***:
1. can set down the weight of those words that appear frequently but less important. Cannot just remove them, because these words may still be relevent to your analysis.
2. Using **log** to make the **idf** be small such as (0,1,2,3,4,5,6) but not (1,10,100,1000,10000,100000).
3. sometimes we need $1+df_i$ to replace $df_i$ to aovid the zero.
