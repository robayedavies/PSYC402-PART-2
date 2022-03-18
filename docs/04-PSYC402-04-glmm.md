---
output:
  html_document: default
  pdf_document: default
---




```
## Loading required package: Matrix
```

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
## x dplyr::combine() masks gridExtra::combine()
## x tidyr::expand()  masks Matrix::expand()
## x dplyr::filter()  masks stats::filter()
## x dplyr::lag()     masks stats::lag()
## x tidyr::pack()    masks Matrix::pack()
## x tidyr::unpack()  masks Matrix::unpack()
```


```
## 
## ── Column specification ────────────────────────────────────────────────────────
## cols(
##   .default = col_double(),
##   subjectID = col_character(),
##   Test = col_character(),
##   Gender = col_character(),
##   Subject = col_character(),
##   item_name = col_character(),
##   item_type = col_character(),
##   SUBTLWF = col_number()
## )
## ℹ Use `spec()` for the full column specifications.
```

> Rob Davies

# PSYC402 Part 2 Week 20

## Welcome

Welcome to our overview of the materials and guidance you will work with in **PSYC402 Week 20** for the **04-glmm** class.

We have been discussing how we can use Linear Mixed-effects models to analyze multilevel structured data, the kind of data that we commonly acquire in experimental psychological studies, for example, when our studies have repeated measures designs. 
The use of Linear Mixed-effects models is appropriate where the outcome variable is a continuous numeric variable like reaction time.
In this chapter, we extend our understanding and skills by moving to examine data where the outcome variable is categorical: this is a context that requires the use of **Generalized Linear Mixed-effects Models (GLMMs)**. 

We will begin by looking at the motivations for using GLMMs.
We will then look at a practical example of a GLMM analysis, in an exploration in which we shall reveal some of the challenges that can arise in such work.
The R code to do the modeling is very similar to the code we have used before. 
The way we can understand the models is also similar but *with one critical difference*.
We start to understand that difference here.

## Objectives

The aims of the lab session work are to:

- understand the reasons for using Generalized Linear Mixed-effects models (GLMMs) when we analyze discrete outcome variables;
- recognize the limitations of alternative methods for analyzing such outcomes;
- practice running GLMMs with varying random effects structures;
- practice reporting the results of GLMMs, including through the use of model plots.

My recommendations for learning are:

- run generalized linear mixed-effects models of demonstration data;
- run generalized linear mixed-effects models of alternate data sets;
- play with the .R code used to create examples for the lecture;
- and edit example code to create alternate visualizations.

## Resources for you

You will see -- below -- links to the lectures, information about the data we will analyze, and an explanation of the activities.

The links and everything you need for your practical work class can *also* be found in the **Week 20** folder on Moodle, here:

[Link to Moodle](https://modules.lancaster.ac.uk/course/view.php?id=34085#section-14){target="_blank"}

I have prepared materials that I suggest you use in this order:

- **Before the lab session**

1. Take a look at the lecture slides, watch the lecture video. The lecture is designed to work *only* as an outline summary of the materials. Learning will work best if you read the book chapter I wrote on the topic, and work through the exercises in the workbook.R
2. Read the book chapter, to develop understanding.
2. Download the week 20 files, and work your way through the workbook.R, guided by the book chapter.

- **In the session**

3. Work through the workbook.R, complete the tasks and answer the questions, in groups, guided by the code tips and the information in the chapter.

- **After the session**

4. Bring your questions to the Q&A session or post questions to the discussion forum.

Be patient with yourself and with the materials. The topic is challenging because it is new but it is very important. The plan is to build up understanding and analysis skill step by step.

5. As an opportunity to gain further experience, I provide a **post-lab** activity, see following.

### Lectures: video recordings

The lecture material for this week is presented in three parts.
Click on a link and your browser should open a tab showing the *Panopto* video for the lecture part.
(You will need to be on campus or logged in to the university VPN to get access to the videos.)

[Part 1 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=bbf38d0e-90e5-4285-82ea-acec012a2f77){target="_blank"}

[Part 2 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=93c898ce-8009-47c6-ad43-acec0130b2ea){target="_blank"}

[Part 3 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=078770df-47d0-4a25-9fdd-acec0135f5ea){target="_blank"}

### Book chapter

I wrote a book chapter to support PSYC402 student learning.

You can download the chapter here [04-glmm.pdf](files/week-20/04-glmm.pdf).

The chapter is useful to you in two ways:

1. I use text and visualization to explain the core ideas in depth;
2. I take you through each part of the code that you need to use, step-by-step, for your development of practical skills in data tidying, visualization, and analysis.

### Pre-lab activity: Get your files ready for the lab class

Download the [04-glmm.zip](files/week-20/04-glmm.zip) files you need.

Activities in the class that goes with this chapter are associated with the following data file:

- `long.orth_2020-08-11.csv`

And the .R code file:

- `402-04-GLMM-workbook.R`

You will use `402-04-GLMM-workbook.R` in the lab activity.

### Lab activity

We will take things step-by-step.

#### Tasks

In the activity, we are going to work through the following tasks.

First, we **prepare the data** for analysis.

1. Load the libraries we need.
2. Read in the data file -- using the `read_csv()` function.
3. Inspect the data -- using `summary()`.
4. We begin to develop awareness of how we approach generalized linear models by fitting some simple models -- using `glm()`.
5. We examine how the different levels of categorical variables are coded, and change the coding -- using `contrasts()` and `contr.sum()`.

Notice that identifying how categorical variables are coded, and modifying the coding as required, is often essential to working with research data from studies involving experimental manipulations or group contrasts.

A useful set of tools for dealing with categorical variables can also be found in the `forcats` library in `tidyverse`.

<https://forcats.tidyverse.org>

Second, we **begin our exploration** of Generalized Linear Mixed-effects Models (GLMMs) by fitting, and examining the results from, a random intercepts model.

6. We run the code to fit the model -- using `glmer()`.
7. Visualize the modeled effect -- using either of two alternative approaches: using `plot_model()` or using `effect()`.
8. Experiment by picking a different predictor variable to visualize.
9. As an optional exercise, I invite you to examine how how to plot interaction effects -- using `plot_model()`; you will need to exploit the information presented in an online guide.

Third, we move into a sequence of activities or exercises designed to expose how you might approach the challenge of fitting models incorporating random effects that are both warranted by the study design (as well as the likely structure of the data) and justified by model fit to data.
I walk you through a sequence of tasks where I show you how to fit and compare a series of models.
The models all have the same fixed effects: we will be comparing models varying in random effects.

10. Fit a minimal random intercepts model, then a maximal model with the full set of random intercepts, slopes and covariances that appear to be justifiable, given the study design for the example dataset. 

**The maximal model will take a relatively long time (several seconds) to fit, so be patient.**

As part of this task, I will ask you to work through a series of variants of the model, so that you can see what it looks like when model variants do or do not converge.

11. Compare the models with the *Likelihood Ratio Test* -- using `anova()`.
12. Experiment a bit with the model specification code to see what key elements are doing -- looking at `glmerControl()` and `dummy()`.

#### The data we will work with: the Ricketts word learning study

We will be working with data collected for a study investigating word learning in children, reported by Ricketts, Dawson, and Davies (2021).
You will see that the study design has both a repeated measures aspect because each child is asked to respond to multiple stimuli, and a longitudinal aspect because responses are recorded at two time points.
Because responses were observed to multiple stimuli for each child, and because responses were recorded at multiple time points, the data have a multilevel structure.
These features require the use of mixed-effects models for analysis.

We will see, also, that the study involves the factorial manipulation of learning conditions.
Children were taught 16 novel words in a $2 \times 2$ factorial design. 
The presence of orthography (orthography absent vs. orthography present) was manipulated within participants: for all children, eight of the words were taught with orthography present and eight with orthography absent. 
Instructions (incidental vs. explicit) were manipulated between participants such that children in the explicit condition were alerted to the presence of orthography whereas children in the incidental condition were not.

Some of the variables included in the .csv file are listed, following, with information about value coding or calculation.

- `Participant` -- Participant identity codes were used to anonymize participation.
- `Time` -- Test time was coded 1 (time 1) or 2 (time 2). For the Study 1 longitudinal data, it can be seen that each participant identity code is associated with observations taken at test times 1 and 2.
- `Instructions` -- Variable coding for whether participants undertook training in the *explicit* or *incidental* conditions.
- `Word` -- Letter string values showing the words presented as stimuli to the children.
- `Orthography` -- Variable coding for whether participants had seen a word in training in the orthography *absent* or *present* conditions.
- `Consistency-H` -- Calculated orthography-to-phonology consistency value for each word.
- `zConsistency-H` -- Standardized Consistency H scores
- `Score` -- Outcome variable -- for the orthographic post-test, responses were scored as: `1` correct, if the target spelling was produced in full; or `0` incorrect, if the target spelling was not produced

### Post-lab activity

Notice that when you download the [04-glmm.zip](files/week-20/04-glmm.zip) files you will find that there are two files you can use for post-lab extension work=.

- `402-04-GLMM-exercise-gavagai-data-analysis-notes.R`
- `noun-verb-learning-study.csv`

It is very helpful, when learning new data analysis methods, to examine how you use the *same* method in *different* contexts, with different study designs, research questions, datasets, and challenges.
You can use these resources, optionally, to extend your practice and deepen your understanding, by exploring the analysis of the noun-verb learning "Gavagai" study data (Monaghan et al., 2015).
The .R analysis script is extensively commented.
You can find further information about the study in the script or in the associated published article.

## References

Monaghan, P., Mattock, K., Davies, R. A., \& Smith, A. C. (2015). Gavagai is as gavagai does: Learning nouns and verbs from Cross‐Situational statistics. Cognitive Science, 39, 1099-1112.

Ricketts, J., Dawson, N., \& Davies, R. (2021). The hidden depths of new word knowledge: Using graded measures of orthographic and semantic learning to measure vocabulary acquisition. *Learning and Instruction*, 74, 101468.

Notice that data and code shared with the Ricketts et al. (2021) manuscript can be found at the publication webpage:
<https://www.sciencedirect.com/science/article/pii/S095947522100027X>
