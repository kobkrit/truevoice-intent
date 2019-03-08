# truevoice-intent
Intent Dataset from Customer Service Phone Calls Transcribed by TrueVoice's [Mari](http://www.truevoice.co.th/en/true-voice-mari/)

The `truevoice-intent` dataset was provided by [TrueVoice](http://www.truevoice.co.th/) through Nattapote Kuslasayanon. The texts are transcribed from customer service phone calls to a mobile phone service provider. This dataset is a part of [pyThaiNLP](https://github.com/PyThaiNLP/) Thai text [classification-benchmarks](https://github.com/PyThaiNLP/classification-benchmarks). `texts` column contains raw texts and `texts_deepcut` column contains those segmented by [deepcut](https://github.com/rkcosmos/deepcut).

The benchmark features a set of **three multi-class classification tasks** for `action`, `object`, and `destination` of all the calls. Performance metrics are macro- and micro-averaged accuracy, F1 score, precision and recall.

For preliminary data exploration, see `exploration.ipynb`. For classification benchmark, see `classification.ipynb`.