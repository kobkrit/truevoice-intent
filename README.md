# truevoice-intent
Intent Dataset from Customer Service Phone Calls Transcribed by TrueVoice's [Mari](http://www.truevoice.co.th/en/true-voice-mari/)

The `truevoice-intent` dataset was provided by [TrueVoice](http://www.truevoice.co.th/) through Khun Nattapote Kuslasayanon and Khun Suphavedee Trakulboon. The texts are transcribed from customer service phone calls to a mobile phone service provider. This dataset is a part of [pyThaiNLP](https://github.com/PyThaiNLP/) Thai text [classification-benchmarks](https://github.com/PyThaiNLP/classification-benchmarks). `texts` column contains raw texts and `texts_deepcut` column contains those segmented by [deepcut](https://github.com/rkcosmos/deepcut). For preliminary data exploration, see `exploration.ipynb`.

## Labeling Process

When the TrueVoice team performs the semantic tagging of each utterance (`texts` field of the dataset), they have a semantic intent extraction guildline for the taggers to do by asking them to look for:

1. What will be the intent of the caller in terms of action (verb) such as request, enquire, complain, and so on (the `action` field of the dataset)?

2. What will be the intent in term of objective such as phone issues, contact officers, balance inquiries and so on (the `object` field of the dataset)?

With these taggings, they then combined `action` and `object` tags together to identify the unique intent of the utterance. This way, it will be easy for the taggers to tag large amount of data in a structured way.

The `destination` field is where the customers will be routed to with a certain intent output such as agents with promotion skills, IVR self-service of bill payment and so on.

## Classification 

We provide 3 benchmarks for the 7-class multi-class classification of destination column in truevoice-intnet dataset: [fastText](fasttext.cc), LinearSVC and [ULMFit](https://github.com/cstorm125/thai2fit). In the transfer learning cases, we first finetune the embeddings using all data. The test set contains 20% of all data split by TrueVoice. The rest is split into 85/15 train-validation split randomly. Performance metrics are micro-averaged accuracy and F1 score. For more details, see `classification.ipynb`.

| model     | accuracy | micro-F1 |
|-----------|----------|----------|
| fastText  | 0.384116 | 0.384116 |
| LinearSVC | 0.807876 | 0.327565 |
| ULMFit    | 0.834981 | 0.834981 |
