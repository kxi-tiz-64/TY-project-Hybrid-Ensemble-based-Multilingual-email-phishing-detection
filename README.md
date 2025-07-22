📧 Multilingual Phishing Email Detection System – Hybrid ML/DL Ensemble
📝 Introduction

This project implements a phishing email detection system using a hybrid ensemble of machine learning and deep learning models.
It is specifically designed to detect multilingual phishing attempts using multilingual BERT embeddings (mBERT).
The system is capable of identifying various types of phishing attacks such as deceptive phishing, BEC, clone phishing, whale phishing, malware phishing, and more.

🚀 Features

- Multilingual phishing detection using mBERT embeddings
- Hybrid Ensemble of ML (SVM, RF, LR) and DL (CNN, LSTM, MLP) models
- Flask web application for real-time email classification
- Hard voting with safety-aware fallback to soft voting
- Modular, production-ready file structure and API architecture

🛠️ Technologies Used

- Python 3.11
- PyTorch
- scikit-learn
- Transformers (HuggingFace)
- Flask (for API)
- TorchScript (for possible deployment optimizations)
- GitHub + Git for collaboration

📊 Dataset Description

The dataset is constructed from multiple sources including Enron (legitimate), TREC, CEAS, Nazario, Nigerian scams, etc.
Emails are vectorized using mBERT and then labeled as:
- 0 → Legitimate
- 1 → Phishing
The final training dataset is balanced and cleaned to improve model accuracy and robustness.

📈 Results Summary

| Model              | Accuracy | Precision | Recall | F1-Score |
|-------------------|----------|-----------|--------|----------|
| Logistic Regression | 94.2% | 94% | 94% | 94% |
| Random Forest       | 94.7% | 95% | 94% | 94% |
| SVM                 | 94.0% | 94% | 93% | 94% |
| LSTM                | 94.4% | 94% | 94% | 94% |
| CNN                 | 75.2% | 75% | 75% | 75% |
| MLP                 | 94.1% | 94% | 94% | 94% |

🌐 Deployment

The system is deployed using Flask and provides a simple form where the user inputs an email. The ensemble engine performs real-time classification.
Final predictions are made using hard voting with a fallback to soft voting only in conflicting edge cases.

⚙️ How to Use

1. Clone the repository.
2. Create a virtual environment and install dependencies from `requirements.txt`.
3. Place your trained models inside the `/models` folder.
4. Run `python app/main.py` to start the Flask server.
5. Open your browser and go to http://localhost:5000 to access the email input form.

🆘 Help Needed & Future Improvements

We welcome collaboration to make this project even stronger! Below are some “Good First Issues” — please label them on GitHub to help new contributors get started:
- Multilingual Dataset Expansion: Add more real-world phishing examples in languages like Hindi, Arabic, etc.
- Overfitting Mitigation: Improve generalization via data augmentation, cross-validation, or better regularization.
- Regularization & Early Stopping: Add dropout/L2 or tree pruning techniques.
- SMTP/IMAP Integration: Real-time email fetching from inboxes.
- Explainability (SHAP/LIME): Help users understand why a message was classified as phishing.
- Convert to ONNX/TorchScript: Speed up model inference for production.
- Use Lightweight Transformers: Try TinyBERT or DistilBERT for faster runtime.
- Adversarial Testing: Simulate manipulations like misspellings or URL obfuscation.
- CI/CD Pipeline: Use GitHub Actions + Docker to automate deployment.

