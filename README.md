This repository contains the Automated Detection of Tropes in Short Texts project.

# Automated Detection of Tropes In Short Texts
Our project has the ambition to tackle the challenge of detecting tropes in the social media context. The first two approaches involved Fine-Tuning pretrained Bert models, while the third and fourth approaches served as a mean of comparison by using a Zero-Shot classification through ChatGPT and LLama.

# Abstract
Tropes — recurring narrative elements like the "smoking gun" or the "veil of secrecy" — are often used in movies to convey familiar patterns. However, they also play a significant role in online communication about societal issues, where they can oversimplify complex matters and deteriorate public discourse. Recognizing these tropes can offer insights into the emotional manipulation and bias present in online discussions. This paper addresses the challenge of automatically detecting tropes in social media posts. We define the task, distinguish it from prior work, and create a ground-truth dataset of social media posts related to vaccines and immigration, manually labeled with tropes. Using this dataset, we develop a supervised machine learning technique for multi-label classification, fine-tune a model, and demonstrate its effectiveness experimentally. Our results show that tropes are common across domains and that fine-tuned models can detect them with high accuracy.

# Experiments
We tested our model on different datasets for conspiracy theories and for persuasion techniques. 

# Resuts
The results yielded by the various models and experiments have been discussed and analyzed, to investigate the possibility of tropes being a "new", detectable figure of speech.

# Cite this paper
```
@inproceedings{flaccavento-peskine-etal-2025-automatedtropedetection,
    title = {Automated Detection of Tropes In Short Texts},
    author = {Flaccavento, Alessandra and Peskine, Youri and Papotti, Paolo and Torlone, Riccardo and Troncy, Raphael},
    booktitle = {Proceedings of the International Conference on Computational Linguistics (COLING 2025)},
    year = {2025},
    address = {Abu Dhabi, UAE}
}
```
# License
Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
