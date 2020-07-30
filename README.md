# NLP Spellchecking System + Evaluation of its Performance

Completed during the MSc Computer Science - Data Analytics on the hollbrook.txt file which is available in the repository.

## Assignment Outline

This assignment involved the creation of a spellchecking system and an evaluation of its performance using the Python programming language.

The file consists of lines of text, with one sentence per line. Errors in the line are marked with a | as follows

My siter|sister go|goes to Tonbury .

In this case the word 'siter' was corrected to 'sister' and the word 'go' was corrected to 'goes'.

In some places in the corpus two words maybe corrected to a single word or one word to a multiple words. This is denoted in the data using underscores e.g.,

My Mum goes out some_times|sometimes .

The purpose of this project was to treat the lines like a single token.

Libraries used: NLTK

## Task 1 (10 Marks)
- Write a parser that can read all the lines of the file holbrook.txt and print out for each line the original (misspelled) text, the corrected text and the indexes of any changes. The indexes refers to the index of the words in the sentence. In the example given, there is only an error in the 10th word and so the list of indexes is [9]. It is not necessary to analyze where the error occurs inside the word.
- Then split the data into a test set of 100 lines and a training set.

## Task 2 (10 Marks):
- Calculate the frequency (number of occurrences), ignoring case, of all words and their unigram probability from the corrected training sentences.

## Task 3 (15 Marks):
- Edit distance is a method that calculates how similar two strings are to one another by counting the minimum number of operations required to transform one string into the other. There is a built-in implementation in NLTK that works as follows:
from nltk.metrics.distance import edit_distance
- Wrote a function that calculates all words with minimal edit distance to the misspelled word. 
1. Collected the set of all unique tokens in the training set.
2. Found the minimal edit distance, that is the lowest value for the function edit_distance between token and a word in the training set.
3. Output all unique words in train that have this same (minimal) edit_distance value.

## Task 4 (15 Marks):
- Wrote a function that takes a (misspelled) sentence and returns the corrected version of that sentence. The system scans the sentence for words that are not in the dictionary (set of unique words in the training set) and for each word that is not in the dictionary, the spellchecker chooses a word in the dictionary that has minimal edit distance and has the highest unigram probability.

## Task 5 (10 Marks):
Evaluate the accuracy of my method using the test corpus, i.e., how many words from my system's output match the corrected sentence.

## Task 6 (35 Marks):
- Considered several modifications to my algorithm that would improve the accuracy of the algorithm developed in Task 3 and 4.

## Task 7 (5 Marks):
- Repeated the evaluation (as in Task 5) of my new algorithm and compared it to the algorithm from Task 3 and 4.
