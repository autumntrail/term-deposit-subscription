# Datasheet Template

## Motivation

#### For what purpose was the dataset created?

The [Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing) was created to predict the likelihood of customers subscribing to a term deposit based on various customer and marketing campaign-related factors. It was designed to help banks and financial institutions better target potential customers by improving the effectiveness of marketing campaigns.

#### Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?

It was first introduced by a team from the University of Minho in Portugal, led by Paulo Cortez and Sérgio Moro, as part of academic research. The work is detailed in the paper titled "A Data-Driven Approach to Predict the Success of Bank Telemarketing." The dataset was made available for educational and research purposes.

## Composition

#### What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 

The instances in the dataset represent individual customers of a Portuguese bank who were targeted by a marketing campaign aimed at promoting the bank’s term deposit product. Each instance includes various attributes related to the customer’s demographics, financial situation, and interactions with the marketing campaign.

#### How many instances of each type are there? 

The dataset contains a total of 45,211 instances. Each instance corresponds to a single customer and includes 16 input features and 1 output feature, indicating whether the customer subscribed to the term deposit (binary classification).

#### Is there any missing data?

The dataset contains some missing data in a few features. Certain attributes may have null or unknown values, reflecting cases where the data was not applicable or unavailable for certain customers.

#### Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?

While the dataset does not include sensitive communications or legally protected information, it does contain some personally identifiable information (PII), such as age and marital status. However, there are no direct identifiers like names, addresses, or other explicit personal details that would compromise individual privacy.

## Collection process

- How was the data acquired? 
- If the data is a sample of a larger subset, what was the sampling strategy? 
- Over what time frame was the data collected?

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 
- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
 
## Uses

- What other tasks could the dataset be used for? 
- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 
- Are there tasks for which the dataset should not be used? If so, please provide a description.

## Distribution

- How has the dataset already been distributed? 
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  

## Maintenance

- Who maintains the dataset?

