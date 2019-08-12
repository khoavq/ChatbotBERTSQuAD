## I.	BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

#### 1.	What is BERT?
BERT stands for Bidirectional Encoder Representations from Transformers.
 
#### 2.	Why did the authors conduct the research (existing problems)?
Some standard language models are unidirectional, and this limits the choice of architectures that can be used during pre-training. 

For example, in OpenAI GPT, the authors use a left-to- right architecture, where every token can only attend to previous tokens in the self-attention layers of the Transformer. It might cause problems when applying fine- tuning based approaches to token-level tasks such as question answering, where the context is extremely significant. In these two sentences “I went to the bank to deposit money”, “I sat on the bank of a river”, the word “bank” is considered the same meaning by using these standard language models.

#### 3.	What did the authors do (key contributions)?
  * Demonstrate the importance of bidirectional pre-training for language representations
  * The first fine- tuning based representation model that achieves state-of-the-art performance on a large suite of sentence-level and token-level tasks, outperforming many task-specific architectures
  * Advances the state of the art for eleven NLP tasks

#### 4.	What are the key differences in the method/approach (innovation)?
BERT is designed to pre- train deep bidirectional representations from unlabelled text by jointly conditioning on both left and right context in all layers.

#### 5.	What are main achievements, significance?
  *  Push the GLUE score to 80.5% (7.7% improvement)
  *  Push MultiNLI accuracy to 86.7% (4.6% improvement)
  *  SQuAD v1.1 question answering Test F1 to 93.2 (1.5 improvement)
  *  SQuAD v2.0 Test F1 to 83.1 (5.1 improvement)

#### 6.	How can BERT be used?
As a result, the pre-trained BERT representations can be fine-tuned with just one additional output layer to create state-of-the art models for a wide range of tasks, such as question answering and language inference, without substantial task-specific architecture modifications.

#### 7.	What can be further improved?
BERT neglects dependency between the masked positions and suffers from a pretrain-finetune discrepancy. It uses the [MASK] in the pretraining, but this kind of artificial symbols are absent from the real data at finetuning time, resulting in a pretrain-finetune discrepancy. So, would it really learn to produce meaningful representations for non-masked tokens? It is also not clear what happens if there are no [MASK] tokens in the input sentence.
It assumes the predicted (masked) tokens are independent of each other given the unmasked tokens.

#### 8.	Research problem identified (to be reflected in the proposed research)?
Build a chatbot for question and answering based on BERT


## II.	XLNet: Generalized Autoregressive Pretraining for Language Understanding

#### 1.	What is XLNet?
XLNet, a generalized autoregressive pretraining method that (1) enables learning bidirectional contexts by maximizing the expected likelihood over all permutations of the factorization order and (2) overcomes the limitations of BERT thanks to its autoregressive formulation.

#### 2.	Why did the authors conduct the research (existing problems)?
Relying on corrupting the input with masks, BERT neglects dependency between the masked positions and suffers from a pretrain-finetune discrepancy. To be clearer:

 a) The [MASK] token used in training does not appear during fine-tuning
  * What does BERT do for tokens that are not replaced with [MASK]?
  * In most cases, BERT can simply copy non-masked tokens to the output. So, would it really learn to produce meaningful representations for non-masked tokens?
  * Of course, BERT still needs to accumulate information from all words in a sequence to denoise [MASK] tokens. But what happens if there are no [MASK] tokens in the input sentence?

 b)	BERT assumes the predicted (masked) tokens are independent of each other given the unmasked tokens

#### 3.	What did the authors do (key contributions)?
There has been a gap between language modeling and pretraining due to the lack of the capability of bidirectional context modeling, XLNet generalizes language modeling and bridges such a gap.

#### 4.	What are the key differences in the method/approach (innovation)?
XLNet does this by introducing a variant of language modeling called “permutation language modeling”. Permutation language modeling objective that not only retains the benefits of AR models but also allows models to capture bidirectional contexts.

Permutation language models are trained to predict one token given preceding context like traditional language model, but instead of predicting the tokens in sequential order, it predicts tokens in some random order. 

#### 5.	What are main achievements, significance?
Empirically, XLNet achieves state-of-the-art results on 18 tasks, i.e., 7 GLUE language understanding tasks, 3 reading comprehension tasks including SQuAD and RACE, 7 text classification tasks including Yelp and IMDB, and the ClueWeb09-B document ranking task. Under a set of fair comparison experiments, XLNet consistently outperforms BERT on 20 tasks, often by a large margin.

#### 6.	What can be further improved?
N/A

#### 7.	Research problem identified (to be reflected in the proposed research)?
Build a chatbot for question and answering based on XLNet

### _References_

[1] https://mlexplained.com/2019/06/30/paper-dissected-xlnet-generalized-autoregressive-pretraining-for-language-understanding-explained/ \
[2] http://mlexplained.com/2019/01/07/paper-dissected-bert-pre-training-of-deep-bidirectional-transformers-for-language-understanding-explained/
