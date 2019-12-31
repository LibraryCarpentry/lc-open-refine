---
title: "Transformations - Handling Arrays"
teaching: 5
exercises: 15
questions:
- "How do I use Arrays in data transformation?"
objectives:
- "Introduce Arrays, and how to use them to run transformations in GREL"
keypoints:
- "Arrays cannot appear directly in an OpenRefine cell"
- "Arrays can be used in many ways using GREL expressions"
---

## Arrays
An 'Array' is a list of values, represented in Refine by the use of square brackets containing a list of values surrounded by inverted commas and separated by commas. For example an array listing the days of the week would look like:

["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"]

Arrays can be sorted, de-duplicated, and manipulated in other ways in GREL expressions, but cannot appear directly in an OpenRefine cell. Arrays in OpenRefine are usually the result of a transformation. For example the ```split``` function takes a string, and changes it into an array based on a 'separator'. For example if a cell has the value:

"Monday,Tuesday,Wednesday,Thursday,Friday,Saturday,Sunday"

This can be transformed into an array using the ```split``` function
```
value.split(",")
```
This would create the array containing the days of the week:

["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"]

This can be combined with array operations like ```sort```. For example, assuming the cell contains the same value as above, then the function
```
value.split(",").sort()
```
would result in an array containing the days of the week sorted in alphabetical order:

["Friday","Monday","Saturday","Sunday","Thursday","Tuesday","Wednesday"]

To output a value from an array you can either select a specific value depending on its position in the list (with the first position treated as 'zero'). For example
```
value.split(",")[0]
```
would extract the first value from the array created by the ```split``` function. In the above example this would be "Monday"

You can also join arrays together to make a 'String'. The GREL expression would look like
```
value.split(",").sort().join(",")
```
Taking the above example again, this would result in a string with the days of the week in alphabetical order, listed with commas between each day.

>## Reverse author names
>You may already have done the boolean exercise and have a facet containing the names in natural order. In this case, select the 'true' facet and start with the step **"1. On the ```Authors``` column use..."**
>
>In this exercise we are going to use both the Boolean and Array data types.
>If you look at the Authors column, you can see that most of the author names are written in the natural order. However, a few have been reversed to put the family name first.
>
>We can do a crude test for reversed author names by looking for those that contain a comma:
>
>1. Make sure you have already split the author names into individual cells using ```Edit cells->Split multi-valued cells``` (you should have done this in the Clustering lesson)
>2. On the Authors column, use the dropdown menu and select ```Facet->Custom text facet...```
>3. The ```Custom text``` facet function allows you to write GREL functions to create a facet
>4. In the Expression box type ```value.contains(",").toString()```
>5. Click ```OK```
>6. Since the ```contains``` function outputs a Boolean value, you should see a facet that contains 'false' and 'true'. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
>7. In this facet select 'true' to narrow down to the author names that contain a comma
>
>Now we have narrowed down to the lines with a comma in a name, we can use the ```match``` function. The match function allows you to use regular expressions, and output the capture groups as an array, which you can then manipulate.
>
>1. On the ```Authors``` column use the dropdown menu and select ```Edit cells->Transform ```
>2. In the Expression box type ```value.match(/(.*),(.*)/)```  The ```/```,  means you are using a regular expression inside a GREL expression. The parentheses indicate you are going to match a group of characters. The ```.*``` expression will match any character(s) appearing 0, 1 or more times. So here we are matching any number of characters, a comma, and another set of any number of characters.
>3. See how this creates an array with two members in each row in the Preview column
>
>To get the author name in the natural order you can reverse the array and join it back together with a space to create the string you need:
>
>1. In the Expression box, add to the existing expression until it reads ```value.match(/(.*),(.*)/).reverse().join(" ")```
>2. In the Preview view you should be able see this has reversed the array, and joined it back into a string
>* Click ```OK```
{: .checklist}
