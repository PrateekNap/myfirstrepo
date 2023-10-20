Prediction Drift Detection using JSD

This documentation will give an overview of prediction drift detection implemented on PASA Model using Jensen-Shannon Divergence (JSD) and how JSD values change based on change in data volume.

Prediction Drift: It is the sub-facet of data drift which refers to the analysis of drift on the prediction data using different time sets. Then, prediction drift happens if the distribution changes significantly over time.

Analysing JSD through variation in Data Volume

Prediction Drift JSD calculations for 2 data distributions

1.	We compute the probability distribution for the LEAD_SCORE feature on two different weeks(p and q): 2023-05-15 and 2023-05-21.
2.	Compute the Jensen-Shannon divergence between the two probability distributions.

The computed JSD value is represented in following manner:

 



Study on how JSD values changes for two data distributions by  varying feature value by 5%, 10%, 20%, 30% and 50%

1.	We changed the LEAD_SCORE feature value ranging between 5% to 50% increase to check its impact on JSD.
2.	The JSD was observed to be zero because the probability distribution did not change as the value count of LEAD_SCORE feature remained the same.
3.	This resulted to a conclusion that JSD gets affected by change in data volume 
4.	The bucketization of LEAD_SCORE feature was done to check the JSD variation when we change the bucket size.

JSD Comparison for different bucket sizes

1.	We find the probability distributions of lead scores for two different weeks with varying bucket sizes.
2.	Here we create 4 buckets of LEAD_SCORE feature in such a way that 
a.	LEAD_SCORE value of 0 to 25 falls in Bucket1, 
b.	26 to 50 in Bucket2, 
c.	51 to 75 in Bucket 3
d.	Greater than 75 in Bucket 4.
3.	We calculate the probability of each lead score bucket for the current week distribution with a bucket size variation as follows: 5%, 10%, 20%, 30%, and 50%.
4.	The JSD results for 4 buckets across varying bucket size is as below. Here the columns represent JSD values for 5%, 10%, 20%, 30% and 50% respectively.

 


Inference:
1.	Increasing the bucket size by x% is equivalent to prediction value drift by x%. We can see that JSD value increases as we increase the bucket size percentage. Hence, JSD has direct correlation with prediction drift.


