Biomedical Named Entity Recognition (NER)
Project Overview
This project focuses on identifying chemical and disease names in biomedical text. This task is called Biomedical Named Entity Recognition (NER).
The project compares three deep learning approaches:
1. BiLSTM baseline built with Keras.
2. Frozen BioBERT, where the BioBERT encoder is kept frozen and a classification head is trained.
3. Fine-tuned BioBERT, where both the BioBERT encoder and the classification head are trained on the dataset.
The goal is to evaluate how well each approach identifies chemical and disease entities in biomedical sentences.
Dataset
The project uses the BC5CDR dataset available through Hugging Face:
- Dataset: tner/bc5cdr
- Task: Biomedical named entity recognition
- Entity types: Chemical and Disease
- Label format: BIO tagging (B-, I-, and O)

Models Compared
1. BiLSTM Baseline
A Bidirectional Long Short-Term Memory (BiLSTM) model was implemented using Keras. It uses an embedding layer, a bidirectional LSTM layer, dropout, and a token-classification output layer.
This model provides a baseline for comparison with the transformer-based models.
2. Frozen BioBERT
This model uses the pretrained checkpoint dmis-lab/biobert-base-cased-v1.2.
The BioBERT encoder is frozen, while the classification head is trained for the NER task. This tests how useful pretrained biomedical language representations are without updating the encoder weights.
3. Fine-tuned BioBERT
The same pretrained BioBERT checkpoint is used, but the encoder and classification head are both trained on the BC5CDR training data. This allows the model to adapt its pretrained representations to the target NER task.
For BioBERT, word-level labels are aligned with tokenizer subwords. Special tokens and continuation subwords are excluded from the training loss, and predictions are mapped back to the original word positions for evaluation.

Tools and Libraries
The project uses the following tools and libraries:
- Python
- Keras
- TensorFlow/Keras-compatible workflow with the PyTorch backend used for the recorded experiments
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- pandas and NumPy
- scikit-learn
- seqeval
- Jupyter Notebook / Google Colab


Results
The models were evaluated on the test set using entity-level precision, recall, and F1-score. Entity-level evaluation requires the predicted entity span and entity type to match the reference annotation.





--------------------------------------------------------------------------------------------------------------------------------------------






Final training loss (4 d.p.):
0.2969

Total trainable parameters:
65

OpenCode model/provider:
Chatgpt 5

Reflection (max 250 words):
One thing OpenCode helped with:

OpenCode helped me understand the structure of two layer neural network using NumPy. It explained the forward pass, backpropagation, and how to update the weight and bias during training.

One thing it got wrong or you had to fix:

I did not had to fix anything in the code as it was provided directly. I understood that the network is only using NumPy library and while running the code I observed that the loss is consitently decreasing with increase in number of epochs. By the given plot I ensured that loss is inversely proportional to epochs.

How you verified the final notebook:

I ran every notebook cell without any errors. Also I tried changing the hidden size to check how the graph changes according to the data. When hidden size was 16 the total trainable parameters were 65, I changed hidden size to 32 the trainable parameters were 129 and epoch remained unchanged throughput the process. I saw slight difference in the plot.With all these changes I reviewed implementation to ensure it met all the assignment requirements.
