# UkrMTEB
Accompanying materials for the "General-purpose text embeddings learning for Ukrainian language" paper.

This repository contains the full code and data to reproduce all experiments. 
Training and evaluation code is available in the `UkrTEB.ipynb` notebook (from getting the training data to evaluating the model on the benchmarks introduced in the paper)
The notebook if fully self-contained and can be run in Google Colab as is.

**Please consider citing the paper if you find it useful!**

Multilingual models used as baselines in this study:
```python
model_names = [
    "intfloat/multilingual-e5-base",
    "sentence-transformers/LaBSE",
    "distiluse-base-multilingual-cased-v2",
]
```
English-only models used as teacher models in the study:
```python
model_names = [
    "intfloat/e5-base-v2",
    "BAAI/bge-base-en-v1.5",
    "Alibaba-NLP/gte-base-en-v1.5",
    "sentence-transformers/all-mpnet-base-v2"
]
```
New models trained in this study:
```python
[
    "maiia-bocharova/ukr_sentence_gte_cos_sim",
    "maiia-bocharova/ukr_sentence_e5_cos_sim",
    "maiia-bocharova/ukr_sentence_bge_cos_sim",
    "maiia-bocharova/ukr_sentence_mpnet_cos_sim"
    "maiia-bocharova/ukr_sentence_mpnet_cos_sim",
    "maiia-bocharova/ukr_sentence_mpnet_mse",
]
```
**If you want to use the model for your unkrainian language embedding task - please use "maiia-bocharova/ukr_sentence_mpnet_cos_sim"**

To download model:
```
from sentence_transformers import SentenceTransformer
model = SentenceTransformer(
    model_name,
    device="cuda",
    trust_remote_code=True # only for 
)
```
New benchmark datasets
```python
dataset_names = [
    "maiia-bocharova/ukr_teb-books_blobs",

    "maiia-bocharova/ukr_teb-forum_sents_s2s",
    "maiia-bocharova/ukr_teb-forum_sents_p2p",

    "maiia-bocharova/ukr_teb-petitions_s2s",
    "maiia-bocharova/ukr_teb-petitions_p2p",

    "maiia-bocharova/ukr_teb-law_drafts",

    "maiia-bocharova/ukr_teb-news_s2s",
    "maiia-bocharova/ukr_teb-news_p2p",
]
```

To load the dataset from `huggingface_hub` run:
```python
import datasets
dataset = datasets.load_dataset(dataset_name)
```
Alternatively data is available in `CSV` format under `/data` directory


