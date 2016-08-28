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

### Exercise 1: Create your first Open Refine project (using provided data)
There are several options for getting your data set into OpenRefine. You can upload or import files in a variety of formats including:

* TSV (tab-separated values)
* CSV (comma-separated values)
* Excel
* JSON (javascript object notation)
* XML
* Google Spreadsheet

To import the data for the exercises below, run OpenRefine. *NOTE: If Open Refine does not open in a brower window, open your browser and type the address http://127.0.0.1:3333/ to take you to the Open Refine interface.*
* Locate the file called which you previously downloaded 'doaj-article-sample.csv'
* Click 'Next'

The next screen gives you some options to ensure that the data gets imported into OpenRefine correctly. The options vary depending on the type of data you are importing.

In this case you need to:

* Set the 'Character encoding' to 'UTF-8'
* Ensure the first row is used to create the column headings
* Make sure OpenRefine doesn't try to automatically detect numbers and dates

Once you are happy click 'Create Project >>'

This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.

To open an existing project in OpenRefine you can click 'Open Project' from the main OpenRefine screen (in the lefthand menu). When you click this, you will see a list of the existing projects and can click on a project's name to open it.

### Going Further
* Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.
* Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a 'record path' - that is the parts of the file that will form the data rows in the OpenRefine project.