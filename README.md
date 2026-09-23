Fraud Detection with Large Language Models
Project Overview
This project explores the application of Large Language Models (LLMs) for fraud detection by analyzing transaction details. We compare the performance of a base LLM (Qwen2.5-1.5B-Instruct) against a fine-tuned version of the same model on a fraud detection dataset.

Models Used
Base Model: Qwen/Qwen2.5-1.5B-Instruct
Fine-tuned Model: angeshwar/fraud-detector (a fine-tuned version of Qwen2.5-1.5B-Instruct)
Dataset
The dataset used is the "Cifer Fraud Detection Dataset AF" from Hugging Face (CiferAI/Cifer-Fraud-Detection-Dataset-AF). A balanced test set of 100 transactions (50 fraud, 50 non-fraud) was created for evaluation.

Methodology
Data Loading and Preparation: The dataset was loaded using the datasets library. A test set was constructed with an equal number of fraudulent and non-fraudulent transactions.
Prompt Engineering: A structured prompt was created for each transaction, detailing various attributes like type, amount, and account balances before and after the transaction.
Prediction: Both the base and fine-tuned LLMs were prompted to classify transactions as "HIGH" (fraud risk) or "LOW" (low fraud risk).
Evaluation: The predictions from both models were compared against actual labels using standard classification metrics: Accuracy, Precision, Recall, and F1-Score.
Results
The evaluation compared the base model's ability to detect fraud versus the fine-tuned model's performance. The results are as follows:

Metric	Base Model	Fine-tuned
Accuracy	48%	52%
Precision	25%	52%
Recall	2%	58%
F1 Score	4%	55%
Interpretation: The fine-tuned model significantly outperforms the base model across all metrics, especially in Precision, Recall, and F1-Score, indicating its enhanced ability to correctly identify fraudulent transactions while minimizing false positives.

Setup and Usage
To run this project, you need to:

Install the required libraries:
!pip install -q --upgrade torchao transformers peft datasets scikit-learn
Load the models from Hugging Face:
The fine-tuned model: angeshwar/fraud-detector
The base model: Qwen/Qwen2.5-1.5B-Instruct
Load the dataset:
from datasets import load_dataset
dataset = load_dataset("CiferAI/Cifer-Fraud-Detection-Dataset-AF", split="train")
Execute the cells sequentially to prepare data, run predictions, and evaluate model performance.
