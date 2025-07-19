# 🧹 Part 2: Cleaning the Survey Data in Python

## 1. Introduction

**Objective:**  
Prepare clean data from the _Multi-Banking Behaviour Survey (Responses).xlsx_ file for analysis by:

- Removing unnecessary columns  
- Renaming for consistency  
- Handling missing values  
- Saving the clean version for further use  

---

## 2. Import Libraries and Load Dataset

```python
import pandas as pd

# Load the dataset
df = pd.read_excel("Multi-Banking Behaviour Survey (Responses).xlsx")

# View initial structure
df.head()
```


## 3. Drop Irrelevant or Open-Ended Columns
**Reason:**  
These columns include free-text or multi-response inputs not used in analysis or visualization.

**Columns to Drop:**
- Name
- Which banks do you use?
- Which is your primary bank?
- What type of accounts do you have?
- How often do you use your secondary bank?
- Why do you use your secondary bank? (Select all that apply)
- What would make you stick to just one bank? (SELECT ALL THAT APPLY)
- If banks were smartphones, your primary bank is a(n) ______ because it’s ______.

```python
# Clean up column names first (strip spaces and \n)
df.columns = df.columns.str.strip()

# Define keywords from open-ended columns to match dynamically
drop_keywords = [
    "Name",
    "Which banks do you use",
    "Which is your primary bank",
    "What type of accounts do you have",
    "How often do you use your secondary bank",
    "Why do you use your secondary bank",
    "What would make you stick to just one bank? (SELECT ALL THAT APPLY)",
    "If banks were smartphones, your primary bank is a(n) ______ because it’s ______. (CHOOSE ONE)"
]

# Drop columns if they contain any of the keywords above
cols_to_drop = [col for col in df.columns for keyword in drop_keywords if keyword.lower() in col.lower()]
df.drop(columns=cols_to_drop, inplace=True)

# Preview to confirm
print("Dropped columns:")
print(cols_to_drop)

```

## 4. Rename Columns for Clarity
**Why?**  
Standardized short names improve readability and coding ease.

```python
df.rename(columns={
    'Age group': 'age',
    'Income Range': 'income',
    'Location': 'location',
    'Employment type': 'employment',
    'How many bank accounts do you have? \n': 'num_accounts'
}, inplace=True)
```

## 5. Handle Missing Values
**Approach:**  
Drop rows with too many missing responses (you can set a threshold).

```python
# Drop rows with more than 5 missing responses
df_cleaned = df.dropna(thresh=len(df.columns) - 5).reset_index(drop=True)
```

## 6. Save the Cleaned Dataset
```python
df_cleaned.to_excel("Cleaned_Banking_Survey.xlsx", index=False)
print("✅ Cleaned dataset saved as Cleaned_Banking_Survey.xlsx")
```

## 7. Output Preview (Optional)
```python
df_cleaned.head()
```

---

Next up: [View Part 3](part3_spss_output/README.md) – SPSS Outputs & Interpretation.

---
