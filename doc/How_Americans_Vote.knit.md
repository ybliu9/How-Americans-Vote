
<!-- rnb-text-begin -->

---
title: "How Americans Vote"
author: "Yibai Liu"
date: "1/24/2021"
output: html_notebook
---


<!-- rnb-text-end -->



<!-- rnb-text-begin -->



<!-- rnb-text-end -->



<!-- rnb-text-begin -->


The 2020 US Presidential Election has settled with Donald Trump losing his bid for re-election. Recalling Trump's electoral college edge in the 2016 Election, his failure in securing his second term was seemingly accounted for by many major events especially those happened in the election year 2020. Among them, the Covid-19 pandemic was definitely the most important event that has hit the world hard and brought about drastic impacts to everyone. As a result, I had raised the following questions: 
    **What factors might explain Trump's loss of his re-election? **
    **Did Americans change their minds in 2020 with the outbreak of the Covid-19?**
To answer these questions, I analyzed survey responses gathered in the 2019 and 2020 pilot studies conducted by [American National Election Studies (ANES)](https://electionstudies.org/). ANES collects non-partisan web survey data about American voters covering their opinions on political and social issues, which provides possible explanations of election results. For the two pilot studies I focused on in this analysis, all respondents are US citizens aged 18 or older who were eligible to vote in 2020. 

## 1. About the data

<!-- rnb-text-end -->



<!-- rnb-text-begin -->


For the 2019 pilot study, the field period was Dec. 20 ~ 31, 2019, while the period for the 2020 study was Apr.10 ~ 18, 2020. The number of effective records for the 2019 and 2020 surveys were 3,165 and 3,080, respectively. Regarding missing values, we can tell from the plots below that 60 out of 900 variables of the 2019 pilot study data had missing values among which 45 were version control variables. In contrast, the 2020 survey did better in reducing missingness. Missing values and version control variables were assigned with special codes, thus out of 470 variables, the 2020 pilot study dataset only had three NAs in 2 variables.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## 2. Data cleaning and processing

By carefully reading through the codebooks for two studies, I processed and cleaned some variables, for example, merged responses from different versions/forms, recoded bipolar rating scales, reordered nominal variables (such as respondent race), organized special values assigned to inapplicable questions or missing responses, etc. to keep two studies consistent. 

Besides, there was a section called Trump Job Approval which asked about respondent's evaluation on Trump's work as president in several aspects. Two questions about covid-19 and healthcare asked in the 2020 survey were not applicable for the 2019 survey, but in order to get a clearer idea about how people think, I kept the two questions in the analysis and filled the respective columns with value -1 in the 2019 dataset.  


<!-- rnb-text-end -->



<!-- rnb-text-begin -->


After having a close look at the questionnaires and the result variables for both years, I picked some relevant questions commonly asked in both surveys for comparison, and I paired and listed these response variables along with detailed descriptions in the file **anes_var_ref.csv** under the `/data/` folder. These common variables were extracted from two cleaned datasets and binded together by adding a `year` variable. Besides, I selected additional questions about Covid-19 that were covered only in the 2020 survey, then I extracted a separate subset of the 2020 dataset for covid-19 related responses. 
You can find the output datasets **anes_bind** and **anes_2020_covid** in '.csv' format under the `/output/` folder.


<!-- rnb-text-end -->



<!-- rnb-text-begin -->



<!-- rnb-text-end -->






<!-- rnb-text-begin -->


## 3. What factors might explain Trump's loss in the 2020 US Presidential Election?

### 3.1 Losing votes from previous supporters in the last election

![](https://raw.githubusercontent.com/ybliu9/How-Americans-Vote/master/figs/vote16.png){width=75%}
In the two studies, based on respondents' answers to the common question `vote16` above regarding turnout and candidate choices in the 2016 Presidential Election, 4,985 out of 6,245 survey participants reported that they voted in 2016, which the overall turnout rate was 79.8%. We can say that the sizes of two groups supporting Trump vs. Hillary in 2016 were approximately equal as 2,325 voted for Donald Trump and 2,204 voted for Hillary Clinton, while Trump won a small margin. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


I compared the two groups to see 1) if they were different in certain ways and 2) whether they would keep their choices or change their minds in the 2020 Election. The horizontal barchart below displays when being asked **"If the 2020 US Presidential Election were between Donald Trump and Joe Biden, would you vote for Donald Trump, Joe Biden, someone else, or probably not vote?"**, how participants of the 2019 vs. 2020 study answered. It is clear that the vast majority of people were likely to stick with their choice in 2016 and vote for the same party in 2020. However, for the group voted for Trump in 2016, the proportion of respondents expected to keep voting for Trump **decreased** from 93% in 2019's survey to 89% in 2019's survey. Although the demographics of respondents were not exactly the same in two studies, since Democrats' supports did not swing much, this probably implies that some of Trump's supporters have changed their minds from 2019 to 2020. Losing votes from some of his old supporters is probably one factor to explain why Trump failed his re-election. 

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Also, if solely looking at Trump's supporters in 2016 and taking into account their race, we can tell from the mosaic plot below that **white people** probably made the majority of the votes Trump won in 2016, while Asians and Black people did not contribute much. However, for **all** races, the proportions of his supporters expected to stay with him in the 2020 election have **decreased** from the 2019's survey to the 2020's survey. Biden's popularity among all races seemed to climb up from 2019 to 2020. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


