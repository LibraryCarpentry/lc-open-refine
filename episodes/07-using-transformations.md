---
title: "Transformations"
teaching: 20
exercises: 40
questions:
- "How do I use transformations to programmatically edit my data?"
- "How do I use GREL, the General Refine Expression Language?"
- "How do I save and reuse a set of operations for use in subsequent projects?"
- "What are the data formats supported by OpenRefine and why should I care?"
objectives:
- "Introduce common transformations"
- "Introduce GREL, the General Refine Expression Language"
- "Explain how to write one's own transformations using GREL"
- "Explain how to use Undo and Redo to retrace ones' steps"
- "Explain how to use Extract and Apply to reuse a set of operations"
- "Introduce data formats"
- "Introduce Boolean values and arrays, and how to run transformations based on them"
keypoints:
- "You can alter data in OpenRefine based on specific instructions"
- "You can expand the data editing functions that are built-in into OpenRefine by building your own"
---

## Transforming data

### Introducing Transformations

Through facets, filters and clusters OpenRefine offers relatively straightforward ways of getting an overview of your data, and making changes where you want to standardise terms used to a common set of values.

However, sometimes there will be changes you want to make to the data that cannot be achieved in this way. Such types of changes include:

* Splitting data that is in a single column into multiple columns (e.g. splitting an address into multiple parts)
* Standardising the format of data in a column without changing the values (e.g. removing punctuation or standardising a date format)
* Extracting a particular type of data from a longer text string (e.g. finding ISBNs in a bibliographic citation)

To support this type of activity OpenRefine supports 'Transformations' which are ways of manipulating data in columns. Transformations are normally written in a special language called 'GREL' (General Refine Expression Language). To some extent GREL expressions are similar to Excel Formula, although they tend to focus on text manipulations rather than numeric functions.

Full documentation for the GREL is available at [https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language](https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language). This tutorial covers only a small subset of the commands available.

### Common transformations
Some transformations are used regularly and are accessible directly through menu options, without having to type them directly.

Examples of some of these common transformations are given in the table below, with their 'GREL' equivalents. We'll see how to use the GREL version later in this lesson.

Common Transformation  | Action | GREL expression
--------------------| ------------- | -------------
To Uppercase| Converts the current value to uppercase | ```value.toUppercase()```
To Lowercase| Converts the current value to lowercase | ```value.toLowercase()```
To Titlecase| Converts the current value to titlecase (i.e. each word starts with an uppercase character and all other characters are converted to lowercase) | ```value.toTitlecase()```
Trim leading and trailing whitespace | Removes any 'whitespace' characters (e.g. spaces, tabs) from the start or end of the current value | ```value.trim()```

