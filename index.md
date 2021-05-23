# DCH-2: Training Data for the DialEval-2 Task

Recently, many reserachers are trying to build automatic helpdesk systems. However, there are very few methods to evaluate such systems. In **DialEval-2**, we aim to explore methods to evaluate task-oriented, multi-round, textual dialogue systems automatically. This dataset have the following features:

- Chinese customer-helpdesk dialogues carwled from [Weibo](weibo.com).
- English dialgoues: manually translated from the Chinese dialgoues.
- Nugget type annotatoins for each turn: indicate whether the current turn is useful to accomplish the task.
- Quality annotation for each dialogue.
  - task accomplishment
  - customer satisfaction
  - dialogue effectiveness

In DialEval-2, we consider annotations ground truth, and participants are required to predict nugget type for each turn (Nugget Detection, or ND) and dialogue quality for each dialogue (Dialogue Quality, or DQ).

Links

- [Homepage of DialEval-2 Task](http://sakailab.com/dialeval2/)
- [Introduction of the training dataset (current page)](https://dialeval-2.github.io/DCH-2/)
- [NTCIR-16](http://research.nii.ac.jp/ntcir/ntcir-16/index.html)

# Registration

To register NTCIR-16 DialEval-2 Task, please send an email to [dialeval2org@list.waseda.jp](mailto:dialeval2org@list.waseda.jp) with the following information.

- Team Name (e.g. Waseda)
- Principal investigator’s name, affilication, email address
- Names, affiliations, email addresses of other team members
- Subtasks that you plan to participate: Chinese, English, or BOTH

Later, NII will require you to register to NTCIR tasks through their website, but please contact us by email first.

# Access to the dataset

To obtain the dataset, please fill and submit [our user agreement form](https://forms.gle/dk3wjqFTEF9k8SAe6).

# Leaderboard

Comming Soon

# Overview of the DCH-2 Dataset

## Training Data

The Chinese training dataset contains 4,390 (4,090 for training + 300 for dev) customer-helpdesk dialgoues which are crawled from [Weibo](weibo.com). All of these dialogues are annotated by 19 annotators.

In the DCH-2 dataset, as we finished the translation of all the Chinese dialogues, the English dataset contains 4,390 dialogues as well. All the English dialogues are manually translated from the Chinese dataset. The English dataset shares the same annotations with the Chinese dataset.

- Training set
  - dch2_train_cn.json (4,090 Chinese dialogues: 3,700 as training set + 390 as dev set at DialEval-1)
  - dch2_train_en.json (4,090 English dialogues: 2,251 as training set + 390 as dev set at DialEval-1 + 1,449 newly translated)

- Dev set
  - dch2_dev_cn.json (300 dialogues, used as test set at DialEval-1)
  - dch2_dev_en.json (300 dialogues, used as test set at DialEval-1)

## Test Data

Will be released in Dec 2021 according to the task schedule.

## Annotation

We hired 19 Chinese students  to annotate the training/dev dataset in 2018. In 2019, the test dataset of DialEval-1 were annotated by another group of annotators. Thus, there may be a gap between the training data and test data, as the dialogue annotation is quite subjective.

# Format of the JSON file

Each file is in JSON format with UTF-8 encoding.

Following are the top-level fields:

- **id**
- **turns**: array of turns from the customer and the helpdesk (see details below)
- **annotations**: a list of annotations provided by 19 annotators. Each annotation consists of two fields: **nugget** and **quality**

Each element of the turns field contains the following fields:

- **sender**: the speaker of this turn (either customer or helpdesk)
- **utterances**: the utterances (may be multiple) they sent in this turn. Note that some utterances are empty strings since we didn't crawl emoji and photos.

Each element of **annotations** contains the following fields:

- **nugget**: The list of nugget types for each turn (see details below).
- **quality**: A dictonary consists of the subjetive dialogue quality scores: A-score, S-score, and E-score (see details below).

## Nugget Types

- CNUG0: Customer trigger (problem stated)
- CNUG*: Customer goal (solution confirmed)
- HNUG*: Helpdesk goal (solution stated)
- CNUG: Customer regular nugget
- HNUG: Helpdesk regular nugget
- CNaN: Customer Not-a-Nugget
- HNaN: Helpdesk Not-a-Nugget

<img src="https://i.postimg.cc/TPqH4ttz/nugget-example.png" alt="drawing" style="width:600px;"/>

## Dialogue Quality

- A-score: Task **A**ccomplishment (Has the problem been solved? To what extent?)
- S-score: Customer **S**atisfaction of the dialogue (not of the product/service or the company)
- E-score: Dialogue **E**ffectiveness (Do the utterers interact effectively to solve the problem efficiently?)

Scale: [2, 1, 0, -1, -2]

## Note

To protect the privacy, some sensitive information in the dialogue data has been masked. For example, we replaced  telephone numbers with 123456789, and email addresses with XXX@YYY.com

# Evaluation

## Metrics

During the data annotaiton, we noticed that annotators' assessment on dialgoues are highly subjective and are hard to consolidate them into one gold label. Thus, we proposed to preserve the diverse views in the annotations “as is” and leverage them at the step of evaluation measure calculation.

Instead of juding whether the estimated label is equal to the gold label, we compare the difference between the estiamted distributions and the gold distributions calculaed by 19 anntators' annotations). Specifically, we employ these metrics for quality sub-task and nugget sub-task:

- Quality:
  - **NMD**: Normalised Match Distance.
  - **RSNOD**: Root Symmetric Normalised Order-aware Divergence
- Nugget:
  - **RNSS**: Root Normalised Sum of Squared errors
  - **JSD**: Jensen-Shannon divergence

For the details about the metrics, please vistit:

- [NTCIR-16 Dialogue Evaluation Task Definition](https://waseda.app.box.com/v/dialeval2taskdef)
- [Comparing Two Binned Probability Distributions for Information Access Evaluation](https://waseda.app.box.com/v/SIGIR2018preprint).

## Test and Submission

Comming Soon

# Have questions?

Please contact: [dialeval2org@list.waseda.jp](mailto:dialeval2org@list.waseda.jp)

# Conditions and Terms

See [https://dialeval-2.github.io/DCH-2/terms](https://dialeval-2.github.io/DCH-2/terms)
