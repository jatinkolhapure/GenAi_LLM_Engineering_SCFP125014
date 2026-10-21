# Text Classification Using RNN and LSTM

This notebook contains two lab activities that use recurrent neural networks to classify IMDb movie reviews as **positive** or **negative**. Activity 1 implements a bidirectional vanilla RNN; Activity 2 implements a bidirectional LSTM and compares its results with the RNN.

**Notebook:** `RNN_LSTM_Text_Classification.ipynb`

## Activities

### Activity 1 — Sentiment Classification Using RNN

**Objective:** Build and evaluate an RNN-based sentiment classifier for movie reviews.

**Implementation**
- Load the IMDb CSV dataset and select 10,000 reviews.
- Keep the `review` and `sentiment` columns; map positive to `1` and negative to `0`.
- Split the data into 80% training and 20% testing sets using stratification.
- Tokenize reviews with `tiktoken` using the `cl100k_base` encoding.
- Pad or truncate every review to 200 tokens.
- Convert the token sequences and labels to PyTorch tensors.
- Train a bidirectional RNN classifier and evaluate it on the held-out test set.
- Run predictions on three manually written sample reviews.

**Model configuration**

| Setting | Value |
|---|---|
| Embedding dimension | 128 |
| Recurrent layer | Bidirectional `nn.RNN` |
| Hidden size | 96 per direction |
| Classifier output | 1 logit |
| Loss function | `BCEWithLogitsLoss` |
| Optimizer | Adam |
| Learning rate | 0.0005 |
| Weight decay | 0.00001 |
| Batch size | 64 |
| Epochs | 12 |
| Maximum sequence length | 200 tokens |

**Recorded result:** The saved notebook output reports **66.95% test accuracy** (1,339 correct predictions from 2,000 test reviews). The final recorded training loss is `0.1950`.

### Activity 2 — RNN vs LSTM for Sentiment Classification

**Objective:** Compare a bidirectional RNN with a bidirectional LSTM on the same sentiment-classification task.

The LSTM activity reuses the same sampled dataset, train/test split, tokenization, sequence length, embedding size, hidden size, loss, optimizer settings, batch size, and number of epochs. The recurrent layer is changed from `nn.RNN` to `nn.LSTM`.

**Model difference**
- **RNN:** processes the sequence using a standard recurrent layer.
- **LSTM:** uses a cell state and gating mechanisms designed to help retain useful information across longer sequences.

**Recorded comparison**

| Metric | Bidirectional RNN | Bidirectional LSTM |
|---|---:|---:|
| Test samples | 2,000 | 2,000 |
| Correct predictions | 1,339 | 1,499 |
| Test accuracy | 66.95% | 74.95% |
| Final training loss | 0.1950 | 0.0978 |

In this saved run, the LSTM test accuracy is **8.00 percentage points higher** than the RNN test accuracy. This describes the recorded experiment; results may differ with other data samples, environments, or training runs.

The notebook also compares predictions for three manually written reviews. In the saved output, both models predict the same sentiment for all three examples.

## Requirements

- Python
- pandas
- NumPy
- scikit-learn
- PyTorch
- `tiktoken`
- IMDb review CSV with `review` and `sentiment` columns

## How to Run

The notebook is designed for Google Colab and uses `files.upload()` to select the dataset.

1. Open `RNN_LSTM_Text_Classification.ipynb` in Google Colab.
2. Run the cells in order.
3. Upload the IMDb CSV file when prompted.
4. Allow the notebook to prepare the data, train both models, and print the evaluation results.

The notebook installs `tiktoken` in its first code cell. It automatically uses a CUDA device if available; otherwise, it uses the CPU.

## Notes

- The notebook's saved results use a 10,000-review sample from a CSV that reported 50,000 rows and two columns.
- Reported accuracy and loss values above are copied from the notebook's saved outputs; they are not a new training run.
- The notebook contains both activities in one file, so this README documents them as separate sections while sharing the common setup instructions.
