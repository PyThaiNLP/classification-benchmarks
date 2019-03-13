# classification-benchmarks
Thai Text Classification Benchmarks

| Datasets                                                    | Style    | Objective | Labels | Size | 
|-------------------------------------------------------------|----------|-----------|--------|------|
| [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) | Informal | Sentiment | 5      | 40k  |(https://github.com/cstorm125/thai2fit/blob/master/notebook/lstm_wongnai.ipynb)               |
| [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k): body_text | Formal   | Topic     | 12    | 67k  |
| [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment)  | Informal | Sentiment | 4   | 28k  | 
| [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): action  | Informal | Intent    | 8    | 16k  |
| [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): object  | Informal | Intent    | 26    | 16k  |
| [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): destination  | Informal | Intent    | 7    | 16k  |

## [wongnai-corpus](https://github.com/wongnai/wongnai-corpus)

Performance of [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) is based on the test set of [Wongnai Challenge: Review Rating Prediction](https://www.kaggle.com/c/wongnai-challenge-review-rating-prediction/). Codes can be run to confirm performance at this [notebook](https://github.com/cstorm125/thai2fit/blob/master/wongnai_cls/classification.ipynb).

| model     | Public Micro-F1 | Private Micro-F1 | 
|-----------|-----------------|------------------|
| [**ULMFit**](https://github.com/cstorm125/thai2fit/) | **0.59313**          | **0.60322**           |
| fastText | 0.5145          | 0.5109           |
| LinearSVC | 0.5022          | 0.4976           |
| Kaggle Score | 0.59139          | 0.58139          |
| [BERT](https://github.com/ThAIKeras/bert) | 0.56612 | 0.57057 |

## [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k): body_text

## [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment)

Performance of [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment) is based on the test set of [WISESIGHT Sentiment Analysis](https://www.kaggle.com/c/wisesight-sentiment/). Codes can be run to confirm performance at this [notebook](https://github.com/PyThaiNLP/wisesight-sentiment/blob/master/competition.ipynb). 

**Disclaimer** Note that the labels are obtained manually and are prone to errors so if you are planning to apply the models in the benchmark for real-world applications, be sure to benchmark it with **your own dataset**.

| Model               | Public Accuracy | Private Accuracy |
|---------------------|-----------------|------------------|
| Logistic Regression | 0.72781         | 0.7499           |
| FastText            | 0.63144         | 0.6131           |
| ULMFit              | 0.71259         | 0.74194          |
| ULMFit Semi-supervised    | 0.73119     | 0.75859      |
| **[ULMFit Semi-supervised Repeated One Time](https://github.com/PyThaiNLP/wisesight-sentiment/blob/master/competition.ipynb)**    | **0.73372**     | **0.75968**      |

## [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): action

## [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): object

## [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): destination
