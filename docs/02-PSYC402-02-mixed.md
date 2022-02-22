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

# PSYC402 Part 2 Week 18

## Welcome

Welcome to our overview of the materials and guidance you will work with in **PSYC402 Week 18** for the **02-mixed** class.



### Targets

Our learning objectives include the development of key concepts and skills.

- **concepts** --	multilevel data and multilevel modeling
- **skills** -- visualization -- examine data within classes (sampling groups)
- **skills** -- run linear models over all data and within each class
- **skills** -- use the `lmer()` function to fit models of multilevel data

We are just getting started.
Our plan will be to build depth and breadth in understanding as we progress over the next few weeks.

## Resources for you

You will see -- below -- links to the lectures, information about the data we will analyze, and an explanation of the activities.

The links and everything you need for your practical work class can *also* be found in the **Week 16 files** folder on Moodle, here:

[Link to Moodle](https://modules.lancaster.ac.uk/course/view.php?id=34085#section-10){target="_blank"}

Our aim is to get started in our development of understanding how to use multilevel of mixed-effects models: we need to learn what they are, when and why they are needed, and how they should be used.

I have prepared materials that I suggest you use in this order:

- **Before the lab session**

1. Take a look at the lecture slides, watch the lecture video. The lecture is designed to work *only* as an outline summary of the materials. Learning will work best if you read the book chapter I wrote on the topic, and work through the exercises in the workbook.R
2. Read the book chapter, at least up to p.11, to get an outline view on the answers to the what, why, when and how questions on multilevel models.
2. Download the week 16 files, and work your way throught the workbook.R, guided by the book chapter, at least as far as reading in the data and tidying it for analysis.

- **In the session**

3. Work through the workbook.R, complete the tasks and answer the questions, in groups, guided by the code tips and the information in the chapter.

- **After the session**

4. Bring your questions to the Q&A session or post questions to the discussion forum.

Be patient with yourself and with the materials. The topic is challenging because it is new but it is very important. The plan is to build up understanding and analysis skill step by step.

### Lectures: video recordings

The lecture material for this week is presented in three parts.
Click on a link and your browser should open a tab showing the *Panopto* video for the lecture part.
(You will need to be on campus or logged in to the university VPN to get access to the videos.)

[Part 1 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=2fa60b12-2eca-4412-8672-acd60104da1d){target="_blank"}

[Part 2 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=7f31cef0-1e39-4712-b2a1-acd601195c78){target="_blank"}

[Part 3 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=58ab0c0c-37be-491f-a9e5-acd6011c38dd){target="_blank"}

### Book chapter

I wrote a book chapter to support PSYC402 students learning about multilevel models.

You can download the chapter here [02-mixed.pdf](files/week-18/02-mixed.pdf).

### Pre-lab activity 1: Get your files ready for the lab class

Activities in the class that goes with this chapter are associated with the following data files:

- `CP study word naming rt 180211.dat`
- `CP study word naming acc 180211.dat`
- `words.items.5 120714 150916.csv`
- `all.subjects 110614-050316-290518.csv`

And the .R code file:

- `402-02-mixed-effects-workbook.R`

A pre-tidied version of the CP study data is available as:

- `long.all.noNAs.csv`

You will use `402-02-mixed-effects-workbook.R` in the lab activity.

### Lab activity

We will take things step-by-step.
We will split .R scripts into parts, tasks and questions:  

- different parts for different phases of the analysis workflow;
- different tasks for different steps in each phase;
- different questions to examine different ideas or coding steps.

### Tasks

In the activity, we are going to work through the following tasks.

1. Load the libraries we need for the exercises
2. Read in the data file we will be using: `BAFACALO_DATASET.RData`
3. We start by selecting the variables we want -- using `select()`
4. Take missing values out of the brazil data -- using `na.omit()`
5. Get R to treat a variable as a type object of the kind required -- using the `as.numeric()` or `as.factor()` functions
6. Experiment with variable coercion
7. Visualize the relationship between portuguese and english grades using a scatterplot
8. Work on editing plots
9. Analyze the relationship between english and portuguese grades in the brazil data -- using `lm()`
10. Exercise: adapt the `lm()` code to do a different analysis
11. Plot the relationship between english and portuguese grades separately for each class using `facet_wrap`
12. Practice your `facet_wrap()` skills
13. Run a linear mixed-effects analysis of the relationship between english and portuguese grades using `lmer()`
14. Exercise mixed-effects model coding

There are some extension exercises you can use to develop your coding skills.

### The data we will work with: Brazilian school children

We will be working with data taken from a study on education outcomes in Brazilian children, reported by Golina and Gomes (2014).
The `BAFACALO_DATASET.RData` data were collected and shared online by Golina and Gomes (2014). 
Information about the background motivating the study, the methods of data collection, along with the dataset itself, can be found in the book chapter, and at the data journal article:

[Golina and Gomes (2014) article](https://openpsychologydata.metajnl.com/articles/10.5334/jopd.af/){target="_blank"}

## References

Golino, H. F., & Gomes, C. M. A. (2014). Psychology data from the “BAFACALO project: The Brazilian Intelligence Battery based on two state-of-the-art models – Carroll’s Model and the CHC model”. *Journal of Open Psychology Data*, 2(1), e6. DOI: http://doi.org/10.5334/jopd.af
