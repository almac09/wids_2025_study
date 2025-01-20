## Dataset Description

_The WiDS Datathon was developed with [Ann S. Bowers Women’s Brain Health Initiative (WBHI)](https://wbhi.ucsb.edu/) in collaboration with Cornell University and UC Santa Barbara. Datasets and support are provided by the Healthy Brain Network (HBN), the signature scientific initiative of the [Child Mind Institute](https://childmind.org/), and the Reproducible Brain Charts project (RBC)._

We will analyze diagnostic data, socio-demographic, emotions, and parenting data, and functional MRI data from the Healthy Brain Network (HBN) — the signature scientific initiative of the Child Mind Institute. HBN utilizes a community-referred recruitment model by encouraging the participation of families who have concerns about mental health or learning challenges in their children. The functional MRI data are used to extract a time series of activity per brain region, and these regions’ time series are correlated to obtain functional MRI connectome matrices.

The goal is to build a model to predict both an individual’s sex _and_ their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information.

## Dataset Folders

**(1)** the training folder `train_tsv` consists of three types of information about the 1,200+ subjects. They are:

- **a)** the targets (ADHD diagnosis and sex)
- **b)** functional MRI connectome matrices
- **c)** socio-demographic information, e.g., subject’s “handedness” or “parent’s education level”, emotions (“Strength and Difficulties Questionnaire”), and parenting information (“Alabama Parenting Questionnaire”). These include both quantitative and categorical metadata.

_Friendly hint: Participants will need to process the categorical data (perhaps create dummy variables) and then combine this processed dataset with the functional connectome dataset to create a final training dataset to use in their models._

**(2)** the test folder `test_tsv` consists of unseen data frames for 300+ subjects. These data frames are as follows:

- **a)** functional MRI connectome matrices
- **b)** socio-demographic, emotions, and parenting information

To participate in the Datathon, you will submit a solution file containing the type of ADHD diagnosis _and_ the sex for each row in the test dataset. The predicted values you submit will be compared against the observed values for the test dataset and this will determine your standing on the Leaderboard during the competition as well as your final standing when the competition closes.

You will also be provided an example solution file prepared for submission.

## External Data Usage

The datathon task can be tackled successfully without the use of external data. In fact, the degree to which we have anonymized the data would make joining additional data to the competition data difficult.

## Target Variables

`ADHD_Outcome`: Type of Diagnosis (0=Other/None, 1=ADHD)  
`Sex_F`: Sex of participant (0=Male, 1=Female)

You will also be provided a full data dictionary