>## Correct Publisher data
>* Create a text facet on the Publisher column
>* Note that in the values there are two that look identical - why does this value appear twice?
>* On the publisher column use the dropdown menu to select 'Edit cells->Common transforms->Trim leading and trailing whitespace'
>* Look at the publisher facet now - has it changed? (if it hasn't changed try clicking the Refresh option to make sure it updates)
{: .challenge}

### Writing transformations
To start writing transformations, select the column on which you wish to perform a transformation and choose 'Edit cells->Transform…'. In the screen that displays you have a place to write a transformation (the 'Expression' box) and then the ability to Preview the effect the transformation would have on 10 rows of your data.

The transformation you type into the 'Expression' box has to be a valid GREL expression. The simplest expression is simply the word 'value' by itself - which simply means the value that is currently in the column - that is: make no change.

GREL functions are written by giving a value of some kind (a text string, a date, a number etc.) to a GREL function. Some GREL functions take additional parameters or options which control how the function works. GREL supports two types of syntax:

* value.function(options)
* function(value, options)

Either is valid, and which is used is completely down to personal preference. In these notes the first syntax is used.

Next to the 'Preview' option are options to view:

* History - a list of transformations you've previously used with the option to reuse them immediately or to 'star' them for easy access
* Starred - a list of transformations you've 'starred' via the 'History' view
* Help - a list of all the GREL functions and brief information on how to use them

>## Put titles into Title Case
>* Facet by publisher
>* Select "Akshantala Enterprises" and "Society of Pharmaceutical Technocrats"
>    * To select multiple values in the facet use the 'Include' link that appears to the right of the facet
>* See that the Titles for these are all in uppercase
>* Click the dropdown menu on the Title column
>* Choose 'Edit cells->Transform...'
>* In the Expression box type ```value.toTitlecase()```
>* In the Preview note that you can see what the affect of running this will be
>* Click 'OK'
{: .challenge}

## Undo and Redo
OpenRefine lets you undo, and redo, any number of steps you have taken in cleaning the data. This means you can always try out transformations and 'undo' if you need to. The way OpenRefine records the steps you have taken even allows you to take the steps you've carried out on one data set, and apply it to another data set by a simple copy and paste operation.

The 'Undo' and 'Redo' options are accessed via the lefthand panel.

The Undo/Redo panel lists all the steps you've taken so far. To undo steps, simply click on the last step you want to preserve in the list and this will automatically undo all the changes made since that step.

The remaining steps will continue to show in the list but greyed out, and you can reapply them by simply clicking on the last step you want to apply.

However, if you 'undo' a set of steps and then start doing new transformations, the greyed out steps will disappear and you will no longer have the option to 'redo' these steps.

If you wish to save a set of steps to be re-applied later, or to a different project, you can click the 'Extract' button. This gives you the option to select the steps you want to save, and to copy the transformations included in the selected steps in a format called 'JSON'

To apply a set of steps you have copied or saved in this 'JSON' format use the 'Apply' button and paste in the JSON. In this way you can share transformations between projects and each other.

Undo/Redo data is stored with the Project and is saved automatically as you work, so next time you open the project, you can access your full history of steps you have carried out and undo/redo in exactly the same way.

## Exporting data
Once you have finished working with a data set in OpenRefine you may wish to export it. The export options are accessed through the 'Export' button at the top right of the OpenRefine interface
Export formats support include HTML, Excel and comma- and tab-separated value (csv and tsv). You can also write a custom export, selecting to export specific fields, adding a header or footer and specifying the exact format.

## Data types
Understanding data types and regular expressions will help you write more complex transformations using GREL.

### Data types in OpenRefine
Every piece of data in OpenRefine has a 'type'. The most common 'type' is a 'string' - that is a piece of text. However there are other data types available and transformations let you convert data from one type to another where appropriate. The data types supported are:

* String
* Number
* Date
* Boolean
* Array

### Dates and Numbers
So far we've been looking only at 'String' type data. Much of the time it is possible to treat numbers and dates as strings. For example in the Date column we have the date of publication represented as a String. However, some operations and transformations only work on 'number' or 'date' type operations. The simplest example is sorting values in numeric or date order. To carry out these functions we need to convert the values to a date or number first.

>## Reformat the Date
>* Make sure you remove all Facets and Filters
>* On the Date column use the dropdown menu to select 'Edit cells->Common transforms->To date'
>* Note how the values are now displayed in green and follow a standard convention for their display format (ISO8601) - this indicates they are now stored as date data types in OpenRefine. We can now carry out functions that are specific to Dates
>* On the Date column dropdown select 'Edit column->Add column based on this column'. Using this function you can create a new column, while preserving the old column
>* In the 'New column name' type "Formatted Date"
>* In the 'Expression' box type the GREL expression ```value.toString("dd MMMM yyyy")```
{: .challenge}

### Booleans and Arrays

Booleans and Arrays are data types that are more often used while manipulating data in a GREL expression than for actually storing in a cell (in fact, Arrays cannot be stored in a cell in OpenRefine).

#### Booleans
A 'Boolean' is a binary value that can either be 'true' or 'false'. Boolean values can be used directly in OpenRefine cell, but is more often used in transformations as part of a GREL expression. For example the GREL expression
```
value.contains("test")
```
generates a boolean value of either 'true' or 'false' depending on whether the current value in the cell contains the text 'test' anywhere.

Such tests can be combined with other GREL expressions to create more complex transformations. For example, to carry out a further transformation only if a test is successful. The GREL transformation ```if(value.contains("test"),"Test data",value)``` replaces a cell value with the words "Test data" only *if* the value in the cell contains the string "test" anywhere.

#### Arrays
An 'Array' is a list of values, represented in Refine by the use of square brackets containing a list of values surrounded by inverted commas and separated by commas. For example an array listing the days of the week would look like:

["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"]

Arrays can be sorted, de-duplicated, and manipulated in other ways in GREL expressions, but cannot appear directly in an OpenRefine cell. Arrays in OpenRefine are usually the result of a transformation. For example the 'split' function takes a string, and changes it into an array based on a 'separator'. For example if a cell has the value:

"Monday,Tuesday,Wednesday,Thursday,Friday,Saturday,Sunday"

This can be transformed into an array using the 'split' function
```
value.split(",")
```
This would create the array containing the days of the week:

["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"]

This can be combined with array operations like 'sort'. For example, assuming the cell contains the same value as above, then the function
```
value.split(",").sort()
```
would result in an array containing the days of the week sorted in alphabetical order:

["Friday","Monday","Saturday","Sunday","Thursday","Tuesday","Wednesday"]

To output a value from an array you can either select a specific value depending on its position in the list (with the first position treated as 'zero'). For example
```
value.split(",")[0]
```
would extract the first value from the array created by the 'split' function. In the above example this would be "Monday"

You can also join arrays together to make a 'String'. The GREL expression would look like
```
value.split(",").sort().join(",")
```
. Taking the above example again, this would result in a string with the days of the week in alphabetical order, listed with commas between each day.

>## Reverse author names
>In this exercise we are going to use both the Boolean and Array data types.
>If you look at the Authors column, you can see that most of the author names are written in the natural order. However, a few have been >reversed to put the family name first.
>
>We can do a crude test for reversed author names by looking for those that contain a comma:
>
>* Make sure you have already split the author names into individual cells using 'Edit cells->Split multi-valued cells' (you should have done this in exercise 5)
>* On the Authors column, use the dropdown menu and select 'Facet->Custom text facet...'
>    * The Custom text facet function allows you to write GREL functions to create a facet
>* In the Expression box type ```value.contains(",")```
>* Click 'OK'
>* Since the 'contains' function outputs a Boolean value, you should see a facet that contains 'false' and 'true'. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
>* In this facet select 'true' to narrow down to the author names that contain a comma
>
>Now we have narrowed down to the lines with a comma in a name, we can use the 'match' function. The match function allows you to use >regular expressions, and output the capture groups as an array, which you can then manipulate.
>
>* On the Authors column use the dropdown menu and select 'Edit cells->Transform'
>* In the Expression box type ```value.match(/(.*),(.*)/)```  The "/",  means you are using a regular expression inside a GREL expression. The parentheses indicate you are going to match a group of characters. The ".\*" expression will match any character from 0, 1 or more times. So here we are matching any number of characters, a comma, and another set of any number of characters.
>* See how this creates an array with two members in each row in the Preview column
>
>To get the author name in the natural order you can reverse the array and join it back together with a space to create the string you need:
>
>* In the Expression box, add to the existing expression until it reads ```value.match(/(.*),(.*)/).reverse().join(" ")```
>* In the Preview view you should be able see this has reversed the array, and joined it back into a string
>* Click 'OK'
{: .challenge}
