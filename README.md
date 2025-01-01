# Cache-Augmented Generation (CAG)

A demo of Cache-Augmented Generation (CAG) using Mistral-7B. 

CAG preloads relevant knowledge into a language model's context, allowing for faster and more efficient question-answering without real-time document retrieval.

## Overview

The notebook `cag_demo.ipynb` showcases the core steps of CAG:

1. Loading the Mistral model and tokenizer
2. Reading a local `document.txt` file containing information about you (For this case, me / Ronan Takizawa)
3. Preloading that knowledge into the model's context using a `DynamicCache`
4. Answering user queries by referencing the cached knowledge, without real-time retrieval

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

3. Create a `document.txt` file in the project directory, containing the knowledge you want to preload

## Usage

1. Open the `cag_demo.ipynb` notebook in Jupyter, VS Code, or Google Colab.

2. Run the cells in order. The notebook will:
- Load the Mistral model and tokenizer
- Read `document.txt` and preload its content into a `DynamicCache` 
- Ask two example questions about Ronan Takizawa, answering them using the cached knowledge

3. Observe the model's responses, which are generated without real-time document retrieval.

## Customization

To use your own knowledge base:

1. Replace the content of `document.txt` with your desired information.
2. Adjust the example questions in the notebook to match your knowledge domain.
