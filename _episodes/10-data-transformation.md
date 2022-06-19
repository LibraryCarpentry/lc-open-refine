---
title: "Transforming Strings, Numbers, Dates and Booleans"
teaching: 5
exercises: 15
questions:
- "How do I use transformations to programmatically edit my data?"
- "How do I transform the various data types?"
objectives:
- "Name and describe 4 types of data - String, Number, Date and Boolean"
- "Transform dates for further analysis"
- "Use Boolean to identify information recorded in a different format"
- "Create and run transformations based on Boolean Values"
keypoints:
- "You can alter data in OpenRefine based on specific instructions"
- "You can expand the data editing functions that are built-in into OpenRefine by building your own"
---

## Data types
Understanding data types and regular expressions will help you write more complex transformations using GREL.

>## Data types in OpenRefine
>Every piece of data in OpenRefine has a 'type'. The most common 'type' is a 'string' - that is a piece of text. However there are other data types available and transformations let you convert data from one type to another where appropriate. The data types supported are:
>
>* String
>* Number
>* Date
>* Boolean
>* Array (covered in the next lesson)
{: .callout}

### Dates and Numbers
So far we've been looking only at 'String' type data. Much of the time it is possible to treat numbers and dates as strings. For example in the Date column we have the date of publication represented as a String. However, some operations and transformations only work on 'number' or 'date' type operations. The simplest example is sorting values in numeric or date order. To carry out these functions we need to convert the values to a date or number first.

>## Reformat the Date
>1. Make sure you remove all Facets and Filters
>2. On the Date column use the dropdown menu to select ```Edit cells -> Transform```
>2. In the 'Expression' box type the GREL expression ```value.toDate("dd/MM/yyyy")``` and press OK.
>3. Note how the values are now displayed in green and follow a standard convention for their display format (ISO 8601) - this indicates they are now stored as date data types in OpenRefine. We can now carry out functions that are specific to Dates
>4. On the Date column dropdown select ```Edit column->Add column based on this column```. Using this function you can create a new column, while preserving the old column
>5. In the 'New column name' type "Formatted-Date"
>6. In the 'Expression' box type the GREL expression ```value.toString("dd MMM yyyy")
{: .checklist}

>## Understanding GREL Expressions
>
>General Refine Expression Language (GREL) allows to manipulate data in OpenRefine.
>
>One of the things we can do is request and specify how we want a date to be formated, following some examples and definition on letters meaning and usage. 
>
>Date and time formats require to be specified by ```pattern strings```, which basically means letters that have some specific representation in the function call. In our case that would be patterns strings for date and time.
>
>Pattern strings are case sensitive, which means they are capital and lower case letters have a different meaning and usage.
{: .callout}

The table below shows letters related to Date and Time representation.

| Letter| Date or Time Representation|
| ------------- |:-------------:|
| `G` | Era designator|
| `y` | Year|
| `Y` | Week year|
| `M` | Month in year|
| `w` | Week in year|
| `W` | Week in month|
| `D` | Day in year|
| `d` | Day in month|
| `F` | Day of week in month|
| `E` | Day name in week|
| `u` | Day number of week|
| `a` | AM/PM marker|
| `H` | Hour in day (0-23)|
| `k` | Hour in day (1-24)|
| `K` | Hour in AM/PM (0-11)|
| `h`| Hour in AM/PM (1-12)|
| `m`| Minute in hour|
| `s`| Second in minute|
| `S`| Milisecond|
| `n`| Nanosecond|
| `z`| Time zone|
| `Z`| Time zone|
| `X`| Time zone|

The table below presents examples on how to use the patterns as input and the obtained output.

| Date and Time Pattern Input| Output|
| ------------- |:-------------:|
| `"h:mm a"`| 12:30 PM|
| `"K:mm a, z"`| 0:07 PM, PDT|
| `"EEE, MMM d, ''yy"`| Mon, Jan 1, '05|
| `"yyyy.MM.dd G 'at' HH:mm:ss z"` | 2022.12.01 AD at 12:00:00 PDT |
| `"hh 'o''clock' a, zzzz"`| 10 o'clock PM, Eastern Daylight Time|
| `"yyyyy.MMMMM.dd GGG hh:mm aaa"`| 02022.June.19 AD 12:10 PM|
| `"EEE, d MMM yyyy HH:mm:ss Z"`| Wed, 5 Jul 2022 12:04:55 -0700|
| `"YYYY-'W'ww-u"`| 2023-W25-5|
| `"yyMMddHHmmssZ"`| 010704120856-0700|
| `"yyyy-MM-dd'T'HH:mm:ss.SSSZ"`| 2022-05-06T12:05:55.235-0700|
| `"yyyy-MM-dd'T'HH:mm:ss.SSSXXX"`| 2022-05-06T12:05:55.235-07:00|

For a more detailed explanation checkout [OpenFile Documentation](https://docs.openrefine.org/manual/grelfunctions#date-functions).


### Booleans
A 'Boolean' is a binary value that can either be 'true' or 'false'. Boolean values can be used directly in OpenRefine cell, but is more often used in transformations as part of a GREL expression. For example the GREL expression
```
value.contains("test")
```
generates a boolean value of either 'true' or 'false' depending on whether the current value in the cell contains the text 'test' anywhere.

Such tests can be combined with other GREL expressions to create more complex transformations. For example, to carry out a further transformation only if a test is successful. The GREL transformation ```if(value.contains("test"),"Test data",value)``` replaces a cell value with the words "Test data" only *if* the value in the cell contains the string "test" anywhere.

>## Find Reversed Author Names
>In this exercise we are going to use the Boolean data type.
>If you look at the Authors column, you can see that most of the author names are written with the personal name first. However, a few have been reversed to put the family name first.
>
>We can do a crude test for reversed author names by looking for those that contain a comma:
>
>1. Make sure you have already split the author names into individual cells using ```Edit cells->Split multi-valued cells``` (you should have done this in exercise 5)
>2. On the Authors column, use the dropdown menu and select ```Facet->Custom text facet...```
>3. The Custom text facet function allows you to write GREL functions to create a facet
>4. In the Expression box type ```value.contains(",").toString()```
>* Click ```OK```
>* Since the 'contains' function outputs a Boolean value, you should see a facet that contains 'false' and 'true'. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
>* In order to change the names to personal name first order, see the Arrays lesson.
{: .checklist}
