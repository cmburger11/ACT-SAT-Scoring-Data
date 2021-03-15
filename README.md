
# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Problem Statement

Some states require the SAT be taken, some require the ACT be taken and other do not require either.
<<<<<<< HEAD
Is there any correlations between participation rate and/or scores for either of these tests in States where they are Required vs. States where they are not?
=======
Are there any correlations between participation rate and/or scores for either of these tests in States where they are Required vs. States where they are not?
>>>>>>> 4c1d7003b1f287306d13b05dcab02acd89ecc433

---
### Background Research & Sources

The states that require ACT or SAT have changed over the years due to legislation, SAT/ACT being pushed, etc. Based on the article 'Does your State require the SAT and ACT?' from testive.com, the following states require either the SAT or the ACT (from 2018 year): States that require the SAT are Colorado, Connecticut, Delaware, District of Columbia, Idaho, Illinois, Maine, Michigan, New Hampshire, Ohio, and Tennessee. States that require the ACT are Alabama, Hawaii, Idaho, Kentucky, Louisiana, Mississippi, Missouri, Montana, Nebraska, Nevada, North Carolina, North Dakota, Ohio, South Carolina, Tennessee, Utah, Wisconsin and Wyoming.

Again, based on the problem statement, I am going to determine if there is any correlation between the ACT and SAT participation rates vs. scores in these states.

---
### Datasets Used

act_19 = pd.read_csv (r'..\data\act_2019.csv')
-ACT Test Participation Rate and Composite/Average Score from the students that took it from All 50 States (Year of 2019)

sat_19 = pd.read_csv (r'..\data\sat_2019.csv')
-SAT Test Participation Rate and Average Score(s) from the 50 states (Year of 2019)

college = pd.read_csv (r'..\data\sat_act_by_college.csv')
-Shows colleges and Information regarding Acceptance Rate, SAT and ACT scores, among other things.

tests_merged = pd.read_csv (r'..\code\tests_merged.csv')
-Merged ACT 2019 with SAT 2019 to show them side by side vs. separately

ivy_league = pd.read_csv (r'..\code\ivy_league.csv')
-Shows the same info as tests_merged but only Ivy League schools, pulled from tests_merged.csv

act_reqd = pd.read_csv (r'..\code\ACT_Required.csv')
-Shows ACT 2019 data only for States that require the ACT test.

act_not_reqd = pd.read_csv (r'..\code\ACT_not_Required.csv')
-Shows ACT 2019 data for all other States/States that do not Require the ACT Test be taken

sat_reqd = pd.read_csv (r'..\code\SAT_Required.csv')
-Shows SAT 2019 data only for States that require the SAT test

sat_not_reqd = pd.read_csv (r'..\code\SAT_not_Required.csv')
-Shows SAT 2019 data for all other States/States that do not Require the SAT Test be taken

