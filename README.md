# English to French Machine Translation using Seq2Seq LSTM

## Overview

This project implements a traditional Sequence-to-Sequence (Seq2Seq) neural machine translation model using LSTM networks.

The goal is to translate English sentences into French sentences by learning patterns from parallel sentence pairs.

## Project Features

- Encoder-Decoder architecture using LSTM
- Word-level tokenization
- Custom vocabulary building
- Padding and special tokens handling
- Teacher forcing during training
- Training and evaluation pipeline
- Sample translation predictions

## Dataset

Dataset used:
- English-French parallel sentence pairs

Training data:
- 60,000 English-French sentence pairs

Example:

English:
I love you

French:
Je t'aime

## Model Architecture

### Encoder

The encoder reads the input English sentence and converts it into hidden representations using an LSTM.

Architecture:
Input Sentence
|
Embedding Layer
|
LSTM Encoder
|
Hidden State + Cell State

### Decoder

The decoder generates the translated French sentence using the encoder's hidden states.

Architecture:
Hidden State
|
LSTM Decoder
|
Linear Layer
|
French Output Tokens

## Training Details

- Framework: PyTorch
- Model: Seq2Seq LSTM
- Hidden Size: 512
- Training Epochs: 50
- Dataset Size: 60,000 sentence pairs

## Sample Output

Example predictions:
English: how are you
Predicted French:
comment allez vous

(Add sample_output.png here)

## Future Improvements

- Add Attention mechanism
- Implement Scaled Dot Product Attention
- Train on larger datasets
- Improve BLEU score evaluation
- Deploy using FastAPI

## Requirements

Install dependencies:

```bash
pip install -r requirements.txt
Author
Suhani Bhardwaj
