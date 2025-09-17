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
## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/SawyerAlston/ML-vs-DL-Sentiment-Classification.git
cd ML-vs-DL-Sentiment-Classification
```
### 2. Install Dependencies
This project uses a variety of libraries, for compatibility please see the [requirements.txt](../main/requirements.txt) file.
```bash
pip install -r requirements.txt
```
### 3. Reduce Dataset (performance optional)
Replace cell 3 of `Data Preprocessing` section of the [notebook](../main/Notebook(s)/ML_vs_DL_classification_comparison.ipynb) with the following updated code:
```python
from sklearn.model_selection import train_test_split

print (df["sentiment"].value_counts())
df = df.drop_duplicates(subset="text")
print (df["sentiment"].value_counts())
df = df.sample(frac=0.1, random_state=1)

# Split into train&val (90%) and the test set (10%)
train_val_texts, test_texts, train_val_labels, test_labels = train_test_split(df["text"].values, df["sentiment"].values, test_size=0.1, random_state=1)

# Now split train&val into train (90% of 90% --> 81%) and val (10% of 90% --> 9%)
train_texts, val_texts, train_labels, val_labels = train_test_split(train_val_texts, train_val_labels, test_size=0.2, random_state=1)

print(f"train split: {train_texts.shape[0]}")
print(f"validation split: {val_texts.shape[0]}")
print(f"test split: {test_texts.shape[0]}")
```
### 4. Explore the Notebook!
Feel free to check all around, tinker, modify, or play/learn from the project however you would like :)

## 📊 Benchmarking Plots:
#### ROC Curve:
![ROC Curve Plot](../main/Plots/ROC_graph.png)
#### Confusion Matrices:
![Confusion Matrices](../main/Plots/ConfusionMatrices.png)
#### Train Times:
![Train Time](../main/Plots/TrainTimes.png)
#### Inference Times:
![Inference Time](../main/Plots/InfTimes.png)

## 📁 Repo Structure
```bash
├── notebook(s)
│   ├── ML_vs_DL_classification_comparison.ipynb.ipynb
├── plots
    ├── (various model benchmark images)
├── README.md
├── requirements.txt
```

## 📝License
This project is licensed under the [MIT License](LICENSE).
