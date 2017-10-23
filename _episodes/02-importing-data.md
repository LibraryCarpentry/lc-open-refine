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

>## Create your first OpenRefine project (using provided data)
>
> To import the data for the exercises below, run OpenRefine. *NOTE: If OpenRefine does not open in a browser window, open your browser and type the address <http://127.0.0.1:3333/> to take you to the OpenRefine interface.*
>
>1. Once OpenRefine is launched in your browser, click `Create Project` from the left hand menu and select `Get data from This Computer`
>2. Click `Choose Files` and locate the file which you have downloaded called `doaj-article-sample.csv` *(if you haven't downloaded it yet, please see 'Downloading the data' in the Setup page [http://data-lessons.github.io/library-openrefine/setup/](http://data-lessons.github.io/library-openrefine/setup/))*
>3. Click `Next >>` - the next screen (see below) gives you options to ensure the data is imported into OpenRefine correctly. The options vary depending on the type of data you are importing.
>4. Click in the `Character encoding` box and set it to `UTF-8`
>5. Ensure the first row is used to create the column headings by checking the box `Parse next 1 line(s) as column headers`
>6. Make sure the `Parse cell text into numbers, dates, ...` box is not checked, so OpenRefine doesn't try to automatically detect numbers
>7. Once you are happy click the `Create Project >>` button at the top right of the screen. This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.
>   
> ![Create project screen capture](../assets/img/openrefine_ui.png)
>
{: .checklist}

To open an existing project in OpenRefine you can click `Open Project` from the main OpenRefine screen (in the left hand menu). When you click this, you will see a list of the existing projects and can click on a project's name to open it.

>## Exercise: Create project from web address
> Try creating your project by importing the data directly from this lesson's GitHub repository. 
>
>1. Launch OpenRefine in a new browser tab by typing in the address <http://127.0.0.1:3333/>
>1. Click `Create Project` from the left hand menu and select `Web Addresses (URLs)`
>2. Paste in `https://raw.githubusercontent.com/data-lessons/library-openrefine/gh-pages/data/doaj-article-sample.csv`
>3. Click `Next >>` and configure the import options as before.
{: .challenge}

>## Exercise: Going further
>1. Look at the other options on the import screen - try changing some of these options and clicking `Update Preview`
>2. Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to `Please specify a record path first` - that is the parts of the file that will form the data rows in the OpenRefine project.
{: .challenge}