### 3.2 Disapproval of Trump's work


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


As the diverging bar chart shown above, I divided the responses into four groups by year and by retrospective candidate choice in 2016, as discussed earlier. On the left, the respondents voted for Trump in 2016, while respondents on the right half of the plot used to vote for Clinton in 2016. In the 2020 pilot study, two additional questions about covid-19 and healthcare were asked, and respondents were randomly assigned to one of the questions.
It is clear that these groups had bipolar evaluations on President Trump's work in every aspect. The vast majority of Trump's supporters were satisfied with Trump's work in all aspects being asked about, however, in the 2020 survey, some of Trump's supporters appeared to disapprove Trump's way of handling Covid-19 and/or healthcare. There were also some swings among respondents who voted for Clinton in the 2020 survey. From 2019 to 2020, more of Trump's supporters turned to feel disappointed about Trump's job, and this might become a cause for Trump to be defeated in the 2020 Presidential Election. 

## 4. Impacts of Covid-19 in the election year 2020 

In the 2020 pilot study, respondents were asked about concerns about the Covid-19 pandemic. Dividing the participants into two groups based on their expected candidate choice in the 2020 Election, we can see how they view the Covid-19 differently. The two mosaic plots below displayed respondents' answers to two Covid-19 related survey questions. The first question was: **"How worried are you personally about getting the COVID-19?"**, and the second question was: **"How worried are you about the economic impact of the COVID-19?"**
In general, it seemed that people expected to vote for Biden had higher levels of concerns about the Covid-19, which few responded with no concerns at all. Another noticeable finding is that people seemed to be more worried about the economic disruption than the health threats caused by the Covid-19. This result was reasonable because the last response of the 2020 exploratory testing survey was recorded on Apr.18, 2020, at the time when people had witnessed unprecedented meltdowns of stock markets but there were not as many cases. Concerns about the Covid-19 might lead voters to turn their back on Trump due to Trump government's poor responses to Covid-19.  


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## 5. Conclusion

Based on the analysis, the vast majority of Trump's supporters were satisfied with Trump's work and were likely going to vote for him again in 2020. In spite of disputes, Trump enjoyed strong support from people who voted for him, however, he seemed have lost some votes from previous supporters. The Covid-19 pandemic had made Trump's tenure even harder, as more supporters disapproved him and turned their back on him. These are all possible explanations on why Trump was defeated by Biden in the 2020 Presidential Election.

## 6. Issues and potential biases

Because the ANES pilot studies depended on web surveys which respondents earn redeemable points by completing the survey, there is an inevitable chance that participants might not take the survey serious or answer questions honestly, resulting to response biases. For example, when cleaning the responses, I saw consecutive identical values, and this might decrease the survey quality and harm the generalization of the studies. In addition, since the survey was only assigned by matching eligible people who are American citizens aged 18 or older, the sampling might not be random, which can lead to non-response bias. More potential issues about the datasets would need to be considered and discussed. 

<!-- rnb-text-end -->

