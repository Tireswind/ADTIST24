# Automated Detection of Tropes In Short Texts

## Abstract
Tropes — recurring narrative elements like the "smoking gun" or the "veil of secrecy" — are often used in movies to convey familiar patterns. However, they also play a significant role in online communication about societal issues, where they can oversimplify complex matters and deteriorate public discourse. Recognizing these tropes can offer insights into the emotional manipulation and bias present in online discussions. This paper addresses the challenge of automatically detecting tropes in social media posts. We define the task, distinguish it from prior work, and create a ground-truth dataset of social media posts related to vaccines and immigration, manually labeled with tropes. Using this dataset, we develop a supervised machine learning technique for multi-label classification, fine-tune a model, and demonstrate its effectiveness experimentally. Our results show that tropes are common across domains and that fine-tuned models can detect them with high accuracy.

## Dataset
We define 9 tropes in online posts, on **Vaccine** and **Immigration** topics:
 - **Skepticism Towards Authority (STA)**: Text appeals to skepticism towards scientific experts or political authorities, with statements such as "They should know/do better"  and "They don't know what they are doing".
> "authorities have failed now and before".
 - **Defend The Weak (DTW)**: Text emphasizes the negative effects of something (e.g., vaccine, immigration policy) on vulnerable populations, with statements like "it is especially harmful to children".
> "we must protect the weak", "they put the weak ones in danger".
 - **Hidden Motives (HM)**: Text alludes to underlying agendas, suggesting that something (e.g., vaccines, illegal immigrants) is promoted by individuals with malicious intentions (such as hypocrites and tyrants) and concealed motives ("There is clearly an untold story behind it").
> "we must stop this scam", "they are lying for their interest".
 - **Liberty, freedom (LF)**: Text emphasizes personal autonomy and rights, using statements such as "my body, my choice", "not anti-something but pro-choice", and "people were stripped of their rights, jobs, freedom and forced against their will".
> "I should be able to do what I want", "They are forcing on me something I don't want".
 - **Natural Is Better (NIB)**: Text promotes the idea that natural or traditional approaches are superior, with assertions like "natural immunity is the best immunity", "traditional solutions are more effective and secure", and "nature had a solution for this".
> "I trust tradition more than innovation", "They want to force non-natural solutions".
 - **Time Proves Me Right (TPMR)**: Text appeals to the eventual validation of one's argument over time ("time will prove me right") and asserting foresight ("I told you this would happen").
> "I knew it / I know what is gonna happen", "They don't see the problem coming".
 - **Too Fast (TF)**: Text implies that something (such as vaccines) is unsafe or unreliable because it is experimental, untested, developed too quickly ("haste makes waste"), or not yet fully approved by authorities.
> "They rushed the decision".
 - **Scapegoat (SC)**: Text that attributes blame for a (possibly under-specified) problem to a person or entity not directly involved, such as "They claim it's A or B's fault, but it's really X's fault", or assigning responsibility for an issue to a popular entity, such as Bill Gates.
> "I blame somebody, even without evidence", "It is all their fault!".
 - **Wicked Fairness (WF)**: Text compares to how two entities are being treated, highlighting application of different principles for similar situations (i.e., double standard). Some examples use questions, "Why can't X have access to Z while Y can?", if/then statements "If X can be punished for that, then Y should be punished as well".
> "It's not fair".

The data consist of 3,304 tweets annotated w.r.t these 9 tropes, and is shared in [./tropes_data.csv](tropes_data.csv)

## Classification models
We propose baseline models to detect tropes automatically. We use BERT, CovidTwitter-BERT as supervised approaches, training on 80% of the data, and Chat-GPT, LLama-3-8B in a zero-shot fashion as LLM baselines. The code used for the experiments is shared in [./src/](src)

We show in this table the results on test data (20%) using F1 score.

|  Models | STA | DTW | HM | LF | NIB | TPMR | TF | SC | WF | None | Avg |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Bert | 0.54 | 0.57 | 0.42 | 0.78 | 0.50 | **0.33** | 0.75 | 0.48 | 0.55 | 0.83 | 0.58 |
| CT-BERT | **0.60** | **0.68** | **0.59** | **0.80** | **0.55** | 0.27 | **0.77** | **0.64** | **0.57** | **0.87** | **0.65** |
| Chat GPT | 0.19 | 0.36 | 0.27 | 0.66 | 0.27 | 0.00 | 0.31 | 0.20 | 0.44 | 0.55 | 0.32 |
| Llama-3-8B | 0.15 | 0.29 | 0.20 | 0.38 | 0.27 | 0.12 | 0.16 | 0.10 | 0.10 | 0.24 | 0.23 |


## Cite this paper
```
@inproceedings{flaccavento-peskine-etal-2025-automatedtropedetection,
    title = {Automated Detection of Tropes In Short Texts},
    author = {Flaccavento, Alessandra and Peskine, Youri and Papotti, Paolo and Torlone, Riccardo and Troncy, Raphael},
    booktitle = {Proceedings of the International Conference on Computational Linguistics (COLING 2025)},
    year = {2025},
    address = {Abu Dhabi, UAE}
}
```
## License
Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
