# NLP-Assignment-1

## Results
* The plot of frequency vs 1/rank of tokens is somewhat a straight line (with 3 or 4 outliers) which verifies the 1st statement of Zipf's Law which says frequency of tokens is proportional to 1/rank of the tokens.
* The plot of volume of text (total number of tokens) (|V|) to different types of tokens (N) is very similar to graphs of type y = kx^b with k and b here estimated to be 14.66 and 0.55 respectively. This is in accordance to the Heap's Law which state |V| = kN^b where k lies between 10 and 100 and b lies between 0.4 and 0.6, hence verifying Heap's Law.
* The plot of number of meanings of token (m) and it's rank (r) might seem a little random but on observation we can see a pattern similar to type of y = kx^-0.5 which verifies the second statement of Zipf's Law which states m is inversely proportional to r^0.5
* The plot of average frequency for length (f) and the length (l) is very similar to the type y = kx^-1 which verifies the third statement of Zipf's Law which states f is inversely proportional to l.

## Answers to when and when not question
The Zipf's Law for meaning - 

Zipf's law for meaning is valid most of the time in the case of content words but in the case of function words or stop words generally it is not valid. The frequency of stop words is generally very high but they hardly have any lexical meaning attached to them contradicting the predicted relation of frequency and meanings of words by Zipf's Law which says number of meanings is proportional to root of frequency.

The Zipf's Law for length -

The Zipf's Law for length is in general valid. Each length token can have any frequency, high or low hence we see in the graph that each length has lot of frequency token in it. But the general trend is that as length gets longer it gets restricted to lower frequencies. This trend makes the average frequency lower as we go for longer tokens and hence we obtain the graph of average frequency vs length verifying Zipf's Law. So we can say the law may not be true for a particular token but on average or stastically the law holds.

## Assumptions
* Word formed by joining 2 words using - or _ is different from the original words.
* Special characters other than - or _ cannot come between any 2 words without any space and hence can be removed without affecting their identity.
* A token without any alphanumeric character is not a valid token.

## Statistics of the Shakespeare corpus by my assumptions
* The total number of tokens are :  920565
* Different types of tokens are :  30318
* The TTR (Type by Tokens Ratio) is : 0.033
