# Advanced Preparation of Financial Data
## Fairfield University

## Goal of the Competition

Explore the "underpricing" phenomenon most commonly seen in the stock market. In this study, we analyze the inter-relationships between the management’s confidence through the proxy of sentiments expressed in textual contents in the Management’s Discussion &amp; Analysis (MD&amp;A) sections in the prospectus and the pre-/post-IPO valuations. 

Understanding pricing strategies in the context of the Initial Public Offering (IPO) process has been receiving much attention. Most prior studies have however focused on information sources from post issuance periods, and understanding such strategies from the management’s perspective during the IPO process is still an open research issue. Form 424 variants, as finalized IPO prospectus approved by Security Exchange Committee (SEC), contain rich and genuine information about the issuing firms. In this study, we analyze the inter-relationships between the management’s confidence (through the proxy of sentiments expressed in textual contents in the Management’s Discussion & Analysis (MD&A) sections in the prospectus) and the pre-/post-IPO valuations.

The data used for this project includes successful U.S. IPOs from more than 600 companies. Our "client" is interested in which features are most important to the "underpricing" phenomenon most commenly seen in the stock market. By using advanced and novel methods to prepare the collected IPO data, we will break down the data in order to process it through phases of a CRISP-DM model. 

# Pipeline Overview
### For stage 2 we used the pipeline on the left. The other is an alternative that will be incorporated in our future work
![](https://github.com/erikhren/Advanced-Preperation-of-Financial-Data/blob/master/Images/PIPELINE.jpeg)

# Data Dictionary 
![](https://github.com/erikhren/Advanced-Preperation-of-Financial-Data/blob/master/Images/data_dictionary.jpeg)

## Data assumptions

By learning about each column and using common sence we come up with a few rules about our features. 

**IPO Pricing (P Columns)**
- IPO prices cannot contain any zero or negative values 
- Price range higher bound - P(H) must be higher or equal to the lower bound - P(L) <br>

**IPO Characteristics (C columns)**
- There can be zero days (C1) between filings, however, no negative values 
- C2 can only be 1 or 0
- Earnings per Share (C3), prior returns (C4), and sales can be zero or negative
- Outstanding and offering shares features (C5, C6) can be zero but not negative

**Textual Characteristics (T colums)**
- Number of sentences (T1), words (T2), and real words (T3) cannot contain any zero or negative values 
- Number of words must be bigger than all other T and S features
- It is possible for the number of long words (T4) and sentences (T5) to be zero but it cannot be negative
- Number of sentences must bigger than long sentences

**Sentiment characteristics (S columns)**
- Number of positive (S1), negative (S2), and uncertain (S3) words can be zero but cannot be negative or lower than the number of words

**Note**
- We we will derive our target features from P columns, meaning, we cannot use in our modeling as they are so called force predictors or "leakers"
- Other features will be calculated after cleaning
