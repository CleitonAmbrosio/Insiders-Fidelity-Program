# "Insiders" Fidelity Program

_Project still under development, currently on a (improvement) 2nd cycle._

## Business problem

A UK-based online retail store wishes to identify the most valuable customers, in order to retain them in the client basis. They shall integrate a (to be built) fidelity program (for now named "Insiders"), with access to benefits such as: discounts, special products portfolio and personalized treatment.

## Dataset

1-year (Nov 16 to Dec 17) historical sales database attained @ [Kaggle](https://www.kaggle.com/vik2012kvs/high-value-customers-identification).

## Planned outputs

- Which customers are in the Insiders group.
- A report answering the following business questions:
  - Who is eligible to take part in the Insiders group?
  - How many clients are there in it?
  - What is the summary profile of these clients?
  - What actions can the marketing and sales team make to increase the income?
  - What is the percentage contribution of the Insiders group to the whole income?
  - What is the expected income from this group for the next months?
  - What are the conditions for someone to become part of the Insiders group?
  - What are the conditions for someone to be removed of the Insiders group?
  - What is the guarantee that the Insiders group is more valuable than the rest of the base?

## Planned cycles

### First cycle

_This one has already been finished!_

After a brief Exploratory Data Analysis step, the segmentation of the customers basis was carried on with the KMeans clustering algorithm, with 3 features engineered based on the Recency-Frequency-Monetary Value Model ([RFM](https://www.investopedia.com/terms/r/rfm-recency-frequency-monetary-value.asp), for short).

5 cohesive and well-separated clusters were attained by the end, which can be briefly described as follows (answering at least the 5 first questions of the outputs aforementioned):

| Cluster | # of customers | Percentage of customers | Avg Gross Revenue | Avg Recency | Avg Frequency |
| ---- | :----: | :----: | :----: | :----: | :----: |
| Platinum | 2 | 0.05%	| $267,963.76	| 0.5 days | 69.5 lifetime purchases |
| Golden | 4 | 0.09%	| $139,291.10	| 10.5 days | 98.8 lifetime purchases |
| Silver	| 23 | 0.53%	| $46,050.76	| 6 days | 64.7 lifetime purchases |
| Bronze | 308 | 7.04%	| $7,757.79	| 18 days | 20.6 lifetime purchases |
| Baseline | 4035 | 92.3%	| $931.45	| 97.8 days | 3.4 lifetime purchases |

- _Platinum:_ highest average gross revenue brought to the company. Moreover, has the lowest recency (desired) and the 2nd highest frequency (also a very good feature).<br>

  - **Suggested action:** keep them very close by giving special attention and benefits, such as a VIP treatment.

- _Golden:_ 2nd highest average gross revenue, highest average frequency of purchases, 3rd lowest recency.<br>

  - **Suggested action:** besides also being given special attention (as in the platinum cluster), these customers should be stimulated to buy ASAP in order to lower their recency and to do so by buying more expensive more products. Maybe some kind of discount coupon could be of use here.

- _Silver:_ 2nd highest average recency and 3rd place both in the average gross revenue as in the average frequency of purchases.<br>

  - **Suggested action:** all 3 characteristics should be stimulated somehow in order to raise these customers to the upper clusters. An idea could be the following: access to a special selection of products could be awarded to customers that chose to participate in the program and who have met the basic monthly criteria (minimum value spent and minimum number of purchases).

- _Bronze:_ these clients could greatly increase the amount of people in the upper clusters and thus should be given just a glimpse of the advantages above (such as limited access to one of them) in order to stimulate a more interesting consumption behavior.

- _Baseline:_ the most part of the customers is here. Since the idea is to develop a fidelity program (should be "restricted" in some way) these clients won't be receiving any kind of benefit, but they should be aware that there is such a program (to stimulate them to purchase in higher values and more often).


This 1st batch of results is fully available through a labeled basis in .csv format (see the models directory), which should be enough for this cycle.<br>
_**Actionable data intelligence is already being delivered**_, since the file can be loaded by business users into some spreadsheets program and more concrete actions by their part could start being planned.<br>

A formal deployment will not be made yet. A 2nd cycle with other clustering algorithms and new engineered features will be tried out first to see how the final results change.

### Future cycles

- More features (beyond those of the RFM model) shall be engineered;

- Other clustering algorithms/methods shall be tested:
  - GMM (Gaussian Mixture Model)
  - Hierarchical clustering
  - DBSCAN
  - Reduction of dimensionality
    - PCA
    - t-SNE
    - UMAP
    - Extra trees
