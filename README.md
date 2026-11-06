# Seq2Seq Machine Translation

English-to-French translation with an LSTM encoder-decoder in PyTorch. The implementation is `seq2seq_translation.ipynb`.

## Data

The notebook reads `fra.txt` (tab-separated English, French, and a license column) and keeps the first 60,000 pairs. Text is lowercased and split on whitespace. Sequences use `<PAD>`, `<SOS>`, `<EOS>`, and `<UNK>`, then pad or truncate to length 20.

## Encoder

The encoder is a 2-layer LSTM.

| Setting | Value |
| --- | --- |
| Embedding size | 256 |
| Hidden size | 512 |
| Layers | 2 |
| Dropout | 0.3 |
| Batch size | 32 |

It returns the final hidden state and cell state. The decoder is the same size, with a linear layer over the French vocabulary. Training uses teacher forcing 0.5, Adam at `1e-3`, pad-masked cross-entropy, and gradient clipping at 1.0. Decoding is greedy argmax.

The notebook trains for 10 epochs. The saved log shows epoch 10 training loss 1.2721. Example prompts are "how are you", "good morning", "thank you", and "where are you".

## Run

```bash
pip install -r requirements.txt
```

Open `seq2seq_translation.ipynb` and point the file load at a local `fra.txt`. The notebook path is `/content/fra.txt`. `sample_output.png` is in the repository.
