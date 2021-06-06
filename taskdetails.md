---
title: Detail of the NTCIR-16 Dialogue Evaluation Task (DialEval-2)
---

# NTCIR-16 Dialogue Evaluation Task (DialEval-2)

Recently, many reserachers are trying to build automatic helpdesk systems. However, there are very few methods to evaluate such systems. In **DialEval-2**, we aim to explore methods to evaluate task-oriented, multi-round, textual dialogue systems automatically. This dataset have the following features:

- Chinese customer-helpdesk dialogues carwled from [Weibo](weibo.com).
- English dialgoues: manually translated from the Chinese dialgoues.
- Nugget type annotatoins for each turn: indicate whether the current turn is useful to accomplish the task.
- Quality annotation for each dialogue.
  - task accomplishment
  - customer satisfaction
  - dialogue effectiveness

In DialEval-2, we consider annotations ground truth, and participants are required to predict nugget type for each turn (Nugget Detection, or ND) and dialogue quality for each dialogue (Dialogue Quality, or DQ).

# Registration

To participate in the DialEval-2 task, please do both (1) and (2).

(1) Visit this NTCIR-16 page, check the information there (e.g. "what participants must do"),
and register online. (You can register to other NTCIR-16 tasks as well.)  
[http://research.nii.ac.jp/ntcir/ntcir-16/howto.html](http://research.nii.ac.jp/ntcir/ntcir-16/howto.html)

(2) Send the following information to [dialeval2org@list.waseda.jp](mailto:dialeval2org@list.waseda.jp) .

  * Team Name (e.g. Waseda)
  * Principal investigator’s name, affilication, email address
  * Names, affiliations, email addresses of other team members
  * Subtasks that you plan to participate: Chinese, English, or BOTH

Please tell us in your email message that you have also completed Step (1).

# Training data

To obtain the training data, see [here](https://dialeval-2.github.io/DCH-2/).

# Leaderboard

Comming Soon

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

# Links

- [Homepage of DialEval-2 Task](http://sakailab.com/dialeval2/)
- [DialEval-2 Details (current page)](https://dialeval-2.github.io/DCH-2/taskdetails)
- [Introduction of the training dataset](https://dialeval-2.github.io/DCH-2/)
- [NTCIR-16](http://research.nii.ac.jp/ntcir/ntcir-16/index.html)
