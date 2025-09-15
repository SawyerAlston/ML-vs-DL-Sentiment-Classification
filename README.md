# In-Depth ML vs. DL Sentiment Classification Walkthrough and Comparison

**In making this project I aimed to accomplish two things:**
- To compare and contrast these two architectures seeking insight into how they work and how each approach performs against the other
- To outline all the building and benchmarking processes in a comprehensive, consolidated Juptyer notebook

## 📄 Notebook Outline
```txt
├── #1. Data Preprocessing
│     ├── Load and inspect dataset
│     ├── Split data into train, val, and test sets
│  
├── #2. ML (Logistic Regression) Approach
│     ├── Extract features with TF-IDF
│     ├── Train LR model
│     ├── Evaluate model on validation and test set
│     ├── Check performance
│  
├── #3. DL (LSTM) Approach
│     ├── Tokenize and vectorize features
│     ├── Create dataset and dataloaders
│     ├── Build and train LSTM model
│     ├── Test on validation and test sets
│  
├── #4. Comparisons and Conclusions
│     ├── Analyze classification reports
│     ├── Create, compare, and analyze ROC curves
│     ├── Analyze confusion matrices
│     ├── Check error overlap
│     ├── Analyze and compare model training and inferencing times
│     ├── Compare model memory usage
│     ├── Observe and analyze model sizes

```

## 📁 Repo Structure
```bash
├── notebook(s)
│   ├── twitter_sentiment_analysis.ipynb
├── plots
    ├── (various model benchmark images)
├── README.md
├── requirements.txt
```