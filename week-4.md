# Week 4

### Lexicon

* Number of single character: 12318
* Number of total words \(including single characters\): around 60000

It contains two parts. One is from the original lexicon from DSP-Lab that has around 40000 distinct words. The other one, `cc-canto` , is from [cccanto.org](/cccanto.org), an open-source Cantonese dictionary that contains around distinct 22000 words. `cc-canto` contains some Cantonese colloquialism, such as `一嚿嘢` and `煮飯仔` , which may be helpful in our task.

### Text Processing

* Deleting English words. \(doubting\)
* Convert numbers into Cantonese pronunciation. For example, 123 to "一百二十三". \(Not done\)
* Delete useless punctuation, like brackets, quotation marks. \(Needs further improvement, as Chinese punctuation has so many formats\)
* Pruning?

### Perplexity

Perplexity is an intrinsic evaluation of the Language Model \(LM\), compared with the extrinsic evaluation, which evaluate the performance of a language model by embedding it in an application and measuring how much the application improves. Extrinsic evaluation is the best way, but it is too expensive.

