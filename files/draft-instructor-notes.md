# Chris Erdmann Instructor notes from https://libcce.github.io/2018-10-18-UNC/

## OpenRefine

OpenRefine is a power tool for messy data
Helps you clean data, link data, visualize it and keeps a record of your revisions
Its been around for a while (GoogleRefine), which means there is a lot of info/tutorials about it out there


Things it’s great for:

overview of data/analysis of data per column
* Resolve inconsistencies (date format)
* Split data into separate cells (multiple names, address parts)
* Matching data, like your local data to Library of Congress data
* Enhance data with data from other sources

Scenarios:
* how many times does a value appear in a column?
* How is data distributed across the dataset?
* changing all data in a column into one format
* splitting data into separate columns
* adding data


Local library examples:
UNCG Library uses it for collections data
Duke Libraries uses it for teaching workshops

Open Context
https://opencontext.org/
Eric Kansa
Uses OpenRefine in its data cleaning workflows

In the Carpentries
OpenRefine for Ecologists
https://datacarpentry.org/OpenRefine-ecology-lesson/


Import > DOAJ data
https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv


Note:
UTF-8
First line is column header
DO NOT check parse text cells into numbers

View on raw data

Records/rows
Flags/stars

Split multi value cells
Authors > Edit Cells > Split Multi Valued Cells
Notice number of rows versus number of records
Authors > Edit Cells > Join Multi Valued Cells

Note: Undo / Redo
We can use this as well if we want to undue something we did
Note: Extract (like a Macro)


Challenge:
1. What separator character is used in the Subjects cells?
2. How would you split these subject words into individual cells?
3. How would you join them back together?

<Green sticky>

## FACETING
Used for overview of the data and creating consistency

Publisher > Text Facet
Count
Name

2 ways of merging names -> cluster button or roll over and edit

Include and exclude for filtering

Challenge:
1. What types of licenses are found in this data set?
2. How many are blank? From what journal?

Note:
I've used this feature, copy and pasted facets, for easy reporting

Explore Text Facet
- How would we find DOIs that are blank with the Text Facet?
  Facet > Customized Facets > Facet by Blank
- Use Text Facet to normalize Language (EN e.g.).

## Clustering

This allows us to use various algorithms to find name variations and then match

Authors > Edit Cells > Split multi-value cells
Authors > Edit Cells > Cluster and Edit

Explore Method / Keying Function

READ
https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth

## Sort / View (like Excel functionality)
Sort A-Z or Z-A
View > Collapse

## Transformations

Allow you to do much more than Facets
You can split values (into new columns), for instance, journal information, addresses...
Standardization, removing punctiation maybe or formatting date
Extracting something from a string like ISBN, geographical coordinates

Publisher > Text Facet
Why does MDPI AG appear twice, looks the same?
Edit cells->Common transforms->Trim leading and trailing whitespace
That is a transformation to start!

## Write Transformations

Citation > Edit Column > Add Column based on this one
GREL - Google Refine Expression Language

What if you wanted to get the volume? 
value.match(/.*?(\d+).*?/)[0]


What if you wanted to get the year?
Answer?
value.match(/.*(\d{4}).*/)[0]
value.match(/.*?\((\d+)\).*?/)[0]
value.match(/.*?\d+.*?\d+.*?\d+.*?\d+.*?(\d+).*?/)[0]
value.match(/.*\((\d{4})\).*/)[0]
value.match(/.*?((\d\d\d\d)\).*?)[0]
value.match(/.*?(\(\d{4}\)+).*?/)[0]

What if you wanted to get the journal name?
Answer?
value.match(/.*?([A-Za-z\s]*)((\(|,)).*?/)[0]
value.match(/(.*?),(.*)/)[0]
value.match(/(.*?)(, ).*?/)[0]
value.match(/(.*?),.*/)[0]
value.match(/^(.*?),.*?/)[0]
value.match(/.*(^((\w+)(\s*)){1,})+.*/)[0]

Google OpenRefine Recipes
https://github.com/OpenRefine/OpenRefine/wiki/Recipes
Lots of examples (ISBN e.g.)

https://libjohn.github.io/openrefine/

- That's something you can do with unstructured data but we know we can grab structured data... from CrossRef for example.

- Does anyone know how we would do that?
Answer:

Remember:
Publisher > Text Facet and choose Society of...
ISSNs > Edit Column > Add Column based Fetching URL
"http://api.crossref.org/journals/"+value
Get JSON back...

How do we get the journal title from the JSON?
Answer:


## Booleans
You can check whether a condition is TRUE or FALSE
Authors > Facets > Custom Facet
Value.contains(",") 


## Reverse author names

You can use Regex again
Authors > True contain "," > Edit Cells > Transform

value.match(/(.*),(.*)/).reverse().join(" ")


## Reconcile

Wikidata on Subjects
Subjects > Start Reconciling > Wikidata > Academic discipline

ORCID
http://refine.codefork.com/
Use: Author Names
http://refine.codefork.com/reconcile/orcid/smartnames

https://www.lib.ncsu.edu/news/orcid%3A-the-number-that-every-academic-needs

## Date to String
Edit Cells > Common transforms > to Date
Edit Column > Add Column based on
value.toString("dd MMMM yyyy")

## Sharing
Export options
Share your recipes on GitHub


Things to note:

Allocate more memory:
https://docs.openrefine.org/manual/installing/#increasing-memory-allocation


Extra:
Transpose http://ssrc.doingdh.org/tidying-data-with-openrefine/
