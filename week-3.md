# Week 3

### Unknown Words

Text file statistics:

* File: 20180111content.txt

* Line Number: 19322265

* Character Number: 47861275

* File Size: 1.5GB

In `jieba`, for unknown words, a HMM-based model is used with the Viterbi algorithm. `jieba.cut(sentence, cut_all=False, HMM=True)` accept 3 parameters. `sentence` is for the sentence that you want to segment. `HMM` controls the whether the HMM module is used.

> ```
> seg_list = jieba.cut("他来到了网易杭研大厦", HMM = False) # "Unknown" words will not be recognized
> seg_list = jieba.cut("他来到了网易杭研大厦", HMM = True) # "Unknown" words will be recognized
> ```

Indeed in what we called "unknown" words there are 2 kinds of words: `unknown` words and `unseen` words. `unknown` are the words that do not occur in lexicon, but can be split into parts that are all in lexicon. For example, the word “樓主” is not in lexicon, but it can be split into “樓” and "主“ which are all in lexicon. `unseen`words, on the other hand, cannot be split in this way.

# 

We calculate the frequency \(times it occurs\) of the words segmentation result under two different conditions `HMM=False` \(stored in `no.txt` \) and `HMM=True` \(stored in `yes.txt` \). We focus more on the condition `HMM=True` , where unknown words will occur. `jieba` does not provide any function interface for determining whether a word is `unknown` . We simply compare the words in `no.txt` and `yes.txt` with the ones in lexicon, and those which do no occur in lexicon are stored in `un-no.txt` and `un-yes.txt` respectively. In principle, `un-no.txt` should only contain `unseen` words. Therefore, words occur in `un-yes.txt` but not in `un-no.txt` can be considered as `unknown` words. Here are some samples:

`unknown.txt` :

> word   freq
>
> ---
>
> 樓主    110601
>
> 好過    55874
>
> 仲要    53124
>
> 出黎    47381
>
> 我會    46479
>
> 試下    41055
>
> 部機    40870

`unseen.txt` :

> word   freq
>
> ---
>
> 首歌    92349
>
> 版主    80416
>
> 小弟    79238
>
> 射手座    56865
>
> 哈哈    53937
>
> 中意    43392
>
> 一班    42598

In fact, in `unseen.txt` there are still some `unknown` words. About 80% of the Words with its frequency higher than 1000 are reasonable words. The number of them in this text is around 5000. In terms of "How to select appropriate words from them", it needs further study.



### Lexicon

* Number of Single Character: 



