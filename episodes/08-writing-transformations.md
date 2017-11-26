---
title: "Writing Transformations"
teaching: 5
exercises: 10
questions:
- "Where do I write GREL expressions in the OpenRefine interface?"
- "How do I write a valid GREL expression?"
objectives:
- "Explain how to write one's own transformations using GREL"
keypoints:
- "You can alter data in OpenRefine based on specific instructions"
- "You can preview the results of your GREL expression"
---

## Writing transformations

To start writing transformations, select the column on which you wish to perform a transformation and choose ```Edit cells->Transform…```. In the screen that displays you have a place to write a transformation (the 'Expression' box) and then the ability to Preview the effect the transformation would have on 10 rows of your data.

The transformation you type into the 'Expression' box has to be a valid GREL expression. The simplest expression is simply the word 'value' by itself - which simply means the value that is currently in the column - that is: make no change.

GREL functions are written by giving a value of some kind (a text string, a date, a number etc.) to a GREL function. Some GREL functions take additional parameters or options which control how the function works. GREL supports two types of syntax:

* ```value.function(options)```
* ```function(value, options)```

Either is valid, and which is used is completely down to personal preference. In these notes the first syntax is used.

Next to the 'Preview' option are options to view:

* 'History' - a list of transformations you've previously used with the option to reuse them immediately or to 'star' them for easy access
* 'Starred' - a list of transformations you've 'starred' via the 'History' view
* 'Help' - a list of all the GREL functions and brief information on how to use them

>## Put titles into Title Case
>Use Facets and the GREL expression ```value.toTitlecase()``` to put the titles in Title Case
>1. Facet by publisher
>2. Select "Akshantala Enterprises" and "Society of Pharmaceutical Technocrats"
>3. To select multiple values in the facet use the ```include``` link that appears to the right of the facet
>4. See that the Titles for these are all in uppercase
>5.  Click the dropdown menu on the Title column
>6. Choose ```Edit cells->Transform...```
>7. In the Expression box type ```value.toTitlecase()```
>8. In the review note that you can see what the affect of running this will be
>9. Click ```OK```
{: .checklist}
