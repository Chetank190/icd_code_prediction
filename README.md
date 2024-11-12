# Medical Use-case:
## Extract the ICD codes from the clinical text.

### Overview

This project provides a pipeline for extracting medical conditions (diagnoses) from clinical text and matching them with the most relevant ICD-10-CM codes using advanced natural language processing (NLP) techniques. Leveraging Stanza for named entity recognition (NER) and Sentence Transformers for semantic similarity, this solution accurately predicts ICD codes based on clinical text descriptions.  

The approach integrates large language models (LLMs) and transformers to handle medical language, improving the ability to understand complex, contextually rich clinical information. By using LLMs and transformer-based embeddings, this pipeline can generate meaningful vector representations of clinical terms, allowing for effective similarity comparisons with ICD-10-CM descriptions.  


### Requirements

The code requires the following Python (Version: Python 3.10.11) libraries:

- pandas: For data handling.
- numpy: For numerical operations.
- stanza: For NER processing (especially for medical/clinical data).
- sentence-transformers: For creating sentence embeddings and similarity matching.


### Data Requirements
The program uses an ICD-10-CM codes dataset, which should be in a tab-separated text file (icd10cm_codes_2025.txt) with each line containing an ICD code and its corresponding description. Ensure the file is structured correctly and placed in the same directory as the script.  


### How the Pipeline Works
1. Entity Extraction with Stanza: The pipeline starts with named entity recognition (NER) using Stanza, which is configured to detect medical conditions (e.g., diagnoses, symptoms) in clinical text. Stanza’s NER is trained with clinical datasets (e.g., MIMIC, i2b2), making it particularly suitable for medical applications.  

2. Embedding Generation with Sentence Transformers: Each extracted medical condition is converted into a high-dimensional vector embedding using Sentence Transformers. Sentence transformers are built on the transformer architecture (BERT, MiniLM, etc.), enabling the model to generate semantically meaningful embeddings. These embeddings capture the context and meaning of medical conditions in a way that allows for accurate comparisons with ICD descriptions.  

3. Similarity Matching Using Embeddings: By calculating cosine similarity between the embeddings of clinical terms and ICD-10-CM descriptions, the pipeline identifies the closest ICD code matches. Cosine similarity measures the angle between vectors in high-dimensional space, providing a similarity score that represents the strength of the match.  

4. LLMs and Transformer Advantages: Using LLMs and transformer-based embeddings enables the pipeline to understand nuances in medical terminology. Transformers, with their self-attention mechanism, help the model grasp complex relationships between words and phrases in clinical text, resulting in more accurate and contextually aware ICD code matching.  


### Usage
1. Prepare the Data: Ensure icd10cm_codes_2025.txt is correctly formatted and available.  
2. Run the Script: Execute the script using Python:  
```
python script_name.py
```
3. View Results: The output will display extracted medical conditions and their best-matching ICD-10-CM codes with similarity scores.  


### Technical Background: LLMs and Transformers

- Large Language Models (LLMs): LLMs, such as BERT, GPT, and MiniLM, are pre-trained on vast text corpora and can generate contextually rich embeddings that understand language meaning at a deep level.
- Transformer Architecture: This project leverages the transformer architecture, which is well-suited for NLP tasks due to its self-attention mechanism. Self-attention allows the model to weigh the importance of each word in a sequence, enabling accurate representation of context and meaning.
- Embeddings: Generated embeddings are high-dimensional vector representations of text, capturing semantic relationships. Similar embeddings imply similar meanings, making them ideal for identifying the best ICD code matches.


### Conclusion
This pipeline leverages the power of transformers and large language models to perform accurate and efficient medical term extraction and ICD-10-CM code matching. By combining advanced NLP models with cosine similarity-based matching, the solution is both robust and adaptable to various clinical documentation tasks.