---

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|act_19|States included in the ACT 2019 dataset|
|**act_participation**|*float*|act_19|Participation rate on the 2019 ACT|
|**act_composite_score**|*float*|act_19|Average student composite scores on the 2019 ACT|
|**state**|*object*|sat_19|States included in the ACT 2019 dataset|
|**sat_participation**|*float*|sat_19|SAT 2019 Participation Rate|
|**sat_reading_writing_score**|*int*|sat_19|2019 SAT Evidence Based Reading & Writing Scores|
|**sat_math_score**|*int*|sat_19|2019 SAT Math Scores|
|**sat_total_score**|*int*|sat_19|2019 SAT Total Score|
|**state**|*object*|tests_merged|States for both 2019 ACTs and SATs|
|**act_participation**|*float*|tests_merged|Participation rate on the 2019 ACT|
|**act_composite_score**|*float*|tests_merged|Average student composite scores on the 2019 ACT|
|**sat_participation**|*float*|tests_merged|SAT 2019 Participation Rate|
|**sat_reading_writing_score**|*int*|tests_merged|2019 SAT Evidence Based Reading & Writing Scores|
|**sat_math_score**|*int*|tests_merged|2019 SAT Math Scores|
|**sat_total_score**|*int*|tests_merged|2019 SAT Total Score|
|**state**|*object*|act_reqd|States that require the ACTs|
|**act_participation**|*float*|act_reqd|Participation rate on the ACT in States that Require it|
|**act_composite_score**|*float*|act_reqd|Average student composite scores on the ACT in States that Require it|
|**sat_participation**|*float*|act_reqd|SAT 2019 Participation Rate in States that Require the ACT|
|**sat_reading_writing_score**|*int*|act_reqd|2019 SAT Evidence Based Reading & Writing Scores in States that Require the ACT|
|**sat_math_score**|*int*|act_reqd|2019 SAT Math Scores in States that Require the ACT|
|**sat_total_score**|*int*|act_reqd|2019 SAT Total Score in States that Require the ACT|
|**state**|*object*|act_not_reqd|States that Don't require the ACT|
|**act_participation**|*float*|act_not_reqd|Participation rate on the ACT in States that Don't Require it|
|**act_composite_score**|*float*|act_not_reqd|Average student composite scores on the 2019 ACT in States that Don't Require it|
|**sat_participation**|*float*|act_not_reqd|SAT 2019 Participation Rate in States that Don't Require the ACT|
|**sat_reading_writing_score**|*int*|act_not_reqd|2019 SAT Evidence Based Reading & Writing Scores in States that Don't Require the ACT|
|**sat_math_score**|*int*|act_not_reqd|2019 SAT Math Scores in States that Don't Require the ACT|
|**sat_total_score**|*int*|act_not_reqd|2019 SAT Total Score in States that Don't Require the ACT|
|**state**|*object*|sat_reqd|States that Require the SAT|
|**act_participation**|*float*|sat_reqd|Participation rate on the ACT in States that Require SAT|
|**act_composite_score**|*float*|sat_reqd|Average student composite scores on the 2019 ACT in States that Require SAT|
|**sat_participation**|*float*|sat_reqd|SAT 2019 Participation Rate in States that Require it|
|**sat_reading_writing_score**|*int*|sat_reqd|2019 SAT Evidence Based Reading & Writing Scores in States that Require it|
|**sat_math_score**|*int*|sat_reqd|2019 SAT Math Scores in States that Require it|
|**sat_total_score**|*int*|sat_reqd|2019 SAT Total Score in States that Require it|
|**state**|*object*|sat_not_reqd|States that Require the SAT|
|**act_participation**|*float*|sat_not_reqd|Participation rate on the ACT in States that Don't Require the SAT|
|**act_composite_score**|*float*|sat_not_reqd|Average student composite scores on the 2019 ACT in States that Don't Require the SAT|
|**sat_participation**|*float*|sat_not_reqd|SAT 2019 Participation Rate in States that Don't Require it|
|**sat_reading_writing_score**|*int*|sat_not_reqd|2019 SAT Evidence Based Reading & Writing Scores in States that Don't Require it|
|**sat_math_score**|*int*|sat_not_reqd|2019 SAT Math Scores in States that Don't Require it|
|**sat_total_score**|*int*|sat_not_reqd|2019 SAT Total Score in States that Don't Require it|
---

### Analysis Summary

I began by importing both the ACT 2019 and SAT 2019 datasets. I then merged them to get a side-by-side comparison in each State. I was originally going to determine whether certain States had better chances of getting into Ivy League schools vs. others but the Ivy League data that I gathered, when compared to the SAT & ACT scores, it was clear that no State's scores fell into any of the Ivy League school's 25th-to-75th percentile range. So, I decided to switch my problem statement to my current one of whether or not there is any change in participation rate and scores for States that require one test or the other. With the new question in mind, I then separated the Merged Tests dataframe into 4 subsets; two for States that Require the ACT and States that do not, as well as two for States that require the SAT and states that do not.
I then analyzed that data to determine by conclusion and graphed my findings primarily with scatterplots to show the results.

---

### Conclusions & Considerations

Ultimately, data shows that states that require testing (for either SAT or ACT) definitely and naturally get higher participation rates but that does not necessarily equate to better scores in either test. Actually, the data shows quite the opposite and in my opinion, this is likely because the states with lower participation likely are composed of test-takers that are passionate about taking that particular test, as it likely is what is needed or preferred by the university that they would like to get into.

I feel that funding should be put towards getting students to take the test that corresponds to whatever test is required or suggested by the College that they would like to attends.

Otherwise, I believe there should be only one, universal test that all colleges accept. Therefore there is only one grading scale vs. 2, which may not represent that student's abilities as good as they could be represented. Would take years of research, trial and error...but I believe it can be done.

---

### Sources Cited:
Does your state require the SAT or ACT?
https://www.testive.com/state-sat-act/
