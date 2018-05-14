# Japanese-Sentence-Similarity-Scorer

A tool for calculating Japanese sentence similarity.
Metrics include: 
* word overlapping score: BLEU-n
* cosine similarity between word-embedding-based sentence representations: Greedy matching, Vector extrema, Average embedding
* (in progress) cosine similarity between sentence vectors: Skip-thoughts

## Example
Given sentence pairs:
- 映画を見ますか || オリンピックは見ますか
- 映画はどんなのを見ますか || オリンピックは見ますか
- 映画はどれくらい見ますか || オリンピックは見ますか
- ゴルフは見ますか || オリンピックは見ますか
- サッカーは見ますか || オリンピックは見ますか
- ゴルフで好きな選手はいますか || オリンピックは見ますか

You are able to segment the sentences and calculate several similarty scores between those pairs:

  > 映画 を 見 ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.4582, greedy: 0.5179, extrema: 0.3493, average: 0.4823, mean embedding-based: 0.449836
  
  > 映画 は どんな の を 見 ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.536, greedy: 0.44, extrema: 0.3906, average: 0.3877, mean embedding-based: 0.406106
  
  > 映画 は どれ くらい 見 ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.536, greedy: 0.3935, extrema: 0.1181, average: 0.2931, mean embedding-based: 0.268249
  
  > ゴルフ は 見 ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.536, greedy: 0.553, extrema: 0.505, average: 0.5863, mean embedding-based: 0.548093
  
  > サッカー は 見 ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.536, greedy: 0.5326, extrema: 0.4489, average: 0.5053, mean embedding-based: 0.495601
  
  > ゴルフ で 好き な 選手 は い ます か || オリンピック は 見 ます か
  >> BLEU 2: 0.4582, greedy: 0.4706, extrema: 0.4657, average: 0.6291, mean embedding-based: 0.52181
  
## Dependencies:

* Tested on Python 3.6
* numpy
* sklearn
* nltk
* mecab (for word segmentation)
* pre-trained Japanese word-embedding file (gensim txt file or with whitespace-sperated lines "[word] [val1] [val2] [val3] ...")
