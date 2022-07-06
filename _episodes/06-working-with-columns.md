---
title: "Working with columns and sorting"
teaching: 5
exercises: 5
questions:
- "How do I move, rename or remove columns in OpenRefine?"
- "How do I sort data in OpenRefine?"
objectives:
- "Explain how to reorder, rename and remove columns"
- "Explain how to sort data in columns"
keypoints:
- "You can reorder, rename and remove columns in OpenRefine"
- "Sorting in OpenRefine always sorts all rows"
- "The original order of rows in OpenRefine is maintained during a sort until you use the option to Reorder Rows Permanently"
---

## Reordering columns
You can re-order the columns by clicking the drop-down menu at the top of the first column (labelled 'All'), and choosing `Edit columns->Re-order / remove columns …`.

You can then drag and drop column names to re-order the columns, or remove columns completely if they are not required.

## Renaming columns

You can rename a column by opening the drop-down menu at the top of the column that you would like to rename, and choosing 'Edit column' > 'Rename this column'. You will then be prompted to enter the new column name. 

## Sorting data
You can sort data in OpenRefine by clicking on the drop-down menu for the column you want to sort on, and choosing `Sort`.

Once applied, locate the new "Sort" button at the top of the grid, pictured in [documentation](https://docs.openrefine.org/assets/images/sort2-3db578c2c60877a5d84129e51ff48021.png). 

"Change the order in which sorts are applied" is not the same as the sort order for a particular column. If  a project has an Author column and a Title column, applying sorts on both columns, then the new "Sort" drop down menu offers:

* Sort by title, then by author (so if two books had the same title but different authors, the two rows for that title would be next to each other in the sort, but ordered by the author name).
* Sort by author, then by title (so if one author had written multiple books, the rows for that author would be grouped together, ordered by the title of the book).

Unlike in Excel, 'Sorts' in OpenRefine are temporary - that is, if you remove the `Sort`, the data will go back to its original 'unordered' state. The 'Sort' drop-down menu lets you amend the existing sort (e.g., reverse the sort order), remove existing sorts, and/or make sorts permanent.

To sort multiple columns, click on the drop-down menu for the second column you want to sort and choose `Sort`. In the new Sort dialog box, make sure that `sort by this column alone` is not checked.
