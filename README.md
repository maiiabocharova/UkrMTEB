# UkrMTEB
Dataset introduced in the paper "General-purpose text embeddings learning for Ukrainian language"

Models used in this study:
```python
model_names = [
    "intfloat/multilingual-e5-base",
    "sentence-transformers/LaBSE",
    "distiluse-base-multilingual-cased-v2",
    
    "maiia-bocharova/ukr_sentence_gte_cos_sim",
    "maiia-bocharova/ukr_sentence_e5_cos_sim",
    "maiia-bocharova/ukr_sentence_bge_cos_sim",
    "maiia-bocharova/ukr_sentence_mpnet_cos_sim",
    "maiia-bocharova/ukr_sentence_mpnet_mse",

]
```

To download model
```
from sentence_transformers import SentenceTransformer
model = SentenceTransformer(
    model_name,
    device="cuda",
    trust_remote_code=True
)
```
Available daasets
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

To load the dataset from hub run:
```python
import datasets
dataset = datasets.load_dataset(dataset_name)
```
Alternatively data is available in `CSV` format under `/data` directory

Training and evaluation code are available in the `UkrTEB.ipynb` notebook
