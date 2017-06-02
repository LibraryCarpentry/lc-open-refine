---
title: "Basic OpenRefine Functions I: Layout of OpenRefine, Rows vs Records"
teaching:  5
exercises: 5
questions: 
- "How is data organised in OpenRefine?"
- "How do I access options to amend data in OpenRefine?"
- "What is the difference between Rows and Records in OpenRefine?"
objectives:
- Locate controls for navigating data in OpenRefine
- Find options to work with data through the OpenRefine dropdown menus
- Split cells which contain multiple bits of data so that each piece of data is in its own cell
keypoints:
- "OpenRefine uses rows and columns to display data"
- "Most options to work with data in OpenRefine are accessed through a drop down menu at the top of a data column"
- "When you select an option in a particular column (e.g. to make a change to the data), it will effect all the cells in that column"
- "OpenRefine has a Records mode which links together multiple rows into a single record"
---

## The layout of OpenRefine
OpenRefine displays data in a tabular format. Each row will usually represent a 'record' in the data, while each column represents a type of information. This is very similar to how you might view data in a spreadsheet or database. As with a spreadsheet, the individual bits of data live in 'cells' at the intersection of a row and a column.

OpenRefine only displays a limited number of rows of data at one time. You can adjust the number choosing between 5, 10 (the default), 25 and 50. You can navigate through the records by using the previous/next/first/last navigation options at the top right of the table of data.

## Working with data in OpenRefine
Most options to work with data in OpenRefine are accessed from drop down menus at the top of the data columns. When you select an option in a particular column (e.g. to make a change to the data), it will affect all the cells in that column. If you want to make changes across several columns, you will need to do this one column at a time.

## Rows and Records
OpenRefine has two modes of viewing data 'Rows' and 'Records'. At the moment we are in Rows mode, where each row represents a single record in the data set - in this case, an article. In Records mode, OpenRefine can link together multiple rows as belonging to the same Record.

### Splitting Cells

To see how this works in practice we can split author names into separate cells. If you look at the Author column you should be able to see that there are multiple names in each cell separated by the pipe symbol "\|".

To work with the author names effectively in OpenRefine, we need to have each name in an individual cell. To split the names into their own cells we can use a 'Split multi-valued cells' function:

* Click the dropdown menu at the top of the Author column
* Choose 'Edit cells->Split multi-valued cells'
* In the prompt type the "\|" symbol and click 'OK'
    * Note that the rows are still numbered sequentially
* Click the 'Records' option to change to Records mode
    * Note how the numbering has changed - indicating that several rows are related to the same record

 ![rows](../assets/img/rows.png)
 ![records](../assets/img/records.png) 

>## Exercise 2: Splitting Subjects into separate cells
>
>1. What separator character is used in the Subject headings cells?
>2. How would you split these subject words into individual cells?
> 
> > ## Solution
> > 1. The subject words/headings are divided up with the pipe "\|" character
> > 2. To split the subject words into individual cells you need to:
> > * Click the dropdown menu at the top of the Subjects column
> > * Choose 'Edit cells->Split multi-valued cells'
> > * In the prompt type the "\|" symbol and click 'OK'
> {: .solution}
{: .challenge}

Now that we can split multi-valued cells, we'll cover how to join them back together.

### Joining Cells

A common workflow with multi-valued cells is

- split multi-valued cells into individual cells (what we did above)
- modify/refine/clean individual cells
- join multi-valued cells back together

Modifying cells will be covered in future lessons, but for now we will cover how to join cells back together than have been split previously.

* Click the dropdown menu at the top of the Author column
* Choose 'Edit cells->Join multi-valued cells'
* In the prompt type the "\|" symbol
    * Here we are specifying the *delimiter* character for OpenRefine to use to join the values together.
* Click 'OK' to join the Authors cells back together

You will now see that split rows have gone away - the Authors have been joined into a single cell with the specified delimiter. Our Rows and
Records values will now be the same since we do not have any more split columns.

* Click both the 'Rows' and 'Records' options and observe how the numbers of Rows and Records are equal

>## Exercise 3: Joining the Subjects column back together
>
>1. If you split the Subjects column in Exercise 2 above, you may not see your Rows and Records counts being equal
>2. If you split the Subjects, now join them back together and you'll see your Rows and Records are equal
>
> > ## Solution
> > 1. The subject words/headings were previously delimited with the pipe "\|" character
> > 2. To join the split subject cells back to a single cell you need to:
> > * Click the dropdown menu at the top of the Subjects column
> > * Choose 'Join cells->Split multi-valued cells'
> > * In the prompt type the "\|" symbol and click 'OK'
> {: .solution}
{: .challenge}

