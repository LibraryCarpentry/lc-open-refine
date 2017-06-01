---
title: "Basic OpenRefine Functions I: Layout of OpenRefine, Rows vs Records"
teaching: 
exercises:
questions:

objectives:

keypoints:

---

## The layout of OpenRefine
OpenRefine displays data in a tabular format. Each row will usually represent a 'record' in the data, while each column represents a type of information. This is very similar to how you might view data in a spreadsheet or database.

OpenRefine only displays a limited number of lines of data at one time. You can adjust the number choosing between 5, 10 (the default), 25 and 50.

# Rows and Records
OpenRefine has two modes of viewing data 'Rows' and 'Records'. So far we've been using the Rows mode, where each row represents a single record in the data set - in this case, an article. In Records mode, OpenRefine can link together multiple rows as belonging to the same Record.

How this works can be seen in the next exercise...

>## Excerise 2: Split author names into separate cells
>If you look at the Author column you should be able to see that there are multiple names in each cell separated by the pipe symbol "|". >To work with the author names effectively we need to split them into separate cells:
>
>* Click the dropdown menu at the top of the Author column
>* Choose 'Edit cells->Split multi-valued cells'
>* In the prompt type the "\|" symbol and click 'OK'
>    * Note that the rows are still numbered sequentially
>* Click the 'Records' option to change to Records mode
>    * Note how the numbering has changed - indicating that several rows are related to the same record
{: .challenge}

![records](../assets/img/records.png) ![rows](../assets/img/rows.png)
