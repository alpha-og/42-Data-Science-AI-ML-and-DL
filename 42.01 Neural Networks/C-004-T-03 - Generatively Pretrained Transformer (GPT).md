# Generatively Pretrained Transformer (GPT)
---
> [!note] Note
> - All code is with reference to python
> - Reference: https://youtu.be/kCc8FmEb1nY
- **Basic Idea**
	- Convert the string of text into a vocabulary list
	- Tokenize the data into integers in any fashion (character/ word/ sub-word/etc...) using the vocabulary list
	- Split the tokenized data (in this case — a list of integers) into training set (90% of the data in general) and validation set (10% of the data in general)
	- Determine a batch size and block size
	- Split the training data into
		- as many context sets ($x$) as the batch size each having as many tokenized data as the block size
		- as many target sets ($y$) as the batch size each having as many tokenized data as the block size
- **Producing the vocabulary list:** typecast the string of text into a set and typecast that into a list to obtain a list of unique strings which must then be sorted to make sure that the vocabulary is arranged in ascending order
- **Splitting the data:** This is done by slicing the dataset string
- **Tokenizing**
	- *creating identifiers for each character:* Iterate through each token (it maybe a character, word, sub-word or any length of substring) and enumerate it. Add the key value pair of character-integer to a dictionary and also add the key value pair of integer-character to another dictionary
	- Using the two dictionaries mentioned previously we can *encode* and *decode* the tokens by simply iterating through each token
- **Batch Size:** It is the number of parallel training operations to be carried out simultaneously
- **Block Size:** It is the number of tokens to be processed in each training operation (influences the time taken for processing)
- 