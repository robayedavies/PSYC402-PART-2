---
output:
  html_document: default
  pdf_document: default
---




```
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──
```

```
## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
## ✓ tibble  3.1.2     ✓ dplyr   1.0.7
## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
## ✓ readr   1.4.0     ✓ forcats 0.5.1
```

```
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```




> Rob Davies

# PSYC402 Part 2 Week 16

## Welcome

Welcome to your overview of the materials and guidance you will work with in **PSYC402 Week 16**.

We will complete four classes in weeks 16-19.
These classes are designed to help students to revise and put into practice some of the key ideas and skills you have been developing in the first year research methods modules *PSYC121, PSYC123 and PSYC124*.

We will do this in the context of a live research project with potential real world impacts: the **Clearly understood** project.

Our focus will be on **what makes it easy or difficult for people to understand written health information**.
We encounter written health information all the time: in warnings signs, on medication labels, in clinics when we go to see the doctor, and online when we research things we are worried about.
It is not always easy to understand this information.
The problem is that it is unclear how health information should be communicated.
As psychologists, we can help to improve health communication.

In these classes, we will complete a research project to answer the research questions:

1. What person attributes predict success in understanding?
2. Can people accurately evaluate whether they correctly understand written health information?

We will present our PSYC402 lessons in the context of this research project because we think that this *context* will help you to make sense of the data, and to see why we ask you to practice the skills we are teaching.

We will be revisiting some of the ideas and techniques you have seen introduced in previous classes.
This is to give you the opportunity to revise and consolidate your learning.
We will be extending your development with some new ideas, to strengthen your skills.

Ultimately, we aim to contribute new findings from the data we will collect together.
These new findings will, we hope, help to make the provision of health advice a bit more useful in future.

## Our learning goals

In Week 16, we will ask you to do two things.

First, we will ask you to do a pre-lab activity that involves completing a survey.
Completing the survey will help you to make sense of the numbers you will be working with in the activities.
Completing the pre-lab activity will help to teach you about the challenges of measurement, a key aspect of the scientific thinking skills we will help you grow:

- *Scientific thinking*: from concerns to questions to results and critical evaluation

Second, we wil ask you to do a set of practical tasks in the lab activity that are designed to consolidate your learning on *data visualization*.
We will focus on the visualization of data distributions.
We will be:

- Using histograms to examine the distributions of variables;
- And learning to edit the histograms so they are more effective.



## Resources for you

You will see -- below -- links to the lectures, information about the data we will analyze, and an explanation of the activities.

All the links to the lectures, and everything you need for your practical work class can *also* be found in the **Week 16 files** folder on Moodle, here:

