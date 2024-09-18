# Datasheet

## Motivation

#### For what purpose was the dataset created?

The [Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing) was created to predict the likelihood of customers subscribing to a term deposit based on various customer and marketing campaign-related factors. It was designed to help banks and financial institutions better target potential customers by improving the effectiveness of marketing campaigns.

#### Who created the dataset and on behalf of which entity? Who funded the creation of the dataset?

It was first introduced by a team from the University of Minho in Portugal, led by Paulo Cortez and Sérgio Moro, as part of academic research. The work is detailed in the paper titled "A Data-Driven Approach to Predict the Success of Bank Telemarketing." The dataset was made available for educational and research purposes.

## Composition

#### What do the instances that comprise the dataset represent? 

The instances in the dataset represent individual customers of a Portuguese bank who were targeted by a marketing campaign aimed at promoting the bank’s term deposit product. Each instance includes various attributes related to the customer’s demographics, financial situation, and interactions with the marketing campaign.

#### How many instances of each type are there? 

The dataset contains a total of 45,211 instances. Each instance corresponds to a single customer and includes 16 input features and 1 output feature, indicating whether the customer subscribed to the term deposit (binary classification).

#### Is there any missing data?

The dataset contains some missing data in a few features. Certain attributes may have null or unknown values, reflecting cases where the data was not applicable or unavailable for certain customers.

#### Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?

While the dataset does not include sensitive communications or legally protected information, it does contain some personally identifiable information (PII), such as age and marital status. However, there are no direct identifiers like names, addresses, or other explicit personal details that would compromise individual privacy.

## Collection process

#### How was the data acquired? 

The data was acquired through direct marketing campaigns conducted by a Portuguese bank. These campaigns involved contacting customers, primarily through phone calls, to promote a term deposit product. Information about the customers and their responses to the campaign were recorded, along with various demographic and financial details.

#### If the data is a sample of a larger subset, what was the sampling strategy? 

The exact sampling strategy is not explicitly detailed, but the dataset appears to include a broad cross-section of customers, capturing a range of demographic and financial characteristics. There is no evidence of specific stratified or randomised sampling being applied.

#### Over what time frame was the data collected?

The data was collected over several campaigns conducted between May 2008 and November 2010. 

## Preprocessing/cleaning/labelling

#### Was any preprocessing/cleaning/labeling of the data done? If so, please provide a description. If not, you may skip the remaining questions in this section. 

No known complex preprocessing steps, such as discretisation, scaling, or feature extraction, were applied in the original dataset.

#### Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 

The categorical features in the publicly available dataset are still in their original string format. No mention is made of the availability of a completely raw, unprocessed version of the data.
 
## Uses

#### What other tasks could the dataset be used for?

In addition to predicting term deposit subscriptions, the dataset could be used for other tasks such as:

- **Customer segmentation**: identifying distinct groups of customers based on demographics and financial behaviours to personalise marketing strategies.
- **Campaign performance analysis**: evaluating the effectiveness of different marketing approaches (e.g., call duration, previous outcomes) on customer responses.
- **Financial behavior analysis**: understanding the relationship between customer demographics and financial decisions, such as savings or investment behaviours.

#### Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups or other risks or harms? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 

Yes, certain aspects of the dataset's composition could affect its future use:

- **Bias in data collection**: the dataset includes sensitive features like age, education, and marital status, which could introduce bias if not handled carefully. For instance, relying heavily on these attributes for marketing decisions could result in unfair treatment or exclusion of specific demographic groups.
- **Imbalanced classes**: the target variable (term deposit subscription) is imbalanced, with fewer positive (subscribed) cases. This imbalance can lead to models overfitting the majority class and struggling to accurately predict the minority class.

To address these concerns, users should ensure their models do not unfairly target or exclude certain groups, and may need to apply techniques like class rebalancing or fairness-aware algorithms to improve model performance and fairness.

#### Are there tasks for which the dataset should not be used? If so, please provide a description.

The dataset should not be used for tasks that could lead to discriminatory outcomes or unfair treatment based on personal characteristics like age, marital status, or education level. For example, it should not be used to make automated decisions that disadvantage certain demographic groups in terms of access to financial products or services. Additionally, it should not be used for applications that might cause legal risks, such as violating data privacy regulations if re-identifiable information is inferred.

## Distribution

#### How has the dataset already been distributed? 

The dataset has been made publicly available through the UCI Machine Learning Repository. It is accessible for download by researchers, students, and professionals for academic and research purposes.

#### Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?

The dataset is provided under the terms and conditions outlined by the UCI Machine Learning Repository. While no explicit copyright or IP license is specified, users are expected to adhere to academic and ethical standards when using the data, including appropriate citation of the source and authors in any published work. The original dataset creators should be credited, specifically referencing the paper "A Data-Driven Approach to Predict the Success of Bank Telemarketing" by Paulo Cortez and Sérgio Moro.

## Maintenance

#### Who maintains the dataset?

The dataset is maintained by the UCI Machine Learning Repository, which hosts and provides access to the dataset. However, the original creators, Paulo Cortez and Sérgio Moro, are responsible for the initial creation and documentation of the dataset. No formal ongoing maintenance or updates to the dataset have been indicated by the authors.
