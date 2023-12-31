# Term-Deposit-Potential-Customer-Prediction
Term deposits stand as a significant revenue stream for banks, representing cash investments held within financial institutions. These deposits yield returns at agreed-upon interest rates over specified terms. To promote term deposits, explained by dataset banks employ diverse outreach strategies like email marketing, advertisements, telephonic outreach, and digital marketing.

Among these strategies, telephone marketing campaigns remain a powerful way to attract customers. However, implementing this kind of campaign requires a large investment in a large call center. **Conditions based on the dataset also explain that the marketing strategy, although categorized as the most effective compared to other strategies, is described as having a low conversion rate of only 11.7%.**

**The hypothesis that the team can give based on this condition is that the bank institution does not yet have an idea of potential customers for marketing campaigns.** Therefore, a solution is needed in the form of potential customers understanding

This project applies a supervised machine learning approach as a solution for understanding potential customers. **The aim of this project is to be able to build a model that has an accuracy and precision of more than 85% as a better representation of the conversion rate than the current situation.**

## Project Organization
```
.
├── dataset-used/                                         : Storage Directory for Dataset Used on Project consist of separated Train & Test
│   └── Banking/
│       ├── train.csv
│       └── test.csv
├── stage-0/                                              : Storage Directory for Output Progress on First Week  
│   └── Report Project Planning.pdf
├── stage-1/                                              : Storage Directory for Output Progress on Second Week
│   ├── EDA + Business Insights.ipynb
│   └── Report EDA + Business Insights.pdf
├── stage-2/                                              : Storage Directory for Output Progress on Third Week
│   ├── first-iteration/                                  : Contains Pre-Processing Output on First Iteration
│   │   ├── test/
│   │   │   ├── output/
│   │   │   │   └── test.csv
│   │   │   └── Pre-Processing.ipynb
│   │   └── train/
│   │       ├── output/
│   │       │   └── train.csv
│   │       └── Pre-Processing.ipynb
│   └── second-iteration                                  : Contains Pre-Processing Output on Second Iteration
│       ├── output/
│       │   └── data.csv
│       └── Pre-Processing.ipynb
├── stage-3/                                              : Storage Directory for Output Progress on Fourth Week
│   ├── first-iteration/
│   │   ├── Modeling_Decision-Tree_Random-Forest.ipynb
│   │   └── Modeling_Decision-Logreg_KNN.ipynb
│   ├── second-iteration
│   │   ├── output/                                       : Output from Random Forest Modeling consist of dot & png
│   │   │   ├── decision_tree.dot
│   │   │   ├── tree.dot
│   │   │   ├── tree.png
│   │   │   └── tree_1.png
│   │   ├── Modeling_Decision-Tree_Random-Forest.ipynb
│   │   └── Modeling_Decision-Logreg_KNN.ipynb
│   └── Report Modeling Experiment.pdf                    : Finals Reports Consist of Project Important Points
├── Project Presentation.pdf
├── README.md                                             : Simple Reports
└── requirements.txt                                      : requirements to run this model  

```

## Potential Customer Prediction

**Marketing Campaign Analysis:**

Marketing campaign analysis for a banking institution's term deposit program focuses on evaluating the rate at which individuals subscribing to the term deposit after engaging with the campaign. This analysis centers on metrics like click-through rates and the conversion rate from interested prospects to actual subscribers. It aims to gauge the campaign's efficiency in converting prospects into term deposit subscribers, enabling the bank to refine strategies, optimize communication channels, and tailor messages for maximum subscriber conversion and financial impact.

**Objective:**

The focus of this project is to produce analysis that can answer several questions regarding marketing campaign analysis as follows.
- How are the profile of prospective bank customers from the Term Deposit Marketing Program?
- What are the significant factors that made customer convert to the program?
- How the predictive models can be implemented to Banking Institution Business Prosess?

### Analysis
Analysis done in this section are perfomed to answer objectives above.

**Customer Profile based on Age & Balance Features**
**Assumption:**
From Banking Prespective the Potential Customer based on Age & Balance are the one who having big amount of balance and correlated to age assume to be around prime carrer age (higher age).

<img src='https://github.com/bagusatya08/Term-Deposit-Potential-Customer-Prediction/blob/main/images/age%20distribution.png'>
Plot showed above are balance distribution after normalization done with IQR method. There are range of customer age from 18 to 72 years old which can considered as normal age range without false outlier. Important insight gain from the plot are the range of converted customer based on age are grouped around range of 25 to 60 years old. So based on these plot we can assumed if we want to understand the customer profile based on age that
1. The higher conversion rate customer are scatter around age of 25 to 60 years old
2. & Low conversion rate are scatter before 25 & after 60 years old.

<p align="center">
<img src='https://github.com/bagusatya08/Term-Deposit-Potential-Customer-Prediction/blob/main/images/age%20correllated%20to%20balance.png'>
<p>
From above, we need to search for more evidance to proof our assumption based on data, so the team does correlate the age feature to balance. The result shown that it is true, that customer on age ranges of 25 to 60 having higher balance than the rest with parameter of 40.000 euros divided by blue line on plot to be spesific age in ranges of 30 to 60 years old. To confirm this findings, team also done statistical significance testing using Kruskal-Wallis and the two group correlated of age and balance are having significance median values. Here are the two group listed.
> Potential Customer Group based on Assumption: Age range of 25 to 60 & higher balance
> Non-Potential Customer Group based on Assumption: Age before 25 & after 60 with lower balance

### Modeling
The use of **Random Forest via Hyperparameter Tuning with GridSearchCV() was selected as the best model from the evaluation metrics Accuracy Score 0.96, & Precision Score 0.95.** These results were taken from the second iteration of the experiment because of the poor results obtained from the first iteration where the model had a tendency to over-fit. The explanation is shown as follows.


<p align="center">
<img src='https://github.com/bagusatya08/Term-Deposit-Potential-Customer-Prediction/blob/main/images/confusion%20matrix%20result.png'>
<img src='https://github.com/bagusatya08/Term-Deposit-Potential-Customer-Prediction/blob/main/images/feature%20importance.png'>
</p>

From the Feature Importance, shown that feature 'duration' having the best score out of other feature.

## Project Conclusion
In the end how the model can implemented to business process explained as per this ilustration.

<p align="center">
<img src='https://github.com/bagusatya08/Term-Deposit-Potential-Customer-Prediction/blob/main/images/business%20process.png'>
</p>