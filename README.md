# classification-benchmarks
Thai Text Classification Benchmarks

| Datasets                                                    | Style    | Objective | Labels | Size | 
|-------------------------------------------------------------|----------|-----------|--------|------|
| [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) | Informal | Sentiment | 5      | 40k  |(https://github.com/cstorm125/thai2fit/blob/master/notebook/lstm_wongnai.ipynb)               |
| [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k) | Formal   | Topic     | 12    | 67k  |
| [wisesight-sentiment]()                                               | Informal | Sentiment | 3      | 10k  | 
| [truevoice]()                                                   | Informal | Intent    | TBD    | 16k  |

## [wongnai-corpus](https://github.com/wongnai/wongnai-corpus)

Performance of [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) is based on the test set of [Wongnai Challenge: Review Rating Prediction](https://www.kaggle.com/c/wongnai-challenge-review-rating-prediction/). Codes can be run to confirm performance at this [notebook](https://github.com/cstorm125/thai2fit/blob/master/wongnai_cls/classification.ipynb).

| model     | micro_f1_public | micro_f1_private | 
|-----------|-----------------|------------------|
| [**ULMFit**](https://github.com/cstorm125/thai2fit/) | **0.59313**          | **0.60322**           |
| fastText | 0.5145          | 0.5109           |
| LinearSVC | 0.5022          | 0.4976           |
| Kaggle Score | 0.59139          | 0.58139          |
| [BERT](https://github.com/ThAIKeras/bert) | 0.56612 | 0.57057 |
