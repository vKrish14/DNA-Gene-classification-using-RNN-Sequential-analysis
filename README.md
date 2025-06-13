🧬 16S rRNA Sequence Classification Using BiLSTM with Attention

This repository presents a deep learning pipeline for classifying 16S rRNA gene sequences using a Bidirectional LSTM architecture enhanced with self-attention mechanisms. The model is designed to handle variable-length DNA sequences and class imbalance, with robust performance evaluation including confusion matrix visualization and cross-validation.
📄 Dataset Requirements

The model expects a CSV file named 16s_sequences.csv with the following structure:
sequence	label
ACGTTCAGT...	Bacillus
TTGACCTTA...	E. coli

    sequence: Raw 16S rRNA gene sequence (character string of A, C, G, T, etc.)

    label: Target class (e.g., bacterial species)

⚙️ Project Features

    Character-level encoding for DNA sequences

    Deep Bidirectional LSTM layers to capture context

    Attention mechanism for improved feature representation

    Class imbalance mitigation using computed class weights

    Evaluation using:

        Accuracy

        Confusion matrix (visualized via Seaborn)

        Classification report (Precision, Recall, F1-score)

    Optional K-Fold cross-validation

🧠 Model Architecture

Input Sequence
     ↓
Embedding Layer (char-level)
     ↓
Bidirectional LSTM (256 units, return_sequences=True)
     ↓
Self-Attention Layer
     ↓
Dropout (0.4)
     ↓
Bidirectional LSTM (128 units)
     ↓
Dense Layer (128 units, ReLU)
     ↓
Dropout (0.3)
     ↓
Softmax Output Layer (num_classes)

🚀 How to Run
1. Environment Setup

Ensure you have the following libraries installed:

pip install tensorflow pandas numpy seaborn scikit-learn matplotlib

2. Upload Dataset

Upload your 16s_sequences.csv file to your working directory (e.g., Google Colab or local path).
3. Execute Script

Run the script or notebook. It will:

    Preprocess and encode the sequences

    Train the BiLSTM-Attention model with early stopping

    Evaluate and plot performance metrics

    Optionally perform 5-fold cross-validation

📊 Output Metrics

Example evaluation output:

Final Test Accuracy: 92.15%

Classification Report:
              precision    recall  f1-score   support

    Bacillus       0.91      0.93      0.92        50
     E. coli       0.94      0.90      0.92        48

Confusion Matrix:
                 Predicted
             ┌───────────────┐
             │  Bacillus  E. coli │
    Bacillus │     46        4     │
     E. coli │      5        43    │
             └───────────────┘

📁 Directory Structure

├── 16s_sequences.csv       # Input dataset
├── main_model.py           # Deep learning pipeline script
├── README.md               # Project documentation

🔄 Cross-Validation

The script includes an optional 5-fold cross-validation step at the end, which evaluates model robustness across different data splits.
🧪 Future Enhancements

    Incorporation of domain-specific embeddings (e.g., k-mer embeddings)

    Integration with pre-trained nucleotide models (e.g., DNABERT)

    Multi-task learning for taxonomic classification at multiple levels (genus, species, etc.)

    Model interpretability using attention weights


    For questions or collaborations, feel free to reach out via GitHub or email.
