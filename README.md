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

**IPO characteristics (C columns)** can contain 0, less than 0 values but no strings<br>
That is because finance/accounting determinants can be 0 or be negative (e.g. EPS, sales, can be negative and 0)<br>

**Sentiment characteristics (S columns)** can contain 0 values but cannot be less than 0 or have strings<br>
Our assumption is that you cannot have a negative amount of words (we only encountered 2). We decided we will allow 0 values here because there aren't many. Our reasoning this section to contain 0 values is becasue of the difficulty translating sentimental analysis for companies not in the US and lack of data. <br>

**Textual Characteristics (T3-T5 columns )** can contain 0 and less than 0 values but no strings, however, **T1 and T2** (Nbr of sentences, number of words respectively) cannot contain 0, less than 0, and no string values. Our assumption is the same that you simply cannot have a negative or zero amount of words. <br>

**IPO pricing (P columns)** cannot contain 0, less than 0, and string values <br>
This column cannot contain these values because we will use it to calculate the control and target variables. <br>
    
**Note:** P columns are called force predictors or price leakers becasue we use them to calculate target and control variables. Therefore, they will not be included in the model (e.g. it can happen that you get 100% accuracy by including them which is unrealistic). 
