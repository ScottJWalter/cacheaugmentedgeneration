# A Demo of Cache-Augmented Generation (CAG) Using an Open-Source LLM
<img width="350" alt="Screenshot 2025-05-22 at 11 48 00 PM" src="https://github.com/user-attachments/assets/b362af23-1c5a-4945-903d-36035ce138ca" />

This is a simple demo of Cache-Augmented Generation (CAG) using an Open-Source LLM. 

CAG preloads relevant knowledge into a language model's context, allowing for faster and more efficient question-answering without real-time document retrieval.
This project demonstrates a simple implementation of CAG and its 76% token reduction usage compared to RAG. 

Article: https://medium.com/@ronantech/cache-augmented-generation-cag-in-llms-a-step-by-step-tutorial-6ac35d415eec

Google Colab: https://colab.research.google.com/drive/1-0eKIu6cGAZ47ROKQaF6EU-mHtvJBILV?usp=sharing

This project was described as a reliable example of CAG in 2 Reddit threads:
https://www.reddit.com/r/LangChain/comments/1jh759u/cache_augmented_generation/
https://www.reddit.com/r/Rag/comments/1i5l2ot/dont_do_rag_its_time_for_cag/


## Overview

The notebook `cag_demo.ipynb` showcases the core steps of CAG:

1. Loading the Mistral model and tokenizer
2. Preloading that knowledge into the model's context using a `DynamicCache`
3. Answering user queries by referencing the cached knowledge, without real-time retrieval
4. Saving the context cache on disk, then reloading it for another chat session

## Setup

### Prerequisites

- Python 3.7+
- PyTorch 1.13+  
- Transformers 4.28+
- Hugging Face account with access to the `mistralai/Mistral-7B-Instruct-v0.1` model

### Installation

1. Clone this repository:

```
git clone https://github.com/yourusername/cache-augmented-generation.git
cd cache-augmented-generation
```

2. Install the required packages:
```
pip install torch transformers
```

## Usage

1. Open the `cagdemo.ipynb` notebook in Jupyter, VS Code, or Google Colab.

2. Run the cells in order. The notebook will:
- Load the Mistral model and tokenizer
- Read `document.txt` and preload its content into a `DynamicCache` 
- Ask two example questions about Ronan Takizawa, answering them using the cached knowledge

3. Observe the model's responses, which are generated without real-time document retrieval.

## Customization

To use your own knowledge base:

1. Replace the content of `document.txt` with your desired information.
2. Adjust the example questions in the notebook to match your knowledge domain.
