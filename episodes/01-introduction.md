---
title: "Introduction to OpenRefine"
teaching: 15
exercises: 0
questions:
- "What is OpenRefine? What can it do?"
objectives:
- "Explain what the OpenRefine software does"
- "Explain how the OpenRefine software can help work with data files"
keypoints:
- "OpenRefine is 'a tool for working with messy data'"
- "OpenRefine works best with data in a simple tabular format"
- "OpenRefine can help you split data up into more granular parts"
- "OpenRefine can help you match local data up to other data sets"
- "OpenRefine can help you enhance a data set with data from other sources"
---

## What is OpenRefine?
OpenRefine is described as a tool for working with ‘messy’ data - but what does this mean? It is probably easiest to describe the kinds of data OpenRefine is good at working with and the sorts of problems it can help you solve.

OpenRefine is most useful where you have data in a simple tabular format but with internal inconsistencies either in data formats, or where data appears, or in terminology used. It can help you:

* Get an overview of a data set
* Resolve inconsistencies in a data set
* Help you split data up into more granular parts
* Match local data up to other data sets
* Enhance a data set with data from other sources

Some common scenarios might be:

* Where you want to know how many times a particular value appears in a column in your data
* Where you want to know how values are distributed across your whole data set
* Where you have a list of dates which are formatted in different ways, and want to change all the dates in the list to a single common date format. For example:

| Data you have   | Desired data |
|-----------------|:-------------|
| 1st January 2014| 2014-01-01   |
| 01/01/2014      | 2014-01-01   |
| Jan 1 2014      | 2014-01-01   |
| 2014-01-01      | 2014-01-01   |

* Where you have a list of names or terms that differ from each other but refer to the same people, places or concepts. For example:

| Data you have   | Desired data |
|-----------------|:-------------|
| London          | London       |
| London]         | London       |
| London,]        | London       |
| london          | London       |

* Where you have several bits of data combined together in a single column, and you want to separate them out into individual bits of data with one column for each bit of the data. For example going from a single address field (in the first column), to each part of the address in a separate field:

| Address in single field | Institution  | Library name  | Address 1 | Address 2 | Town/City | Region | Country | Postcode |
|-------------------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|
| University of Wales, Llyfrgell Thomas Parry Library, Llanbadarn Fawr, ABERYSTWYTH, Ceredigion, SY23 3AS, United Kingdom | University of Wales | Llyfrgell Thomas Parry Library | Llanbadarn Fawr | | Aberystwyth | Ceredigion | United Kingdom | SY23 3AS |
| University of Aberdeen, Queen Mother Library, Meston Walk, ABERDEEN, AB24 3UE, United Kingdom | University of Abderdeen | Queen Mother Library | Meston Walk | | Aberdeen | | United Kingdom | AB24 3UE |
| University of Birmingham, Barnes Library, Medical School, Edgbaston, BIRMINGHAM, West Midlands, B15 2TT, United Kingdom | University of Birmingham | Barnes Library | Medical School | Edgbaston | Birmingham | West Midlands | United Kingdom | B15 2TT |
| University of Warwick, Library, Gibbett Hill Road, COVENTRY, CV4 7AL, United Kingdom | University of Warwick | Library | Gibbett Hill Road | | Coventry | | United Kingdom | CV4 7AL |

* Where you want to add to your data from an external data source:

| Data you have   | Date of Birth from VIAF (Virtual International Authority File) | Date of Death from VIAF (Virtual International Authority File) |
|-----------------|:-------------|:-------------|
| Braddon, M. E. (Mary Elizabeth) | 1835 | 1915 |
| Rossetti, William Michael       | 1829 | 1919 |
| Prest, Thomas Peckett           | 1810 | 1879 |
