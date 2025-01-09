# README

## 1. General Objective

This project aims to **train a Machine Learning model** that classifies products into a **new product hierarchy** (department, subdepartment, line, and subline) based on the **old hierarchy** and each product’s **description**. By leveraging text embeddings from a Spanish BERT model, the code automatically learns how to map the product information to the new classification.

## 2. Key Requirements

1. **Text Cleaning**  
   - Remove accents, punctuation, and convert to lowercase.
   - Retain only alphanumeric characters and spaces.
   - Remove extraneous spaces and normalize the text.

2. **Use the Old Hierarchy**  
   - Combine the old hierarchy columns (`DepartamentoTroncal`, `DepartamentoSAP`, `Linea`) with the product description to enrich the input.

3. **Efficient Model in Spanish**  
   - Use a Spanish BERT model (`dccuchile/bert-base-spanish-wwm-cased`) to capture the semantic meaning of the text.

4. **Multi-output Classification**  
   - Predict four columns (new department, subdepartment, line, and subline) simultaneously.

5. **Data Splitting**  
   - Divide the dataset into training (70%), validation (15%), and test (15%) sets, ensuring that all classes (in each column) appear at least once in the training set.

6. **Optional**: Model Saving and Excel Predictions  
   - Save the trained model to a file.
   - Load and use it later to classify new data from an Excel file.

## 3. Step-by-Step Explanation

Below is a summary of each relevant code section:

1. **Dependencies Installation**
   ```bash
   !pip install pandas numpy scikit-learn torch transformers openpyxl
