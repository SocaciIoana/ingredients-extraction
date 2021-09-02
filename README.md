# ingredients-extraction

## Task

For a given recipe extract the ingredients and their position (start and end indices).

## Solution

1. Data Analysis Results
- empty text recipes were eliminated
- some recipes had ingredients that were not present in the recipe text itself so we eliminated those ingredients
- duplicate recipes in terms of both ingredients and recipe text were eliminated

2. Modeling the problem as a Named Entity Recognition task and training an ML model in this sense
- words from recipes text were encoded using the Keras Tokenizer class - given the vocabulary size (number of unique words) each word was encoded using a unique integer
- the output we expect from our model is the same size as the input (input is padded as text is of different sizes) and gives a classification of each word from the input as being an ingredient (1) or not an ingredient (0)
- the neural network model layers include an Embedding and a Bi-LSTM layer. This architecture was chosen as being more close to what represents nowadays state of the art models in the field of information extraction.

3. The model is evaluated 
- 20% of the data is used for testing (a validation set was not considered in this case). 99% accuracy was obtained on this data (to be reviewed).
- a much simpler model should be considered too for comparison reasons
- output is presented in the stated form

## FUTURE CONSIDERATIONS
- consider using word embeddings (word2vec) as word representation
- use transfer learning in order to start with pre-trained weights on the Embedding layer
- consider a lighter model too (this one has a pretty large number of parameters - see model summary from notebook)
