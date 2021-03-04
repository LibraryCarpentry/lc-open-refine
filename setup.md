---
layout: page
title: Setup
---

## Getting ready

You need to install OpenRefine and download a data file to follow this lesson.

### Installing and running OpenRefine

OpenRefine is a free, open-source Java application.
This lesson has been tested with all versions of OpenRefine up to the latest tested version, 3.4.

Packages are available on <https://openrefine.org/download.html> for Windows, macOS, and Linux.
Please download the latest stable version, choosing the "kit" for your operating system.
Current versions of the "Windows kit with embedded Java" and "Mac kit" include everything you need to run OpenRefine.
The "Linux kit" and traditional "Windows kit" require a "Java Runtime Environment" (JRE) installed on your system (see notes below).

If you are using an older version of OpenRefine, it is recommended you upgrade to the latest tested version. 

Please follow the installation instructions in the OpenRefine User Manual: [Installation Instructions](https://docs.openrefine.org/manual/installing)

Notes:
* When you download OpenRefine for Windows or Linux from the address above, you are downloading an archive file (zip or tar). To install OpenRefine unzip the downloaded file to a permanent location on your computer. This can be to a personal directory or to an applications or software directory - OpenRefine should run wherever you put the unzipped folder. The location has to be a "local" drive as problems have been reported trying to run OpenRefine from a Network drive.
* In OpenRefine versions 3.4+ the options "Windows kit with embedded Java" and "Mac kit" include Java as part of the package. You **do not** need to install Java if you use one of these kits. This is the preferred method on Windows and Mac systems.
* On Windows, if you use the traditional "Windows kit" without embedded Java, you will need a "Java Runtime Environment" (JRE) on your system. If you do not already have JRE or JDK installed, you can visit [Adopt OpenJDK](https://adoptopenjdk.net/) or [Oracle Java](https://java.com/en/download/) to download an installer package. Please note that [Oracle significantly changed their license terms in 2019](https://www.oracle.com/java/technologies/javase/jdk-faqs.html) limiting it to "personal use" with out a paid license. If you use OpenRefine at work or in research, OpenJDK is preferred.
* On Linux a "Java Runtime Environment" (JRE) will be required to run OpenRefine. If you do not already have JRE or JDK installed on your system, most distribution repositories will contain OpenJRE / OpenJDK packages. Install the default version available from your distribution. For example, on Ubuntu/Debian: `sudo apt install default-jre`.
* OpenRefine does not support Internet Explorer. Please use [Firefox](https://www.mozilla.org/firefox/new/), [Chrome](https://www.google.com/chrome/) or [Safari](https://www.apple.com/safari/) instead.

### Downloading the data

You can download [doaj-article-sample.csv](https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv), which is a csv file that will open in a new browser tab. Be sure to right click or control click in order to save the file (NOTE: In Safari, right click and select **download linked file**; in Chrome and Firefox, right click and select **save link as...**). Make a note of the location (i.e. the folder, your desktop) to which you save the file.

### Getting help

If you encounter problems installing or running OpenRefine, a good source of support is [the OpenRefine mailing list and forum](https://groups.google.com/g/openrefine).
Include your operating system when searching to find the most relevant answers for your issue.

There are also general and specialist tutorials about using OpenRefine available on the web, including:

* [Getting started with OpenRefine by Thomas Padilla](http://thomaspadilla.org/dataprep/)
* [Cleaning Data with OpenRefine by Seth van Hooland, Ruben Verborgh and Max De Wilde](http://programminghistorian.org/lessons/cleaning-data-with-openrefine)
* [Blog posts on using OpenRefine from Owen Stephens](http://www.meanboyfriend.com/overdue_ideas/tag/openrefine/?orderby=date&order=ASC)
* [Identifying potential headings for Authority work using III Sierra, MS Excel and OpenRefine](http://epublications.marquette.edu/lib_fac/81/)
* [Free your metadata website](http://freeyourmetadata.org)
* [Data Munging Tools in Preparation for RDF: Catmandu and LODRefine by Christina Harlow](http://journal.code4lib.org/articles/11013)
* [Cleaning Data with OpenRefine by John Little](https://libjohn.github.io/openrefine/)
* [OpenRefine Blog](https://openrefine.org/category/blog.html)

[template]: {{ site.workshop_repo }}
