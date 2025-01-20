# Description

## Background / Context:

The WiDS Datathon Global Challenge was developed with [Ann S. Bowers Women’s Brain Health Initiative (WBHI)](https://wbhi.ucsb.edu/) in collaboration with Cornell University and UC Santa Barbara. Datasets and support are provided by the Healthy Brain

Neuropsychiatric disorders that occur in development, like anxiety, depression, autism, and attention deficit hyperactivity disorder, or ADHD, often differ in how and to what extent they affect males and females. ADHD occurs in about 11% of adolescents, with around 14% of boys and 8% of girls having a diagnosis. There is some evidence that girls with ADHD can often go undiagnosed, as they tend to have more inattentive symptoms which are harder to detect. Girls with ADHD who are undiagnosed will continue suffering with symptoms that burden their mental health and capacity to function.

For more domain context see the following videos: [The Role of AI in Advancing Women's Brain Health Research](https://youtu.be/7X4M8dYkrvw?si=Ae4Qrgo_4bb3nUdo) and [Sex-specific differences in the healthy and disordered brain](https://youtu.be/KO7YI7j_d-A?si=uU1UQF3ybGveKuwU)

## Registration

Participants are required to register with WiDS Worldwide to participate in the WiDS Datathon. You only need to register once, regardless of the datathon 2025 competition(s) that you choose to compete in.

## Challenge Overview:

In this year’s WiDS Datathon, participants will be tasked with building a model to predict both an individual’s sex and their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information.

**Challenge Question and Task:**  
“What brain activity patterns are associated with ADHD; are they different between males and females, and, if so, how?”

The task is to create a multi-outcome model to predict two separate target variables: 1) ADHD (1=yes or 0=no) and 2) female (1=yes or 0=no).

For more information see the following video: [Statistical Approaches on Vectorized Connectomes for Brain-Behavior Mapping](https://youtu.be/jbIsfVxuMWM?si=4n6Ghe9Eoh5lO1eL)

**Why is this important?**  
Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

**Data Science Skills Developed:**

- Data cleaning and preprocessing for model development and analysis
- Understanding correlations
- Regression model selection (statistical, machine learning)
- Regression model fitting/testing (cross validation, avoiding over/underfitting, stratification of data during training)
- Explaining factors that drive the performance of the model
- Multi-outcome prediction


### Evaluation


The F1 score is the harmonic mean of the precision and recall. It thus symmetrically represents both precision and recall in one metric. The highest possible value of an F-score is 1.0, indicating perfect precision and recall, and the lowest possible value is 0, if precision and recall are zero.

[https://en.wikipedia.org/wiki/F-score](https://en.wikipedia.org/wiki/F-score)

Since the theme of this challenge is to uncover gender inequities and because ADHD diagnosis is harder for females to predict, for the purposes of this competition we are assigning 2x weight to Female ADHD cases (ADHD\_Outcome=1, Sex\_F=1). In our implementation of the F1 Score, weighted F1 Score is calculated on each column, and those two individual scores are averaged to get the final Kaggle leaderboard score.

## Submission Format

For every participant (i.e. row) in the test dataset (`test_tsv`), submission files should contain three columns: `participant_id` and `ADHD_Outcome` and `Sex_F`. `participant_id` should be an integer and `ADHD_Outcome` and `Sex_F` should both be a real value. For each row, these three values should be separated by a comma.

The file should contain a header and have the following format:

```
participant_id,ADHD_Outcome,Sex_F
v1nMpCoLGU0V, 1, 1
uEZHGukIUQ0k, 0, 1
IbF3zW0Wbx4Q, 0, 0
```

## Leaderboard Standings

During the competition the leaderboard is calculated with approximately 51% of the test data. After the competition closes, the final standings will be computed based on the other 49%. Thus, **the final leaderboard standings may be different from those during the competition.**

### Tutorials & Resources

### Domain Context Resources:

- [The Role of AI in Advancing Women's Brain Health Research](https://youtu.be/7X4M8dYkrvw?si=Ae4Qrgo_4bb3nUdo) (27 min)
- [Sex-specific differences in the healthy and disordered brain](https://youtu.be/KO7YI7j_d-A?si=uU1UQF3ybGveKuwU) (16 min)
- [10 Points about ADHD](https://drive.google.com/file/d/10OBI8xKT2lw6USz8BsK9BBOG_VhRAyV0/view?usp=sharing)

### Dataset Resources:

_More information on the dataset and how it was processed_

- [Introduction to the Healthy Brain Network (HBN)](https://youtu.be/GVEemkLwz-k) (3 min)
- [Functional Connectivity Matrices Processed Through RBC](https://youtu.be/OH3QH1ol4io?si=FFYEg-m1WYyCDcEB) (7 min)
- Follow along dataset videos with this [summary script](https://drive.google.com/file/d/1Ioxeajg-EDI9dNDtGxfJPnZZETmTMwqi/view?usp=sharing)

### Recorded Workshops:

- [Global Datathon Workshop #1: Introduction to the Challenge and Dataset](https://youtu.be/Lp-4rtCEVKY?si=kRvCoP145965GoLr) (17 min)

### Additional Resources:

- [Statistical Approaches on Vectorized Connectomes for Brain-Behavior Mapping](https://youtu.be/jbIsfVxuMWM?si=4n6Ghe9Eoh5lO1eL) (36 min)
- [Functional Magnetic Resonance Imaging (fMRI)](https://youtu.be/Zy0lpiuoET0?si=niYIDI8E53Btk5Lv) (19 min)
- [Geometric Approaches for Processing Brain Connectomes](https://youtu.be/vtHBOBOcn6E?si=Q0FuLhRJAHxqRcPx) (19 min)
- [Graph Neural Networks to Process Brain Connectomes](https://youtu.be/OkE3776GfWU?si=u1q_45MKaRzue70d) (23 min)
- [Full data dictionaries](https://drive.google.com/file/d/1hQs3irD_kERkgrmyvjF7n8U8YXFEzyqg/view?usp=sharing) for Color Vision Test, Strength and Difficulties Questionnaire, and Alabama Parenting Questionnaire
- [Relevant Readings and Research Papers](https://drive.google.com/drive/folders/14flM-1i7Ksz3iKY2KWhnlBz8RNguJBCA?usp=sharing)