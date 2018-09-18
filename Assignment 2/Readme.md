# NLP Assignment 2

## Results and Answers
#### How many n-grams are possible and how many actually exists?
In the train set - 
There are 8886 distinct unigrams in my train set. We know by the knowledge of combinatorics that there can be as many as (unigrams)^n total n-grams.

Bigrams - There are total 78960996 bigrams possible whereas we see that there are only 50077 distinct bigrams in the train set.

Trigrams - There are 701647410456 trigrams possible whereas we see that only 69303 are there in the train set.

Quadgrams - There are 6.2348389e+15 quadgrams possible whereas we see that only 74853 are there in the train set.

#### Implement add-1 smoothing for bigram model and give 2-3 examples where drastic change in the count occurs post-smoothing. Can you explain this drastic change in a sentence?
Some examples of drastic change in bigram models - 

* of the  -  562  ->  108.36368593238822
* \<s\> i  -  781  ->  297.75944250871083
* in the  -  406  ->  55.464035769828925

This drastic change occurs as most of the probability mass is transferred from their probability and distributed to all the possible zero probability bigrams of corresponding first unigram and as the count of their first unigram is high, the effect of decrease in probabilitiy amplifies and we see a very drastic change in counts. 

As count of a bigram = probability of the bigram * count of its first unigram

#### Do you observe the constant discounting value ‘d’ by implementing Good-turing smoothing technique? If yes, what is the value of ‘d’? 
As such there is a little bit variation in discounting value 'd' for each frequency but the mean value turns out to be 0.9106292951975302 with a variance of 0.11676834771403574.

#### Compute the perplexity value for the test dataset for the bigram model using add-1 and Good-turing. Which performs better? 
The Good turing smoothing performs much better than Add-1 smoothing on the test dataset. Perplexity of Good Turing is 15.65 and that of add-1 is 1120.5. This might be because add-1 smoothing results in drastic changes which decrease the probability of the bigram drastically but in the corpus still the chance of occurence of the bigram is high and hence for a lot of place add-1 ends up putting a lower probability to a bigram when it occurs frequently in the courpus. This decreases probability of sentence which increases perplexity value. This happens for almost all the high count bigrams in add-1 and hence effect is far greater. In contrast, Good Turing does not lead to such drastic changes as in add-1.


## Arguments
* n_grams()
  * lst - list of the processed sentences which are to be used
  * n - the model which has to be used (1 - unigram, 2 - bigram, 3 - trigram, 4 - quadgram)
  
* MLE_calculation()
  * n_grams - The dictionary of counts of the n-gram model you want to use
  * n_1_grams - The dictionary of counts of the corresponding n-1 gram model
  
* conversion()
  * n_grams - The dictionary of MLE of the n-gram model you want to use

* next_word()
  * n - the n-gram model you want to use to predict the next word
  * last_n_1_gram - list of last n-1 words of the sentence for prediction
  
* string_Generator()
  * n - the n-gram model you want to use to generate strinf
  * string - the string which is under the process of prediction
  * last_n_1_gram - list of last n-1 words of the sentence for prediction
  
* Generator()
  * n - the n-gram model you want to use to generate the string
  
* Probability()
  * sentence - The processed sentence whose probability is to be predicted
  * n - the n-gram model you want to use to predict the probability of sentence
  
* expand_vocab()
  * test - the dataset which should be added
  * count - the dictionary of counts of the n-grams which is to be expanded
  * total - total number of n-grams observed in the old corpus
  * n - the n-gram model you want to use
  
* add1_smoothed_count()
  * bi_gram - bigram for which to calculate smoothed value
  
* Frequency_of_frequencies()
  * n_grams - the expanded dictionary of counts of the n-grams
  
* Fof_approximation()
  * arr - a new data structure
  
* GoodTuring()
  * frequency - frequency of the bigram we want to smooth in the expanded dictionary
  * N - array of FOF
  * popt - array of optimal values for the function f()
  
* Perplexity()
  * sentence - The processed sentence whose perplexity is to be predicted
  * mode - 0 for add-1 and 1 for Good turing


## Return values
* n_grams()
  * count - dictionary of counts of the n-gram
  * total - the total number of n-grams in corpus
  
* MLE_calculation()
  * n_grams - The dictionary of MLE values of the n-grams
  
* conversion()
  * d - a new data structure

* next_word()
  * word - the next word to be appended in the string
  
* string_Generator()
  * string - the string which is under the process of prediction
  
* Generator()
  * string - the final generated string
  
* Probability()
  * p - the probability of the sentence in the log10 space
  
* expand_vocab()
  * count - the dictionary of counts of the n-grams which has been expanded
  * total - total number of n-grams observed in the old corpus
  
* add1_smoothed_count()
  * a tuple of probability of the bigram and effective count in the corpus
  
* Frequency_of_frequencies()
  * N - list if FOF
  * arr - a special 2d list for optimization
  
* Fof_approximation()
  * popt - the array of optimal values for f()
  
* GoodTuring()
  * c - the effective count for the frequency after smoothing
  
* Perplexity()
  * the perplexity value of the sentence
