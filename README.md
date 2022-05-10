# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Civic data analysis

### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

### Problem Statement

The mayor wants to start a new initiative to move the needle on high school education outcomes. With the data on SAT and ACT standardized testing along with data on California Colleges, we will look at at how the two tests compare. We will determine which test is more popular, how average test scores vary between the two tests, and which test gives students a better chance of being accepted in colleges. 

---

### Executive Summary

Initially we import data from ACT and SAT test scores for each state from 2017, 2018, 2019 along with data from california ACT/SAT testing and College ACT/SAT test scores. We then clean our data by dropping unnecessary columns and correcting data types and Null values in order to perform functions over them. Our data analysis looks into trends in SAT/ACT participation rates, average scores, and college admissions based on SAT/ACT test scores. Ultimately we reveal why the SAT is a better choice for students to focus on in order to improve their chances of being admitted into colleges of varying acception rates. 

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|act_merged|US State| 
|**part_*year***|*float*|act_merged|Percentange of ACT test takers in ***year*** (2017, 2018, 2019) i.e. **part_17, part_18, part_19**| 
|**comp_*year***|*float*|act_merged|Avg ACT composite score in  in ***year*** (2017, 2018, 2019) i.e. **comp_17, comp_18, comp_19**| 
|**state**|*object*|sat_merged|US State|
|**part_*year***|*float*|sat_merged|Percentange of SAT test takers in ***year*** (2017, 2018, 2019) i.e. **part_17, part_18, part_19**|
|**EBRW_*year***|*float*|sat_merged|Avg SAT Evidence-Based Reading and writing score in ***year*** (2017, 2018, 2019) i.e. **EBRW_17, EBRW_18, EBRW_19**|
|**math_*year***|*float*|sat_merged|Avg SAT Math score in ***year*** (2017, 2018, 2019) i.e. **math_17, math_18, math_19**|
|**total_*year***|*float*|sat_merged|Avg SAT Total score in ***year*** (2017, 2018, 2019) i.e. **total_17, total_18, total_19**|
|**CDS**|*float*|sat_act_19_ca|Unique identifier for school|
|**record_type**|*object*|sat_act_19_ca|Record type: County, District, School (C, D, S)|
|**school**|*object*|sat_act_19_ca|School Name|
|**disctrict**|*object*|sat_act_19_ca|District of School|
|**city**|*object*|sat_act_19_ca|City Name|
|**enroll_12**|*float*|sat_act_19_ca|Number of Seniors enrolled|
|**sat_part**|*float*|sat_act_19_ca|Number of students who took SAT test|
|**sat_rate_pass**|*float*|sat_act_19_ca|Rate of students that passed SAT|
|**act_part**|*float*|sat_act_19_ca|Number of students who took the SAT|
|**act_rate_over_20**|*float*|sat_act_19_ca|Rate of students who passed ACT|
|**act_avg_read**|*float*|sat_act_19_ca|Average score for Read section of ACT|
|**act_avg_eng**|*float*|sat_act_19_ca|Average score for English section of ACT|
|**act_avg_math**|*float*|sat_act_19_ca|Average score for Math section of ACT|
|**act_avg_sci**|*float*|sat_act_19_ca|Average score for Science section of ACT. This section was excluded when comparing SAT to ACT Math sections |
|**act_avg_score**|*float*|sat_act_19_ca|Average Composite score for ACT|
|**school**|*object*|sat_act_19_ca|School Name|
|**optional**|*object*|sat_act_19_ca|Test Optional|
|**year_apply**|*object*|sat_act_19_ca|Year the policy applies to|
|**policy**|*object*|sat_act_19_ca|Test policy|
|**num_applicants**|*int*|sat_act_19_ca|Number of applicants to school|
|**accept_rate**|*object*|sat_act_19_ca|Rate of acceptance|
|**sat_q1**|*float*|sat_act_19_ca|25% Pecentile of SAT scores|
|**sat_q3**|*float*|sat_act_19_ca|75% Percentile of SAT scores|
|**act_q1**|*float*|sat_act_19_ca|25% Percentile of ACT scores|
|**act_q3**|*float*|sat_act_19_ca|75% Percentile of ACT scores|
|**test_blind**|*float*|sat_act_19_ca|Schools that do not look at standardized test scores|
|**accept_tiers**|*float*|sat_act_19_ca|Acceptance rates grouped in range 5%, 10%, 15%, 25%, 50%, 75%, 100%|
|**sat_q1_perc**|*float*|sat_act_19_ca|SAT score percentage for 25% Percentile scores|
|**act_q1_perc**|*float*|sat_act_19_ca|ACT scores percentage for 75% Percentile scores|
|**sat_q2**|*float*|sat_act_19_ca|Presumed median SAT score. Median cannot be correctly calculated from interquartile range|
|**act_q2**|*float*|sat_act_19_ca|Presumed median ACT score. Median cannot be correctly calculated from interquartile range|
|**accept_tiers**|*float*|coll_tiers_nat_avg|Acceptance rates grouped in range 5%, 10%, 15%, 25%, 50%, 75%, 100%|
|**act_q1_diff**|*float*|coll_tiers_nat_avg|Difference of 25% Perntile ACT score percentage from National Average|
|**sat_q1_diff**|*float*|coll_tiers_nat_avg|Difference of 25% Perntile SAT score percentage from National Average|
|**act_q1**|*float*|coll_tiers_nat_avg|Colleges' 25% Percentile ACT Score|
|**sat_q1**|*float*|coll_tiers_nat_avg|Colleges' 75% Percentile ACT Score|

### Conclusions and Recommendations

Based on the data on states' participation rates and average scores for the ACT and SAT standardized tests we are able to clearly see that there is a trend of SAT gaining popularity over the ACT. Average test scores overall are higher for the SAT than the ACT. 

The data on college test scores leads to the conclusion that the lower 25% of acceptable SAT test scores are closer to the SAT national average than the ACT lower 25% scores are to the ACT national average. This suggests that it is advantageous for students to take the SAT over the ACT. 

We categorized colleges based on their acceptance rates and provided the lower 25% SAT and ACT scores for each category. This information is meant to be used as target points for students. If a student wishes to get into a college with a lower acceptance rate and higher acceptable test score, they can use this information to understand by how much they need to improve their scores. 

We recommend providing students with resources for practice testing in order to gauge their standing in relation to this scale of college admission test scores. The SAT has the added benefit of allowing Junior students to take the test. Students should be advised to take the SAT in their junior year to introduce them to the standardized test as early as possible. 

Requiring students to take the either standardized test results in an overall lower average score. This correlation is due to a larger sample size and presumably less willingness to participate in standardized testing. Further study would be required to analyze how these states requiring students participate in order to reach any conclusions on the those students performance and how to improve their results. 

---
  - More on the *structure of your submission repo* [here][deliverables]
- Students should demonstrate the ability to:
