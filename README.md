# r_sample

## Dataset Description

From 2009 to 2016, a cluster randomized controlled trial was implemented by several researchers to study the impact of local banks’ 
expansion on households’ loans, savings, and insurance talking behavior. The research project sought to evaluate the impact of the 
intervention on a wide range of outcomes that reflect household well-being (e.g. household income, consumption), as well as individual 
well-being (e.g. women’s empowerment, health). The research implementation partner was a large financial institution in rural South India 
that randomly expanded bank infrastructure across rural villages (called service areas) in 3 districts of Tamil Nadu, India. In 2009, 101
service areas over three districts were identified, which formed 50 service area pairs. One service area “pair” is a triplet, containing 
one treatment area and two control area. 50 treatment areas and 51 control areas given a total of 101 service areas. A bank branch was 
assigned to each service area, and the bank opened branches in the treatment group service area at the time of assignment, while expansion
into the control group areas after 18-24 months later. More than 4,000 households were randomly selected across all service areas to be 
included in the study. The opening of bank branches happened in three rounds. Thus, there are three baseline surveys, and three endline surveys.

## Codebook

There are three main data files in the "01 Data" folder: 

1. treatment_status.csv
    * pair_id: uniquely identifies a service area control and treatment pair
    * group_id: uniquely identifies one service area
    * treated: indicator ==1 denoting a member of the treatment group

2. endline.dta
    * hhid: unique identifier for each household
    * totformalborrow_24: total formal borrowed amount (loans) in India Rupees in the past 24 months
    * totinformalborrow_24: total informal borrowed amount (loans) in India Rupees in the past 24 months
    * hhinc: self-reported total household income in the last 30 days
    * survey_round: the round of the survey, either endline 1, 2 or 3.
    * hhnomembers: Number of household members in each household

3. baseline_controls.dta: This dataset contains baseline household demographics including gender, age, education of head of household, 
household religions and household caste.

## Analysis Description

1. Data Preparation
      a. Clean the endline data and generate relevant variables
      b. Merge the endline data with the treatment_status dataset
      c. Merge the working data with the baseline controls dataset, and save the merged data.

2. Analysis
      a. Establish a testable hypothesis about the possible effects of this program
      b. Check balance between the treatment and control groups using baseline household variables
      c. Regress (with OLS) the household income and log household income on the treatment dummy, including 
      pair fixed effects, and standard errors clustered at the appropriate level 
      e. Re-run the previous regression including a set of household-level controls and export and save a regression table 
      suitable for publication from these results
      f. Create a bar chart suitable for publication that summarizes the average borrowed amount for each income quartile,
      by treatment group.
      
## Description of Folders

* 01 Data: Contains the .csv and .dta files for endline data, treatment status, and baseline controls, as well as the merged data  
* 02 Output: Contains the R markdown in .docx format and the regression output from the analysis described above 
* 03 Figures: Contains the bar chart for mean amt. borrowed by income quantile and treatment group in .png format 
* 04 Code: Contains the code to perform the described analysis in .rmd format
