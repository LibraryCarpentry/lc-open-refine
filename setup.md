---
layout: page
title: Setup
root: .
---

## Getting ready

You need to download and install OpenRefine and download a data file to follow this lesson.

### Downloading OpenRefine

You can download OpenRefine from [http://openrefine.org/download.html](http://openrefine.org/download.html). This lesson has been tested with all versions of OpenRefine up to 3.1.  

OpenRefine 3.1 is recommended. 
If using an older version, it is recommended to upgrade to the tested version (currently 3.1). 

There are versions for Windows, Mac OS X and Linux.

### Installing and Running OpenRefine

When you download OpenRefine for Windows or Linux from the address above, you are downloading a zip file. To install OpenRefine you simply unzip the downloaded file wherever you want to install the program. This can be to a personal directory or to an applications or software directory - OpenRefine should run wherever you put the unzipped folder. The location has to be a "local" drive as problems have been reported trying to run OpenRefine from a Network drive.

If you are downloading OpenRefine for Mac, you are downloading a 'dmg' (disk image) file which you can open, and then drag the OpenRefine application to an appropriate folder on you computer.

**OpenRefine is a Java application, and you need to have a 'Java Runtime Environment' (JRE) installed on your computer to run OpenRefine**. If you don’t already have one installed then you can download and install from [http://java.com](http://java.com) by going to the site and clicking "Free Java Download".

To run Refine:

* On Windows: Navigate to the folder where you’ve installed OpenRefine and either double-click ‘openrefine.exe’
* On Linux: Navigate to the folder where you’ve installed OpenRefine in a terminal window and type ‘./refine’
* On Mac: Navigate to where you installed OpenRefine and click the OpenRefine icon

The interface to OpenRefine is accessed via a web browser. When you run Refine normally this should open a window in your default web browser pointing at the address http://127.0.0.1:3333. If this doesn't happen automatically you can open a web browser and type in this address.

### Getting Help

If you encounter problems installing or running OpenRefine, a good source of support is [the OpenRefine mailing list and forum](https://groups.google.com/forum/?fromgroups#!forum/openrefine).

If you are installing OpenRefine on Windows, you may want to check the forum for ['Windows' related threads](https://groups.google.com/forum/?fromgroups#!searchin/openrefine/windows%7Csort:date) or specific threads like [Installing OpenRefine on Windows 7](https://groups.google.com/forum/?fromgroups#!searchin/openrefine/64-bit%7Csort:date/openrefine/vUzqJqJ-sAA/Tb2Om9wvaqgJ).

There are also general and specialist tutorials about using OpenRefine available on the web, including:

* [Getting started with OpenRefine by Thomas Padilla](http://thomaspadilla.org/dataprep/)
* [Cleaning Data with OpenRefine by Seth van Hooland, Ruben Verborgh and Max De Wilde](http://programminghistorian.org/lessons/cleaning-data-with-openrefine)
* [Blog posts on using OpenRefine from Owen Stephens](http://www.meanboyfriend.com/overdue_ideas/tag/openrefine/?orderby=date&order=ASC)
* [Identifying potential headings for Authority work using III Sierra, MS Excel and OpenRefine](http://epublications.marquette.edu/lib_fac/81/)
* [Free your metadata website](http://freeyourmetadata.org)
* [Data Munging Tools in Preparation for RDF: Catmandu and LODRefine by Christina Harlow](http://journal.code4lib.org/articles/11013)
* [Cleaning Data with OpenRefine by John Little](https://libjohn.github.io/openrefine/)
* [OpenRefine Blog](http://openrefine.org/category/edge-case.html)

### Downloading the data

There are a number of ways to get the data we will be using in OpenRefine.

1. Once you have started OpenRefine, use this link [https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv](https://raw.githubusercontent.com/LibraryCarpentry/lc-open-refine/gh-pages/data/doaj-article-sample.csv) to import the data directly into OpenRefine using the **Web Addresses URLs** option.

2. You can download [doaj-article-sample.csv](https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv), which is a csv file that will open in a new browser tab. Be sure to right click or control click in order to save the file (NOTE: In Safari, right click and select **download linked file**; in Chrome and Firefox, right click and select **save link as**). Make a note of the location (i.e the folder, your desktop) to which you save the file.


[template]: {{ site.workshop_repo }}
