## Demo 1
### **Q/A with RAG + LangChain**

In this project, the LangChain framework was utilized to develop RAG applications aimed at answering questions based on documents.

RAG represents a more flexible and less expensive approach to overcoming knowledge cutoffs compared to fine-tuning, allowing the model access to additional external data (e.g., proprietary knowledge) during inference.

  - Initially, constructed a one-pass question-answering solution.
  - Subsequently, incorporated chat history to track and extract relevant information from conversations and data sources.






## Demo 2
### **Fine-tuning with LLMs + PEFT + Quantization**

Fine-tuning a pre-trained model FLAN-T5 from Hugging Face for enhanced dialogue summarization involved several steps as belows to compare the performance of full fine-tuning, PEFT, and quantization methods.

- Fully fine-tuned the pretrained model using the 🤗 Transformers high-level `Trainer` API.
- Applied a PEFT method to a pretrained base model for training using LoRA.
- Quantized to 4-bit precision using the `bitsandbytes` library with a PEFT adapter on top.
- Utilized the ROUGE metric to evaluate the results.

> Conclusion:

- A fully-tuned model for a small dataset may yield poor performance due to overfitting. However, by adding the dataset, adjusting hyperparameters, and experimenting with various model configurations, performance can be enhanced by up to 10.34% (ROUGELsum).
- The advantages of PEFT typically outweigh the slightly lower performance metrics (a small percentage decrease of 0.89% in the ROUGE1 metrics compared to full fine-tuning).
  - Furthermore, other metrics outperform full fine-tuning (up to 3.35% ROUGELsum). **PEFT has demonstrated superior performance over full fine-tuning in low-data regimes.** Moreover, training with the PEFT method requires significantly fewer computing and memory resources, often just a single GPU.
- Quantizing a small model to 4-bit precision resulted in worse performance compared to the original model. This indicated **a significant loss in accuracy due to the compression of high precision weights to lower precision in a small model.**


