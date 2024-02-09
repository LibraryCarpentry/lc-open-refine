---
title: Transforming Strings, Numbers, Dates and Booleans
teaching: 5
exercises: 15
---

::::::::::::::::::::::::::::::::::::::: objectives

- Name and describe 4 types of data - String, Number, Date and Boolean
- Transform dates for further analysis
- Use Boolean to identify information recorded in a different format
- Create and run transformations based on Boolean Values

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I use transformations to programmatically edit my data?
- How do I transform the various data types?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Data types

Understanding data types can help you write a wider variety of transformations using GREL.

:::::::::::::::::::::::::::::::::::::::::  callout

## Data types in OpenRefine

Every piece of data in OpenRefine has a 'type'. The most common 'type' is a 'string' - that is a piece of text. However there are other data types available and transformations let you convert data from one type to another where appropriate. The data types supported are:

- String
- Number
- Date
- Boolean
- Array (covered in the next lesson)
  

::::::::::::::::::::::::::::::::::::::::::::::::::

### Dates and Numbers

So far we've been looking only at 'String' type data. Much of the time it is possible to treat numbers and dates as strings. For example in the Date column we have the date of publication represented as a String. However, some operations and transformations only work on 'number' or 'date' typed data, such as sorting values in numeric or date order. To carry out these functions we need to convert the values to a date or number first.

:::::::::::::::::::::::::::::::::::::::  checklist

## Reformat the Date

1. Make sure you remove all Facets and Filters
2. On the Date column use the dropdown menu to select `Edit cells -> Transform`
3. In the 'Expression' box type the GREL expression `value.toDate("dd/MM/yyyy")` and press OK.
4. Note how the values are now displayed in green and follow a standard convention for their display format (ISO 8601) - this indicates they are now stored as date data types in OpenRefine. We can now carry out functions that are specific to Dates
5. On the Date column dropdown select `Edit column->Add column based on this column`. Using this function you can create a new column, while preserving the old column
6. In the 'New column name' type "Formatted-Date"
7. In the 'Expression' box type the GREL expression `value.toString("dd MMMM yyyy")`
  

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Specifying Date Formatting in GREL Expressions

GREL allow us to specify date and time using `pattern strings`, which are letters that have some specific representation in the function call.

Pattern strings are case sensitive, therefore capital and lower case letters have a different meaning and usage.


::::::::::::::::::::::::::::::::::::::::::::::::::

The table below shows letters related to date and time representation.

| Letter                      | Date or Time Representation | 
| --------------------------- | :-------------------------: |
| `y`                            | Year                        | 
| `M`                            | Month in year               | 
| `D`                            | Day in year                 | 
| `d`                            | Day in month                | 
| `F`                            | Day of week in month        | 
| `E`                            | Day name in week            | 
| `u`                            | Day number of week          | 
| `a`                            | AM/PM marker                | 

The table below presents examples on how to use the patterns as input and the obtained output.

| Date and Time Pattern Input | Output                      | 
| --------------------------- | :-------------------------: |
| `"yyyy-MM-dd"`                            | 2022-06-05                  | 
| `"dd MMM yyyy"`                            | 05 Jun 2022                 | 
| `"EEE, MMM d, ''yy"`                            | Mon, Jun 5, '22             | 
| `"yyyy.MMMM.dd hh:mm a"`                            | 2022\.June.05 12:10 PM       | 
| `"EEE, d MMM yyyy HH:mm:ss"`                            | Mon, 5 Jun 2022 12:10:10    | 

For a more detailed explanation checkout [OpenRefine Documentation](https://docs.openrefine.org/manual/grelfunctions#date-functions).

### Booleans

A 'Boolean' is a binary value that can either be 'true' or 'false'. Boolean values can be used directly in OpenRefine cells, but are more often used in transformations as part of a GREL expression. For example the GREL expression

```
value.contains("test")
```

generates a boolean value of either 'true' or 'false' depending on whether the current value in the cell contains the text 'test' anywhere.

Such tests can be combined with other GREL expressions to create more complex transformations. For example, to carry out a further transformation only if a test is successful. The GREL transformation `if(value.contains("test"),"Test data",value)` replaces a cell value with the words "Test data" only *if* the value in the cell contains the string "test" anywhere.

:::::::::::::::::::::::::::::::::::::::  checklist

## Find Reversed Author Names

In this exercise we are going to use the Boolean data type.
If you look at the Authors column, you can see that most of the author names are written with the personal name first. However, a few have been reversed to put the family name first.

We can do a crude test for reversed author names by looking for those that contain a comma:

1. Make sure you have already split the author names into individual cells using `Edit cells->Split multi-valued cells` (you should have done this in exercise 5)
2. On the Authors column, use the dropdown menu and select `Facet->Custom text facet...`
3. The Custom text facet function allows you to write GREL functions to create a facet
4. In the Expression box type `value.contains(",")`

- Click `OK`
- Since the 'contains' function outputs a Boolean value, you should see a facet that contains 'false' and 'true'. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
- In order to change the names to personal name first order, see the Arrays lesson.
  

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- You can alter data in OpenRefine based on specific instructions
- You can expand the data editing functions that are built-in into OpenRefine by building your own

::::::::::::::::::::::::::::::::::::::::::::::::::