[Link to Moodle](https://modules.lancaster.ac.uk/course/view.php?id=35319#section-9){target="_blank"}

## Lectures: video recordings

The lecture material for this week is presented in three parts.
Click on a link and your browser should open a tab showing the *Panopto* video for the lecture part.
(You will need to be on campus or logged in to the university VPN to get access to the videos.)

[Part 1 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=dfdd3c63-d608-446f-9324-ae3f011ad107){target="_blank"}

[Part 2 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=2df8cf1c-f577-4870-816a-ae3f011e841b){target="_blank"}

[Part 3 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=17266295-94df-4b9f-baf3-ae3f012274e5){target="_blank"}

## Readings

We do not provide further reading but you may find it helpful to take another look at the readings provided, previously, for your classes in weeks 11-13.

## Pre-lab activity 1

In weeks 16-19, we will be working together on a research project to investigate how people vary in their response to health advice.
Completing the project involves collecting responses from PSYC402 students.
In our class activities, we can then analyze the data we collect.

To enter your responses, we invite you to complete a short survey.
You can complete the survey here (just click on the web address to get started):

[Complete the survey](https://lancasteruni.eu.qualtrics.com/jfe/form/SV_0ww8HHxx172TPJs){target="_blank"}

### Survey information

The survey asks you to:

- complete some questions about who you are;
- and then answer some questions about what you know about some English words, about what you know about health matters, and about how you approach reading.

The survey then asks you to:

- read five short extracts from patient information leaflets about different kinds of health issue;
- respond to some multiple choice questions about each extract;
- and rate how well you think you understand the advice.

The survey should take about 20 minutes to complete.
Some people will take less time, and some people might take a little more time.

Taking part in the survey is **completely voluntary**.
You can stop at any time without completing the survey if you do not want to finish it.
If you do not want to do the survey, you can do an alternative activity (see below).

All responses will be recorded completely anonymously.

## Pre-lab activity 1 alternative

If you do not want to complete the survey, we invite you to read the pre-registered research plan for the *PSYC402 health advice* research project.

[Read the project pre-registration](https://osf.io/p6fsc/){target="_blank"}

## Pre-lab activity 2: Getting ready for the lab class

### Get your files ready

Download the [122_week16_forStudents.zip](files/week-16/122_week16_forStudents.zip) files you need and upload them to your RStudio Server.

The folder includes data files:

- `study-one-general-participants.csv`
- `study-two-general-participants.csv`

and code files:

- `2021-22-PSYC402-w16-activity.R`
- `2021-22-PSYC402-w16-how-to.R`

You will use `2021-22-PSYC402-w16-how-to.R` in the lab activity.

### Review the how-to guide

We show you how to do everything you need to do in the lab activity (see the next section) in the `how-to` guide.

The guide comprises an .R file `2021-22-PSYC402-w16-how-to.R` with code and advice, and a video showing you how the code works.
The code in the .R file was written to work with the data file `study-one-general-participants.csv`.

In the video, I work my way through the R code, step-by-step, explaining what each line of code does.
Watching the video takes about 20 minutes.
It is completely optional but I have provided the video because students have told us they find it useful.

[Watch the how-to guide](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=fc290f97-5085-4b92-8870-ae3f01294230){target="_blank"}

## Lab activity

In the lab activity .R file `2021-22-PSYC402-w16-activity.R`, you will work with data from a study about how people respond to guidance about a variety of health topics (general topics):

- `study-two-general-participants.csv`

The data are similar in format to the response data we are collecting as part of the PSYC402 project.

The activity .R file and the data .csv file can be downloaded from:

[122_week16_forStudents.zip](files/week-16/122_week16_forStudents.zip)

Or you can download it from the module Moodle page for PSYC402:

[Link to Moodle](https://modules.lancaster.ac.uk/course/view.php?id=35319#section-9){target="_blank"}

### What is in the activity .R file?

We will take things step-by-step.
We will split .R scripts into parts, tasks and questions:  

- different parts for different phases of the analysis workflow;
- different tasks for different steps in each phase;
- different questions to examine different ideas or coding steps.

### Tasks

In the activity, we are going to work through the following tasks.

1. Empty the R environment -- using `rm(list=ls())`
2. Load relevant libraries -- using `library()`
3. Read in the data file -- using `read_csv()`
4. Inspect the data -- using `head()` and `summary()`
5. Change the type classification of a variable in the data -- using `as.factor()`
6. Draw histograms to examine the distributions of variables -- using `ggplot()` and `geom_histogram()`
7. Edit the appearance of *one variable* histogram plot step-by-step

The activity `2021-22-PSYC402-w16-activity.R` file takes you through the tasks, one by one.

If you are unsure about what you need to do, check in the `how-to` guide: look at the advice in `2021-22-PSYC402-w16-how-to.R` or watch the accompanying video.

You will see that you can match a task in the `activity` to the same task in the `how-to`.
The `how-to` shows you what function you need and how you should write the function code.
You will need to change the names of the dataset or the variables to complete the tasks in the activity.

This process of adapting demonstration code is a process critical to data literacy and to effective problem solving in working with data in psychological science.

### What is in the data files

Each of the data files we will work with has a similar structure.

```r
# head(study.two.gen)
```

You can see the columns:

- `participant_ID` participant code
- `mean.acc` average accuracy of response to questions testing understanding of health guidance
- `mean.self` average self-rated accuracy of understanding of health guidance
- `study` varianble coding for what study the data were collected in
- `AGE` age in years
- `HLVA` health literacy test score
- `SHIPLEY` vocabulary knowledge test score
- `FACTOR3` reading strategy survey score
- `GENDER` gender code
- `EDUCATION` education level code
- `ETHNICITY` ethnicity (Office National Statistics categories) code
