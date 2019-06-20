---
title: "Data Cleaning"
title: "Data Cleaning"
date: 2019-06-06T18:01:45-04:00
draft: false
weight: 15
---

Data being in a tabular format offers a tremendous advantage when it comes to doing data science. However just because our data is in a table doesn't mean that it's really ready for analysis. Sometimes the data that we receive can consist of inconsistencies and gaps that can make the underlying analysis difficult or downright impossible to do. 

**Data cleaning** refers to the process of detecting and correcting these problems from a data set. **Data cleaning** is a very common processing step in the data science pipeline. 

Unfortunately for data scientists there are an endless amount of ways that our data can have problems. In this lesson and in the end of Chapter 7 , we will touch on some of these problems and suggest ways to solve them. 

Before we do that, let's introduce another dataset, this time one that suffers from "messiness". 

Every year, groups of anxious New York City parents wait for the results of NYC's **Gifted and Talented Test**,  an exam  for K-3rd grade children that controls the admissions for the city's **Gifted and Talented Program **(G&T) . Getting into G&T can be a big deal, certain well funded early education schools are limited to those only in the program. 

![This image is a picture of New York City's Department of Education logo. ](NYC.png)

There's a certain level of uncertainity on what score is necessary in order to get into G&T (the cutoff changes every year and NYC doesn't publicly share the information for a variety of reasons). In an attempt to solve this uncertainity parents have crowdsourced their own child's score resuts on online spreadsheets . Below is a snapshot of the data collected by New York City families.

| Entering Grade Level | Month     | OLSAT Verbal Score | NNAT Non Verbal Raw Score | Overall Score | School Preferences          |
| -------------------- | --------- | ------------------ | ------------------------- | ------------- | --------------------------- |
| 1                    | september | 28                 | 45                        | 99            | NEST+m, TAG, Anderson, Q300 |
| K                    | August    | 25                 | 39                        | 99            | Anderson, NEST+m            |
| 1                    | March     | 27                 | 42                        | 98            | NaN                         |
| K                    | September | 23                 | 40                        | 98            | NaN                         |
| K                    | April     | 25                 | 38                        | 99            | Brooklyn School of Inquiry  |

It might be possible to tell right away that this data isn't nearly as "clean" as the LEGO dataset that was introduced earlier in this chapter. However, by using `pandas` we can get closer to "cleanliness" we may need to do data analysis. 

There are six **columns** in the dataset: 

- **Entering Grade Level** descibes the grade level that the student is about to go into and ranges from Kindergarden to 3rd grade. 
- **Month** describes the month that the child was born. 
- **OLSAT Verbal Score** describes the score result of one of the two tests required in the G&T examination process 
- **NNAT Non Verbal Raw Score** describes the score result of one of the two tests required in the G&T examination process. 
- **Overall Score** is a curved score given based on the results of the OLSAT and NNAT. 
- **School Preferences** is the written parental preference for schooling given that the student gets into the G&T program.

Each **row** describes the attributes of one child. 

Let's start with some of the values in the data itself, specifically the `NaN` value. Unsuprisingly, there is no school in the NYC School district called `NaN`, instead Pandas uses `Nan` (Not a Number) to fill out columns values in rows where there is no data inputed. Unfortunately for us some parents didn't bother to fill out the column value that asked for what school they prefered their child to attend if they were to get into G&T. 

What should we do about this? One strategy that can we try, (especially if the existence of `NaN` is rare and most parents followed the online directions), is to drop any rows with missing data.

~~~python
nyc_testscores = pd.read_csv("G&T.csv")
nyc_testscores.dropna()
~~~

Unfortunately for us, `NaN` isn't rare and 34% of parents didn't bother filling out their School Preferences. It might still make sense to get rid of the `NaN` rows depending on what questions we want to ask about our data. (Such as if we want to do an analysis specifically on the schools that parents are prefering for hopefully G&T students.)

The amount of `NaN`s  might be also a feature to analyze in and of itself. For example are parents of children than end up getting lower scores more likely to leave that field blank? (since they might not be able to be as picky on where there kid can go?). 

Even when columns are filled out, another common problem with data is the lack of standardization when it comes to the values in those columns. This is especially true when it comes to *user generated data*, where users can use different spellings/typings to describe the same thing. 

One quick way to check the different 





In the G&T dataset, its common to have certain 



Let's start with the first row of the data , before the raw student data, which holds the column names of the dataset. Based on the data dictionary that was defined earlier it might make sense to redefine some of our columns names to make our analysis more clearer/easier.

We can **rename** the *OLSAT Verbal Score* column name to just `OLSAT`. (We can also do something similar with the `NNAT Non Verbal Raw Score` column.) **Renaming** using `pandas` is fairly simple 







Column Names

Missing Values —> Replace NaNs

Unique and string characterizations 

K and (1) Problem

There are numerous ways of handling the other problems

Lower to Upper 

Renaming Columns 



process of detecting and correcting (or removing) corrupt or inaccurate records from a record set, table, or database and refers to identifying incomplete, incorrect, inaccurate or irrelevant parts of the data and then replacing, modifying, or deleting the dirty or coarse data

In the end of the day, while some "messy" data problems can be solved using data cleaning tools like the ones described above, other problems simply can't be. At that point, it's up to us, as data scientists to decide what we shoud we do. We can either decide **not** to analyze the data, (not as preferable), or we can try to get the data fixed at the point of creation. This would require talking to groups responsible for the creation of the data such as data managers and data engineers. 

Ultimately, people who create and share data usually want insights from it so there's no need to hesitate when giving feedback on how to help improve data cleanliness. Data science is a team sport and as the consumers of data, data scientists have a responsibility to help the producers we are dependent upon. 



DataOne would like to thank 