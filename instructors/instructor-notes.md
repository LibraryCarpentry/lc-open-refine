---
title: Instructor Notes
---

***

# Tips and Tricks

***

## Making a handout

Adapt/print from:

- [Library Carpentry Reference Page](https://librarycarpentry.org/lc-open-refine/reference.html)
- [Instructor Draft Notes](https://github.com/LibraryCarpentry/lc-open-refine/blob/gh-pages/files/draft-instructor-notes.md)
- [Introduction to OpenRefine by Owen Stephens](https://www.meanboyfriend.com/overdue_ideas/wp-content/uploads/2014/11/Introduction-to-OpenRefine-handout-CC-BY.pdf)

***

# General notes on OpenRefine

## Common problems

- If learners are using a browser other than Firefox, or OpenRefine does not automatically open for them when they click the .exe file, have them point their browser at [http://127.0.0.1:3333/](https://127.0.0.1:3333/) or [http://localhost:3333](https://localhost:3333) to launch the program.

- Mac users with the newest operating system will have to allow this to run by "allowing everything" to run. They can change the setting back after the exercise.

- Some students will run into issues with
  
  - unzipping
  - finding the .exe file once the software has been unzipped
  - finding the data file on their computers after downloading

- If OpenRefine crashes when launched from a network share drive, do the following:
  
  - Copy the OpenRefine folder to a local drive not mapped to a network share, e.g. "C:\\Users\\JaneDoe"
  - Open a Windows Command prompt
  - Change the working directory to the OpenRefine folder at "C:\\Users\\JaneDoe"
  - Run openrefine.exe

- If "https" doesn't work to fetch CrossRef during Advanced OpenRefine Functions, they can try "http"

- If they need to diagnose failure to fetch the content from the URL they can check the "Store error" option in the "Add column by fetching URLs" dialogue and try looking at the common problems listed in the [documentation](https://docs.openrefine.org/manual/columnediting#common-errors)

- The data for this lesson was pulled from DOAJ in 2015 and may not reflect the same data currently available from DOAJ on the day of your workshop.

## Powerful transformations

- In the titlecase exercise, highlight the fact that
  each transformation can have unintended side effects,
  and advise that running one cleanup operation too few
  may sometimes be preferable to one too many.


