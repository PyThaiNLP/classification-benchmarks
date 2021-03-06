# Thai Text Classification Benchmarks

We provide 4 datasets for Thai text classification in different styles, objectives, and number of labels. We also created some preliminary benchmarks using [fastText](https://fasttext.cc), linear models (linearSVC and logistic regression), and [thai2fit](https://github.com/cstorm125/thai2fit)'s implementation of [ULMFit](https://arxiv.org/abs/1801.06146).

`prachathai-67k`, `truevoice-intent`, and all code in this repository are released under Apache License 2.0 by [pyThaiNLP](https://github.com/PyThaiNLP/). `wisesight-sentiment` is released to public domain, using Creative Commons Zero v1.0 Universal license, by [Wisesight](https://wisesight.com/). `wongnai-corpus` is released under GNU Lesser General Public License v3.0 by [Wongnai](https://www.wongnai.com/).

## Dataset Description

| Datasets                                                    | Style    | Objective | Labels | Size | 
|-------------------------------------------------------------|----------|-----------|--------|------|
| [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k): body_text | Formal (online newspapers), News   | Topic     | 12    | 67k  |
| [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): destination  | Informal (call center transcription), Customer service | Intent    | 7    | 16k  |
| [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment)  | Informal (social media), Conversation/opinion | Sentiment | 4   | 28k  | 
| [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) | Informal (review site), Restuarant review | Sentiment | 5      | 40k  |(https://github.com/cstorm125/thai2fit/blob/master/notebook/lstm_wongnai.ipynb)               |

## [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k): body_text

We benchmark [prachathai-67k](https://github.com/PyThaiNLP/prachathai-67k) by using `body_text` as text features and construct a 12-label multi-label classification. The performance is measured by macro-averaged accuracy and F1 score. Codes can be run to  confirm performance at this [notebook](https://github.com/PyThaiNLP/prachathai-67k/blob/master/classification.ipynb). We also provide performance metrics by class in the notebook.

| model     | macro-accuracy | macro-F1 |
|-----------|----------------|----------|
| fastText  | 0.9302         | 0.5529   |
| LinearSVC | 0.513277       | 0.552801 |
| **ULMFit**    | **0.948737**       | **0.744875**	 |
| [USE](https://tfhub.dev/google/universal-sentence-encoder-multilingual/3)    | 0.856091    | 0.696172	 |

## [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent): destination

We benchmark [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent) by using `destination` as target and construct a 7-class multi-class classification. The performance is measured by micro-averaged and macro-averaged accuracy and F1 score. Codes can be run to  confirm performance at this [notebook](https://github.com/PyThaiNLP/truevoice-intent/blob/master/classification.ipynb). We also provide performance metrics by class in the notebook.

| model     | macro-accuracy | micro-accuracy | macro-F1       | micro-F1   |
|-----------|----------------|----------------|----------------|------------|
| **LinearSVC** | **0.957806**       | **0.95747712**     |       **0.869411** | **0.85116993** |
| ULMFit    | 0.955066       | 0.84273111     | 0.852149       | 0.84273111 |
| [BERT](https://github.com/KongpolC/thai_intent_classification_using_bert) | 0.8921 | 0.85 | 0.87 | 0.85 |
| USE    | 0.943559       | 0.94355855    | 0.787686       | 0.802455 |

## [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment)

Performance of [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment) is based on the test set of [WISESIGHT Sentiment Analysis](https://www.kaggle.com/account/login?ReturnUrl=/t/0b22205d288143bb8672527b04690a97). Codes can be run to confirm performance at this [notebook](https://github.com/PyThaiNLP/wisesight-sentiment/blob/master/kaggle-competition/competition.ipynb). 

**Disclaimer** Note that the labels are obtained manually and are prone to errors so if you are planning to apply the models in the benchmark for real-world applications, be sure to benchmark it with **your own dataset**.

| Model               | Public Accuracy | Private Accuracy |
|---------------------|-----------------|------------------|
| Logistic Regression | 0.72781         | 0.7499           |
| FastText            | 0.63144         | 0.6131           |
| ULMFit              | 0.71259         | 0.74194          |
| ULMFit Semi-supervised    | 0.73119     | 0.75859      |
| **[ULMFit Semi-supervised Repeated One Time](https://github.com/PyThaiNLP/wisesight-sentiment/blob/master/competition.ipynb)**    | **0.73372**     | **0.75968**      |
| [USE](https://tfhub.dev/google/universal-sentence-encoder-multilingual/3)    | 0.63987*   |
* Done after competition with a test set that was cleaned from 3946 rows to 2674 rows


## [wongnai-corpus](https://github.com/wongnai/wongnai-corpus)

Performance of [wongnai-corpus](https://github.com/wongnai/wongnai-corpus) is based on the test set of [Wongnai Challenge: Review Rating Prediction](https://www.kaggle.com/account/login?ReturnUrl=%2Ft%2F5db04b4da3264e1091d83463b110153b). Codes can be run to confirm performance at this [notebook](https://github.com/cstorm125/thai2fit/blob/master/wongnai_cls/classification.ipynb).

| Model     | Public Micro-F1 | Private Micro-F1 | 
|-----------|-----------------|------------------|
| [**ULMFit Knight**](https://www.facebook.com/photo.php?fbid=10215789035573261&set=pcb.795048317543327&type=3&theater&ifg=1) | **0.61109** | **0.62580** |
| [ULMFit](https://github.com/cstorm125/thai2fit/) | 0.59313          | 0.60322           |
| fastText | 0.5145          | 0.5109           |
| LinearSVC | 0.5022          | 0.4976           |
| Kaggle Score | 0.59139          | 0.58139          |
| [BERT](https://github.com/ThAIKeras/bert) | 0.56612 | 0.57057 |
| [USE](https://tfhub.dev/google/universal-sentence-encoder-multilingual/3) | 0.42688 | 0.41031 |

## BibTeX
```
@software{cstorm125_2020_3852912,
  author       = {cstorm125 and
                  lukkiddd},
  title        = {PyThaiNLP/classification-benchmarks: v0.1-alpha},
  month        = may,
  year         = 2020,
  publisher    = {Zenodo},
  version      = {v0.1-alpha},
  doi          = {10.5281/zenodo.3852912},
  url          = {https://doi.org/10.5281/zenodo.3852912}
}
```

## Acknowledgements

* [Ekapol Chuangsuwanich](https://github.com/ekapolc) for pioneering [wongnai-corpus](https://github.com/wongnai/wongnai-corpus), [wisesight-sentiment](https://github.com/PyThaiNLP/wisesight-sentiment), and [truevoice-intent](https://github.com/PyThaiNLP/truevoice-intent) for his [NLP classes](https://github.com/ekapolc/nlp_course) at Chulalongkorn University. 

* [@lukkiddd](https://github.com/lukkiddd) for data exploration and linear model codes.
