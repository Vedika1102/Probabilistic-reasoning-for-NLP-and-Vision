
# Part 1: Part-of-Speech Tagging

## Problem Formulation:

The first assignment involved developing a system capable of tagging words in a sentence with their corresponding parts of speech. The goal was to formulate this problem in terms of probabilistic models that can predict the most likely tags based on the context of each word.


## Program Description:

In the Solver class, we've implemented three distinct methods: posterior, train, and solve. The train function initializes the probabilities based on the training data. It calculates transition and emission probabilities, which are crucial for the posterior function to return the log-probability of a given sentence and label pairing.

For the posterior calculations, the simple model assumes each word's tag is independent of adjacent words, relying solely on emission probabilities. The HMM model integrates transition probabilities, reflecting the likelihood of moving from one tag to the next, to compute a more nuanced posterior probability.

The solve method acts as a selector for the tagging algorithms based on the model specified. The simplified function uses emission probabilities to choose the most likely tag for each word. In contrast, the hmm_viterbi function implements the Viterbi algorithm, using both transition and emission probabilities to find the most likely sequence of tags for a sentence.

## Problems and Solutions:

During implementation, we faced challenges in handling words unseen in the training set. We addressed this by assigning a minimal probability, avoiding zero probability, which would have invalidated our log-probability calculations. We also made design decisions regarding the treatment of transition probabilities, ensuring that even the least likely transitions had a non-zero probability.

# Part 2: Reading Text in an Image

## Problem Formulation:

This part of the assignment is aimed to extract and interpret text from a noisy image. We approached this by applying HMMs to model the problem, assuming that the text within an image could be represented as a sequence of characters, each with a probabilistic model describing its appearance and relation to neighboring characters.

## Program Description:

In this we worked on the character recognition logic using the simplified and viterbi functions. The simplified function implemented a direct pixel comparison between the test and training images for character matching. For more accurate text recognition, our viterbi function applied the Viterbi algorithm to consider both the appearance of individual characters and the likelihood of character sequences.

The OCR algorithm is a two-fold process. The simplified function matches each character in the test image to the most similar character in the training set, using a simple pixel comparison. For a more accurate prediction, we used the viterbi function, which applies the Viterbi algorithm to find the sequence of characters that has the highest overall probability, considering both the appearance of individual characters and the transitions between them.

## Problems and Solutions:

The OCR part was particularly challenging due to the noise in the images. We experimented with different weightings for matching characters and adjusting the model to give less weight to noise pixels. Through iterative testing and tuning of the model parameters, we were able to significantly improve the recognition accuracy.

## Work Division:

For both parts of the assignment, all of us, Gayatri, Rishikesh, and Vedika, initially worked separately to come up with the solution. After the individual work, we came together to share what we had each done, including the problems we had encountered. We shared our thought processes on the best solutions and then collectively worked towards the final code.
