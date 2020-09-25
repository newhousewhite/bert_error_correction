# Summary
tune a BERT model for error correction and deploy in a local machine (docker)

# Reference
- huggingface: https://github.com/huggingface/transformers
- BERT Error Detection & Correction: https://github.com/sunilchomal/GECwBERT
- deploy to sagemaker: https://github.com/data-science-on-aws/workshop

# Methods
- Pre-trained BERT model -> Fine-tuning with CoLA data -> Grammar Error Detection (GED) model
- Masked LM (MLM) of BERT for alternate sentence generation -> GED for correct suggestions

## Data
- CoLA data
  - correct/in-correct label for a single sentence
  - 10,657 English sentences

## Steps (Abstract-level)
- Tokenize the sentence using Spacy
- Check for spelling errors using Hunspell
- For all preposition, determiners & action verbs, create a set of probable sentences
- Create a set of sentences with each word "masked", deleted or an additional determiner, preposition or helper verbs added
- Used BERT Masked LM to determine possible suggestions for masks
- Use the Grammer Error Detection model to select appropriate solutions

# Setup
- install pytorch 1.5 & tensorflow 2, using below references, in a virtualenv
  - https://illya13.github.io/RL/tutorial/2020/04/28/installing-pytorch-on-ubuntu-20.html
  - https://illya13.github.io/RL/tutorial/2020/04/26/installing-tensorflow-on-ubuntu-20.html
- Start
```
pyenv activate bert

```
