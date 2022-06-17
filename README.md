# Human Saliency Interpretation
This repository contains the collected study data and R analysis code of our FAccT 2022 paper [Human Interpretation of Saliency-based Explanation Over Text](https://arxiv.org/abs/2201.11569).

## Human Ratings
We provide the human ratings and the respective word and sentence features of the three experiments described in our paper in [human_ratings](human_ratings/).
The ratings regarding the first (English sentiment, EN), second (German fact checking, DE) and third (English sentiment
with integrated gradients, EN-IG) can be found in the respective CSV files [responses_en.csv](human_ratings/responses_en.csv),
[responses_de.csv](human_ratings/responses_de.csv) and [responses_en_ig.csv](human_ratings/responses_en_ig.csv).

The files contain the following fields:
* **saliency**: The color intensity specified as the saturation value S in a (H,S,V) color triple.
* **display_index**: The sentence's position within a sequence of sentences (e.g. the third sentence in the sequence of 150 sentences). This relates to temporal effects such as learning.
* **word_length**: The number of characters in a word, e.g. 7 for ``example''.
* **sentence_length**: Number of words in the sentence.
* **relative_word_frequency**: The word's normalized frequency, estimated on a large corpus.
* **lemma_polarity**: The sentiment polarity of a word (defined via its lemma) ranging from -1 to 1 (only for EN and EN-IG).
* **normalized_saliency_rank**: Normalized rank of a word's saliency score (i.e. color intensity) in comparison to the other words in its sentence ranging from 0 to 1.
* **word_position**: The index of the token's position within its sentence.
* **capitalization**: The word's capitalization, e.g. ''example'', ''Example'' or ''EXAMPLE''.
* **dependency_relation**: Dependency relation to its parent within the dependency graph (36 types for EN and EN-IG)
* **sentence_id**:
* **worker_id**:
* **completion_time_ms**: Time the participant took to enter the rating (in milliseconds).
* ***human_importance_rating***: Importance rating the participant entered on the 7-point Likert scale.

## Statistical Analysis
We provide the code of our ordinal GAMM models and the respective significance tests and plots.
The code regarding the first (English sentiment, EN), second (German fact checking, DE) and third (English sentiment
with integrated gradients, EN-IG) can be found in the respective R Jupyter notebooks [code/analysis_en.ipynb](code/analysis_en.ipynb),
[code/analysis_de.ipynb](code/analysis_de.ipynb) and [code/analysis_en_ig.ipynb](code/analysis_en_ig.ipynb).

To run the notebooks yourself, make sure to install an R kernel to use in your Jupyter server and install the R packages:
* mgcv (at least version 1.8.32)
* itsadug
* gratia
* hash
* stringr

## Purpose of this Software
This software is a research prototype, solely developed for and published as part of the publication cited above.
It will neither be maintained nor monitored in any way.

## License
The code in the folder [code](code/) is open-sourced under the MIT license.
See the [LICENSE](LICENSE) file for details.


The user study data in the folder [human_ratings](human_ratings/) is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) (CC-BY-4.0).
## Citation
If you use our data or scripts, please cite [our paper](https://arxiv.org/abs/2201.11569):
```
@article{DBLP:journals/corr/abs-2201-11569,
  author    = {Hendrik Schuff and
               Alon Jacovi and
               Heike Adel and
               Yoav Goldberg and
               Ngoc Thang Vu},
  title     = {Human Interpretation of Saliency-based Explanation Over Text},
  journal   = {CoRR},
  volume    = {abs/2201.11569},
  year      = {2022},
  url       = {https://arxiv.org/abs/2201.11569},
  eprinttype = {arXiv},
  eprint    = {2201.11569},
  timestamp = {Tue, 01 Feb 2022 14:59:01 +0100},
  biburl    = {https://dblp.org/rec/journals/corr/abs-2201-11569.bib},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}
```
