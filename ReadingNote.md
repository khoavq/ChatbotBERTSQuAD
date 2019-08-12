## I.	BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

**1.	What is BERT?**

BERT stands for Bidirectional Encoder Representations from Transformers.
 
**2.	Why did the authors conduct the research (existing problems)?**

Some standard language models are unidirectional, and this limits the choice of architectures that can be used during pre-training. 

For example, in OpenAI GPT, the authors use a left-to- right architecture, where every token can only attend to previous tokens in the self-attention layers of the Transformer. It might cause problems when applying fine- tuning based approaches to token-level tasks such as question answering, where the context is extremely significant. In these two sentences “I went to the bank to deposit money”, “I sat on the bank of a river”, the word “bank” is considered the same meaning by using these standard language models.

**3.	What did the authors do (key contributions)?**

  * Demonstrate the importance of bidirectional pre-training for language representations
  * The first fine- tuning based representation model that achieves state-of-the-art performance on a large suite of sentence-level and token-level tasks, outperforming many task-specific architectures
  * Advances the state of the art for eleven NLP tasks

**4.	What are the key differences in the method/approach (innovation)?**

BERT is designed to pre- train deep bidirectional representations from unlabelled text by jointly conditioning on both left and right context in all layers.

**5.	What are main achievements, significance?**
  *  Push the GLUE score to 80.5% (7.7% improvement)
  *  Push MultiNLI accuracy to 86.7% (4.6% improvement)
  *  SQuAD v1.1 question answering Test F1 to 93.2 (1.5 improvement)
  *  SQuAD v2.0 Test F1 to 83.1 (5.1 improvement)

**6.	How can BERT be used?**

As a result, the pre-trained BERT representations can be fine-tuned with just one additional output layer to create state-of-the art models for a wide range of tasks, such as question answering and language inference, without substantial task-specific architecture modifications.

**7.	What can be further improved?**

BERT neglects dependency between the masked positions and suffers from a pretrain-finetune discrepancy. It uses the [MASK] in the pretraining, but this kind of artificial symbols are absent from the real data at finetuning time, resulting in a pretrain-finetune discrepancy. So, would it really learn to produce meaningful representations for non-masked tokens? It is also not clear what happens if there are no [MASK] tokens in the input sentence.
It assumes the predicted (masked) tokens are independent of each other given the unmasked tokens.

**8.	Research problem identified (to be reflected in the proposed research)?**

Build a chatbot for question and answering based on BERT
