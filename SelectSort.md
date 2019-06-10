---
title: "Data Cleaning"
date: 2019-06-06T18:01:45-04:00
draft: false
weight: 15
---

Data being in a tabular format offers a tremendous advantage when it comes to doing data science. However just because our data is in a table doesn't mean that it's really ready for analysis. Sometimes the data that we receive can consist of inconsistencies and gaps that can make the underlying analysis difficult or downright impossible to do. 

**Data cleaning** refers to the process of detecting and correcting these problems from a data set. **Data cleaning** is a very common processing step in the data science pipeline. 

Unfortunately for data scientists there are an endless amount of ways that our data can have problems. In this lesson and in the end of Chapter 7, we will touch on some of these problems and suggest ways to solve them.

Before we do that, let's introduce another dataset, this time one that suffers from "messiness". 

Every year, groups of anxious New York City parents wait for the results of NYC's **Gifted and Talented Test**,  an exam for K-3rd grade children that controls the admissions for the city's **Gifted and Talented Program**(G&T) . Getting into G&T can be a big deal, certain well funded early education schools are limited to those only in the program. 

![This image is a picture of New York City's Department of Education logo. ](NYC.png)

There's a certain level of uncertainity on what score is necessary in order to get into G&T (the cutoff changes every year and NYC doesn't publicly share the information for a variety of reasons). In an attempt to solve this uncertainity parents have crowdsourced their own child's score resuts on online spreadsheets. Below is a snapshot of the data collected by New York City families. 

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

Let's start with some of the values in the data itself, specifically the `NaN` value. Unsuprisingly, there is no school in the NYC School district called `NaN`. Instead Pandas uses `Nan` (shortform for *Not a Number*) to fill out columns values in rows where there is no data inputed. Unfortunately some parents didn't bother to fill out the column value that asked for what school they prefered their child to attend if they were to get into G&T. 

What should we do about this? One strategy that can we try, (especially if the existence of `NaN` is rare and most parents followed the online directions), is to drop any rows with missing data using the `dropna` method. 

~~~python
nyc_testscores = pd.read_csv("G&T.csv")
nyc_testscores.dropna()
~~~

By looking at the amount of rows that were dropped due to `dropna`, we can find what the percentage of rows containing`NaN `s are in the dataset. For G&T though`NaN` isn't rare and 34% of parents didn't bother filling out their School Preferences. 

It might still make sense to get rid of the `NaN` rows depending on what questions we want to ask about our data. (Such as if we want to do an analysis specifically on the schools that parents are prefering for hopefully G&T students.)

The amount of `NaN`s  might be also a feature to analyze in and of itself. For example are parents of children than end up getting lower scores more likely to leave that field blank? (since they might not be able to be as picky on where there kid can go?). 

Even when columns are filled out, another common problem with data is the lack of standardization when it comes to the values in those columns. This is especially true when it comes to *user generated data*, where users can use different spellings/typings to describe the same thing. 

One quick way to check the different unique values in a column is by using the `unique` function on a column. For the **Month** column we expect at most 12 different values since that's how months there are in a year. 

~~~Python
len(nyc_testscores["Month"].unique()) 
~~~

~~~
19
~~~

NYC parents didn't discover new months in our Gregorian calendar, instead some of them decided to type their students birth month with and without the first letter being capitalized. We already saw an example of this in the snapshot of the dataset earlier with one child's month being *september* and another being *September*. 

How do we fix this? We can use a String method that we learned earlier, `lower`, to ensure that all of our months are stadardized and are lowercased. 

~~~python
nyc_testscores["Month"] = nyc_testscores["Month"].str.lower()
nyc_testscores
~~~

| Entering Grade Level | Month     | OLSAT Verbal Score | NNAT Non Verbal Raw Score | Overall Score | School Preferences          |
| -------------------- | --------- | ------------------ | ------------------------- | ------------- | --------------------------- |
| 1                    | september | 28                 | 45                        | 99            | NEST+m, TAG, Anderson, Q300 |
| K                    | august    | 25                 | 39                        | 99            | Anderson, NEST+m            |
| 1                    | march     | 27                 | 42                        | 98            | TAG                         |
| K                    | september | 23                 | 40                        | 98            | Anderson                    |
| K                    | april     | 25                 | 38                        | 99            | Brooklyn School of Inquiry  |



Standardizing data across columns is a common goal when doing data cleaning, but how to actually accomplish that standardization can vary wildely depending on the type of data that's inside your columns.  

For example, how do we handle the fact that the column **Entering Grade Level** has both numbers, (1,2,3 representing 1st-3rd graders), and a string, (K representing kindergardners)? Should we convert all our numbers into strings or vice-versa? 

We'll explore more advanced data cleaning problems like this in Chapter 7! 