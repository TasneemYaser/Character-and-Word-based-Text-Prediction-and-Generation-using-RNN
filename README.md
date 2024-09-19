# Overview
This repository contains two approaches for text prediction and generation using Recurrent Neural Networks (RNNs): character-based and word-based models. Both models are trained on Wikipedia pages related to a specific topic, with the goal of generating coherent text after training and predicting the next character or word based on a given input sequence.
# Character-based Approach:
## Data Preprocessing:
Extracted Wikipedia titles and fetched the corresponding pages.
Processed the text to extract individual characters.
Applied one-hot encoding to represent each character.
## Model:
Created sequences of characters with a sequence length of 10.
Used a 3-layer Simple RNN with a dense layer for character prediction.
The index2char dictionary was used to map predicted indices to characters.
## Training:

Trained the model for 50 epochs (achieved 59% accuracy) and for 200 epochs (achieved 68% accuracy).
Used categorical crossentropy as the loss function and the Adam optimizer.
Text Prediction and Generation:

After training, the model can predict the next character in a sequence based on a provided input of 10 characters.
The generated text sequence is built character-by-character by predicting and appending the next character until the desired length is reached.

# Word-based Approach:
## Data Preprocessing:
Used the same Wikipedia titles and pages as the character-based approach.
Extracted words from the text.
Utilized FastText pre-trained embeddings for word representation.
## Model:
Created sequences of words with a sequence length of 10.
Used a 4-layer Simple RNN and a dense layer to predict word embeddings.
A custom get_closest_word function was developed to retrieve the closest word from the predicted embedding vector.
## Training:
Trained the model for 50 epochs (achieved 45% accuracy) and for 200 epochs (achieved 68% accuracy).
Used mean square error (MSE) as the loss function and the Adam optimizer.
Text Prediction and Generation:

After training, the model can predict the next word in a sequence based on a given input of 10 words.
The generated text sequence is constructed word-by-word, where each predicted word is fed back into the model for generating the next word, until the required length is reached.

# Future Improvements
- Experiment with deeper RNN layers and advanced architectures (e.g., LSTM, GRU) to capture long-term dependencies.
- Try different embedding models for word-based text generation, like GloVe or Word2Vec.
- tune hyperparameters for better accuracy and generalization.
- Implement beam search or sampling strategies for more diverse text generation.

**Feel free to modify the code and improve the models as you explore different approaches to text prediction and generation.**
