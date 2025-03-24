---
title: Working with columns and sorting
teaching: 5
exercises: 5
---

::::::::::::::::::::::::::::::::::::::: objectives

- Explain how to reorder, rename and remove columns
- Explain how to sort data in columns

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I move, rename or remove columns in OpenRefine?
- How do I sort data in OpenRefine?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Reordering columns

You can reorder the columns by clicking the drop-down menu at the top of the first column (labelled 'All'), and choosing 'Edit columns' > 'Re-order / remove columns …'.

You can then drag and drop column names to reorder the columns, or remove columns completely if they are not required.

## Renaming columns

You can rename a column by opening the drop-down menu at the top of the column that you would like to rename, and choosing 'Edit column' > 'Rename this column'. You will then be prompted to enter the new column name.

## Sorting data

What if you want to organize your data in a way that will let you detect outliers (blanks, errors, etc.) more easily? You can accomplish this by sorting your data in OpenRefine. You can do this by clicking on the drop-down menu for the column you want to sort on, and choosing `Sort`. You can then sort your data by **text**, **numbers**, **dates** or **booleans** (**TRUE** or **FALSE** values). You can also specify what order to put blanks and errors in the sorted results.

Once applied, locate the new "Sort" button at the top of the grid.

![New Sort menu appears above grid after first sort command](fig/sort-menu-highlight.png){alt="Note the addition of a menu called Sort which appears after your first sort command. It follows the number of rows displayed."}

After clicking on the new "Sort" button, OpenRefine will present you with additional sorting options:

 - `Remove sort` - This option allows you to undo your sort.
 - `Reorder rows permanently` - This option allows you to permanently change the order of your data to the sort.
 - `By *column name*` - This option allows you to make changes to your pre-existing sort.

Unlike in Excel, 'Sorts' in OpenRefine are temporary - that is, if you remove the `Sort`, the data will go back to its original 'unordered' state.

You can sort on multiple columns at the same time by adding another sorted column (in the same way).

:::::::::::::::::::::::::::::::::::::::: instructor

## Sorting and Reorder Rows Permanently

Do not rush these last two sentences. Repeat them slowly after a pause and allow learners to explore how sorting works for a moment. 

Although the "Undo/Redo" tab is not introduced until episode 9, it may be worth noting that applying a sort does not count as a change to the data because removing the sort will restore the data to its original order. However, once you select "Reorder Rows Permanently" this does count as a data change and adds an entry to the Undo/Redo history.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- You can reorder, rename and remove columns in OpenRefine
- Sorting in OpenRefine always sorts all rows
- The original order of rows in OpenRefine is maintained during a sort until you use the option to Reorder Rows Permanently from the Sort drop-down menu

::::::::::::::::::::::::::::::::::::::::::::::::::
