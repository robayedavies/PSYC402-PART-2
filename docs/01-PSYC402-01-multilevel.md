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

Welcome to our overview of the materials and guidance you will work with in **PSYC402 Week 16**.

This week, we shall start to develop skills in using a method or approach that is essential in modern data analysis: *multilevel modeling*.
We are going to invest four weeks in working on this approach.
This investment is designed to give you a specific, important, advantage in your work as a psychologist, or as someone who produces or consumes psychological research.

It is now clear that someone who works in psychological research *has* to know about multilevel or hierarchically structured data, and has to know how to apply multilevel models (or mixed-effects models).
Growth in the popularity of these kinds of analysis has been very very rapid, and it is now, effectively, the standard or default method for professional data analysis in most areas of psychological and other social or clinical sciences (or it soon will be).

<div class="figure">
<img src="01-PSYC402-01-multilevel_files/figure-html/pporteng-1.png" alt="Plot of child English and Portuguese grades, from the Golino and Gomes (2014) dataset, shown separately for each school class" width="576" />
<p class="caption">(\#fig:pporteng)Plot of child English and Portuguese grades, from the Golino and Gomes (2014) dataset, shown separately for each school class</p>
</div>

But, because it is relatively new, many professional psychologists struggle to understand why or how to use these methods effectively.
This means that students who acquire the skill graduate with a clear *employability* advantage.
It also means that we have to take seriously the challenge of learning about these methods.
This is why we will spend a bit of time on them.
In my experience, in over a decade of teaching multilevel models, in working with both students and professionals, we shall need to develop understanding and skills gradually.
We will work patiently, so that we can secure understanding by building our learning through a series of practical examples, increasing the scope of our practical skills, and developing the sophistication of our understanding, step-by-step, as we go.

### The approach we take

We are *not* going to take a mathematical approach to learning about multilevel models.
We do not have to.
The approach we are going to take is:

- **verbal** -- We will talk about the main ideas in words. Sometimes, we will present formulas but that is just to save having to use *too many* words.
- **visual** -- We will show ourselves and each other what multilevel structure in data looks like, and what that structure means for our analyses of behaviour.
- **practical** -- We will use R to complete analyses, so we will learn about coding models in practice. Fortunately, through coding we can get a clear idea of what we want the models to do.

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

[Part 1 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=66e89421-4491-4eb9-b1c8-acd4012a183d){target="_blank"}

[Part 2 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=22361165-636b-424c-9e28-acd4012efd6f){target="_blank"}

[Part 3 of 3](https://dtu-panopto.lancs.ac.uk/Panopto/Pages/Viewer.aspx?id=5942b084-457f-4687-aa3d-acd401332b44){target="_blank"}

### Book chapter

I wrote a book chapter to support PSYC402 students learning about multilevel models.

You can download the chapter here [01-multilevel.pdf](files/week-16/01-multilevel.pdf).

- *Why did I write the chapter: why do I recommend reading the chapter?*

I wrote the chapter to provide students with a summary of the critical ideas that we should start to consider, as we begin to develop understanding and skills in working with multilevel models.
There are many books about multilevel or mixed-effects models but they are, in my view, sometimes too technical, or too mathematical, or they do not provide examples that will appear relevant to PSYC402 students.
This chapter is my attempt to provide you with the information you need, as we get started.
Later chapters will serve to consolidate and to grow the critical ideas as understanding develops.
I include a reference section, at the end, to point you to the source materials I used in writing the chapter, and to present a guide for further reading.

The lectures are designed to present an outline of the main ideas and the critical code moves.
But this are of work is quite advanced, and I believe it would be worthwhile to use the lectures together with the chapter.

### Pre-lab activity 1: Get your files ready for the lab class

Download the [01-multilevel.zip](files/week-16/01-multilevel.zip) files you need and upload them to RStudio Server.

The folder includes the data file:

- `BAFACALO_DATASET.RData`

and code file:

- `402-01-multilevel-workbook.R`

You will use `402-01-multilevel-workbook.R` in the lab activity.

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

### Answers

You can now download the answers version of the practical activity workbook script as: [402-01-multilevel-workbook-with-answers.R](files/week-16/402-01-multilevel-workbook-with-answers.R).

There is an extension section which shows you code for how I fitted a separate model of the relation between English and Portuguese grades for each class, then plotted the model estimates to demonstrate between class differences in intercepts and slopes.

If you have any questions, please post them to the Moodle discussion forum, or to the Friday Q&A slido.

### The data we will work with: Brazilian school children

We will be working with data taken from a study on education outcomes in Brazilian children, reported by Golina and Gomes (2014).
The `BAFACALO_DATASET.RData` data were collected and shared online by Golina and Gomes (2014). 
Information about the background motivating the study, the methods of data collection, along with the dataset itself, can be found in the book chapter, and at the data journal article:

[Golina and Gomes (2014) article](https://openpsychologydata.metajnl.com/articles/10.5334/jopd.af/){target="_blank"}

## References

Golino, H. F., & Gomes, C. M. A. (2014). Psychology data from the “BAFACALO project: The Brazilian Intelligence Battery based on two state-of-the-art models – Carroll’s Model and the CHC model”. *Journal of Open Psychology Data*, 2(1), e6. DOI: http://doi.org/10.5334/jopd.af
