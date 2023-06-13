---
title: Transformations - Handling Arrays
teaching: 5
exercises: 15
---

::::::::::::::::::::::::::::::::::::::: objectives

- Understand the purpose of Arrays in OpenRefine
- Use arrays as part of transformations in GREL

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I use Arrays in data transformation?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Preview

The following example is chosen to demonstrate how to go from a list with duplicated values to a list with each value just once by using an array in a transformation.

:::::::::::::::::::::::::::::::::::::::: instructor

## Different meanings of 'transformation'

Ask the students what transformation means to them currently.  Many may only know it from Excel to convert columns into rows or vice versa. Discuss how in OpenRefine, transformation is specifically the working window--these values are neither stored nor displayed in the cells or output.

::::::::::::::::::::::::::::::::::::::::::::::::::

It does this using a function called uniques() which can be used to remove duplicates from an array. In this example we start with a list of subject words:

`crystal structure|clozapinium|crystal structure|molecular configuration|hydrogen bonding|supramolecular assembly|Chemistry|QD1-999`

Examining this by eye we can see it contains "crystal structure" twice. If we assume that each cell in the subject column might have duplicates in it, and in each case the subject word/phrase that is duplicated could be different, then it's not practical to "fix" this problem (remove the duplicates from each) by find and replace. However, we can do it using an array. The lesson's goal is: an array as something you can manipulate.

To remove the repetition we show how to do a GREL transformation like:

```
value.split("|").uniques().join("|")
```

In total this transformation does three steps:

- `split("|")` creates an array -> `["crystal structure", "clozapinium", "crystal structure", "molecular configuration", "hydrogen bonding", "supramolecular assembly", "Chemistry", "QD1-999"]`
- `uniques()` takes the array created, and from it generates an array with any duplicates removed (so each value in the resulting array is unique) so the result is -> `["crystal structure", "clozapinium", "molecular configuration", "hydrogen bonding", "supramolecular assembly", "Chemistry", "QD1-999"]`
- `join("|")` turns the array created by the uniques() command back into a string of pipe separated values which can be stored in a cell -> `crystal structure|clozapinium|molecular configuration|hydrogen bonding|supramolecular assembly|Chemistry|QD1-999`

Let us now move from a list with duplicated values to a list with each value just once using an array in transformation.

## Arrays

An 'Array' is a data type (as mentioned in the previous lesson) which can contain a list of values. In OpenRefine an array is represented by the use of square brackets containing a list of values separated by commas.

For example:

- an array containing a list of strings (in this case subject keywords or phrases) could look like: `["crystal structure", "clozapinium", "crystal structure", "molecular configuration", "hydrogen bonding", "supramolecular assembly", "Chemistry", "QD1-999"]`
- an array containing a list of numbers could look like: `[1, 2, 3, 4]`

Arrays can be sorted, de-duplicated, and manipulated in other ways in GREL expressions, but cannot be stored directly in an OpenRefine cell. Arrays in OpenRefine are usually the result of a transformation written with GREL. For example the `split` function takes a string, and changes it into an array based on a 'separator'. For example if a cell has the value:

`"crystal structure|clozapinium|crystal structure|molecular configuration|hydrogen bonding|supramolecular assembly|Chemistry|QD1-999"`

This can be transformed into an array using the `split` function specifying the pipe character ( | ) as the separating character. Recall the cautionary note about separator choice from [Working with Data](https://librarycarpentry.org/lc-open-refine/03-working-with-data/index.html).
.

```
value.split("|")
```

This would create the array containing a list of subject headings, separated by a pipe character | (as in the first example above). In the transformation preview the array will display as a list of comma separated values in double quotes, with the whole array surrounded by square brackets.

This subject string can be found for the title "The crystal structures of three clozapinium salts: different molecular configurations, and supramolecular assembly in one, two and three dimensions" in the original project.

This can be combined with array operations like `uniques`. For example, assuming the cell contains the same value as above, then the function

```
value.split("|").uniques()
```

would result in the following array:
["crystal structure", "clozapinium", "molecular configuration", "hydrogen bonding", "supramolecular assembly", "Chemistry", "QD1-999"]

Compared to the first example, now the second 'crystal structure' has been removed.

You can extract a specific item from the array using the square bracket notation and number for position in sequence:

```
value.split("|")[0]
```

would result in the string:
"crystal structure"

You can also join arrays together to make a 'String'. The GREL expression would look like

```
value.split("|").uniques().join("|")
```

Taking the same example again, this would result in a string with the subjects in alphabetical order, listed with commas between each subject.

:::::::::::::::::::::::::::::::::::::::  instructor

## Recap on best practice for separators

Recall previous discussion of dangers of changing separators and ensuring you avoid using a separator character that is already used in the text. A possible question to pose to learners could be: Which subject would be broken if a hyphen were used as a separator?

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::  checklist

## Reverse author names

You may already have done the boolean exercise and have a facet containing the names in personal name first order. In this case, select the 'true' facet and start with the step **"9. On the `Authors` column use..."** below.

In this exercise we are going to use both the Boolean and Array data types.
If you look at the Authors column, you can see that most of the author names are written in personal name first order. However, a few have been reversed to put the family name first.

We can do a crude test for reversed author names by looking for those that contain a comma:

1. Make sure you have already split the author names into individual cells using `Edit cells->Split multi-valued cells` (you should have done this in the Clustering lesson)
2. On the Authors column, use the dropdown menu and select `Facet->Custom text facet...`
3. The `Custom text` facet function allows you to write GREL functions to create a facet
4. In the Expression box type `value.contains(",")`
5. Click `OK`
6. Since the `contains` function outputs a Boolean value, you should see a facet that contains 'false' and 'true'. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
7. In this facet select 'true' to narrow down to the author names that contain a comma
8. Now we have narrowed down to the lines with a comma in a name, we can use the GREL `split` function. This is different to the `Split multi-valued cells` operation we have previously used as it allows us to manipulate the content of a cell, rather than create new cells.
9. On the `Authors` column use the dropdown menu and select `Edit cells->Transform `
10. In the Expression box type `value.split(", ")` (make sure to include a space after the comma inside the split expression to avoid extra spaces in your author name later).
11. See how this creates an array with two members in each row in the Preview column
12. To get the author name in personal name first order you can reverse the array and join it back together with a space to create the string you need:
13. In the Expression box, add to the existing expression until it reads `value.split(", ").reverse().join(" ")`
14. In the Preview view you should be able see this has reversed the array, and joined it back into a string
15. Click `OK`
  

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- Arrays cannot appear directly in an OpenRefine cell
- Arrays can be used in many ways using GREL expressions

::::::::::::::::::::::::::::::::::::::::::::::::::


