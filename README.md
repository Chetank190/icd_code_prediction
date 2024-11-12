# Medical Use-case:
## Extract the ICD codes from the clinical text.

### Overview

This code provides a pipeline to extract medical conditions (diagnoses) from clinical text and match them with the most relevant ICD-10-CM codes using natural language processing (NLP) techniques. The program combines the Stanza library for named entity recognition (NER) with Sentence Transformers for semantic similarity matching, allowing for accurate ICD code predictions based on clinical text descriptions.  


### Requirements

The code requires the following Python (Version: Python 3.10.11) libraries:

- pandas: For data handling.
- numpy: For numerical operations.
- stanza: For NER processing (especially for medical/clinical data).
- sentence-transformers: For creating sentence embeddings and similarity matching.


### Data Requirements
The program uses an ICD-10-CM codes dataset, which should be in a tab-separated text file (icd10cm_codes_2025.txt) with each line containing an ICD code and its corresponding description. Ensure the file is structured correctly and placed in the same directory as the script.  


### Usage
1. Prepare the Data: Ensure icd10cm_codes_2025.txt is correctly formatted and available.  
2. Run the Script: Execute the script using Python:  
```
python script_name.py
```
3. View Results: The output will display extracted medical conditions and their best-matching ICD-10-CM codes with similarity scores.  


