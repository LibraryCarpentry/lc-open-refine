---
title: "Importing data into OpenRefine"
teaching: 10
exercises: 5
questions:
- "How do I get data into OpenRefine?"
objectives:
- "Successfully import data into OpenRefine"
keypoints:
- "Use the 'Create Project' option to import data"
- "You can control how data imports using options on the import screen"
---

## Importing data

If you haven't already, at this point download [doaj-article-sample.csv](https://github.com/data-lessons/library-openrefine/raw/gh-pages/data/doaj-article-sample.csv), which is a csv file. Make a note of the location you save the file.

>## What kinds of data files can I import?
>There are several options for getting your data set into OpenRefine. You can upload or import files in a variety of formats including:
>
>* TSV (tab-separated values)
>* CSV (comma-separated values)
>* Excel
>* JSON (javascript object notation)
>* XML
>* Google Spreadsheet
{: .callout}

>## Exercise 1: Create your first Open Refine project (using provided data)
>
>To import the data for the exercises below, run OpenRefine. *NOTE: If Open Refine does not open in a browser window, open your browser and type the address <http://127.0.0.1:3333/> to take you to the Open Refine interface.*
>
>1. Locate the file which you have downloaded called `doaj-article-sample.csv`
>2. Click 'Next'
>   
>    The next screen gives you some options to ensure that the data gets imported into OpenRefine correctly. The options vary depending on the type of data you are importing.
>    
>    In this case you need to:
>    
>1. Set the 'Character encoding' to `UTF-8`
>2. Ensure the first row is used to create the column headings
>3. Make sure OpenRefine doesn't try to automatically detect numbers and dates
>
>    Once you are happy click the`Create Project >>`button at the top right of the screen
>
>    This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.
{: .challenge}

To open an existing project in OpenRefine you can click 'Open Project' from the main OpenRefine screen (in the left hand menu). When you click this, you will see a list of the existing projects and can click on a project's name to open it.

### Going Further
* Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.
* Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a 'record path' - that is the parts of the file that will form the data rows in the OpenRefine project.
