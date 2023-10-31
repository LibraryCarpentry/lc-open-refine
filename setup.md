---
title: Setup
---

## Getting ready

You need to install OpenRefine and download a data file to follow this lesson.

### Installing and running OpenRefine

OpenRefine is a free, open-source Java application. You can download OpenRefine from
[http://openrefine.org/download.html](https://openrefine.org/download.html).
This lesson has been tested with all versions of OpenRefine up to the latest tested version, 3.6.1

Packages are available on [https://openrefine.org/download.html](https://openrefine.org/download.html) for Windows, macOS, and Linux.
Please download the latest stable version, choosing the "kit" for your operating system.
Current versions of the "Windows kit with embedded Java" and "Mac kit" include everything you need to run OpenRefine.
The "Linux kit" and traditional "Windows kit" require a "Java Runtime Environment" (JRE) installed on your system (see notes below).

If you are using an older version of OpenRefine, it is recommended you upgrade to the latest tested version.

Please follow OpenRefine's manual to [install](https://docs.openrefine.org/manual/installing) and [run](https://docs.openrefine.org/manual/running) it.

When running OpenRefine, initially a command line window will open. This is a window with a black background. As OpenRefine runs, lines of text will appear in the command line window. Then the Open Refine interface will open in your default web browser. You do not need to interact with the command line window. Leave it open in the background, and work on datasets in your web browser.

Notes:

- When you download OpenRefine for Windows or Linux from the address above, you are downloading an archive file
  (zip or tar). To install OpenRefine unzip the downloaded file to a permanent location on your computer. This can
  be to a personal directory or to an applications or software directory - OpenRefine should run wherever you put the
  unzipped folder. The location has to be a "local" drive as problems have been reported trying to run OpenRefine
  from a Network drive.
- The options "Windows kit with embedded Java" and "Mac kit" include Java as part of the package. You **do not**
  need to install Java if you use one of these kits. This is the preferred method on Windows and Mac systems.
- On Windows, if you use the traditional "Windows kit" without embedded Java, you will need a
  "Java Runtime Environment" (JRE) on your system. If you do not already have JRE or JDK installed,
  you can visit [Adopt OpenJDK](https://adoptopenjdk.net/) or [Oracle Java](https://java.com/en/download/)
  to download an installer package. Please note that
  [Oracle significantly changed their license terms in 2019](https://www.oracle.com/java/technologies/javase/jdk-faqs.html) limiting it to "personal use" without a paid license. If you use OpenRefine at work or in research, OpenJDK is preferred.
- On Linux a "Java Runtime Environment" (JRE) will be required to run OpenRefine. If you do not already have
  JRE or JDK installed on your system, most distribution repositories will contain OpenJRE / OpenJDK packages.
  Install the default version available from your distribution. For example, on Ubuntu/Debian:
  `sudo apt install default-jre`.
- OpenRefine does not support Internet Explorer. Please use [Firefox](https://www.mozilla.org/firefox/new/),
  [Microsoft Edge](https://www.microsoft.com/edge),
  [Chrome](https://www.google.com/chrome/) or [Safari](https://www.apple.com/safari/) instead.

### OpenRefine cloud services

If you are unable to install OpenRefine (due to IT restrictions, for example), please try
[openrefineder using MyBinder](https://github.com/betatim/openrefineder/).
It's free to use without registration, but it's the older OpenRefine 3.4.1,
[restricted to 1-2 GB RAM](https://mybinder.readthedocs.io/en/latest/about/user-guidelines.html#resources-available),
and the server will be deleted after 10 minutes of inactivity.

[![](https://mybinder.org/badge.svg){alt='Binder'}](https://mybinder.org/v2/gh/betatim/openrefineder/6ba108b?urlpath=%2Fopenrefine)

### Downloading the data

You can download [doaj-article-sample.csv](data/doaj-article-sample.csv), which is a csv file that will open in a new browser tab. Be sure to right click or control click in order to save the file (NOTE: In Safari, right click and select **download linked file**; in Chrome and Firefox, right click and select **save link as...**). Make a note of the location (i.e. the folder, your desktop) to which you save the file.

### Exiting OpenRefine

To exit OpenRefine, close all the browser tabs or windows, then navigate to the command line window. To close this window and ensure OpenRefine exits properly, hold down [control] and press [c] on your keyboard. This will save all changes to your projects.

### Getting help

If you encounter problems installing or running OpenRefine, a good source of support is the [OpenRefine mailing list and user forum](https://forum.openrefine.org).
Include your operating system when searching to find the most relevant answers for your issue, such as threads related to [Windows](https://forum.openrefine.org/search?q=windows), [macOS](https://forum.openrefine.org/search?q=macOS), or [Linux](https://forum.openrefine.org/search?q=linux).

You may also want to check the [Stack Overflow OpenRefine tag](https://stackoverflow.com/questions/tagged/openrefine).

There are also general and specialist tutorials about using OpenRefine available on the web, including:

- Official wiki [List of OpenRefine External Resources](https://github.com/OpenRefine/OpenRefine/wiki/External-Resources)
- [Getting started with OpenRefine by Thomas Padilla](https://thomaspadilla.org/dataprep/)
- [Cleaning Data with OpenRefine by Seth van Hooland, Ruben Verborgh and Max De Wilde](https://programminghistorian.org/lessons/cleaning-data-with-openrefine)
- [Blog posts on using OpenRefine from Owen Stephens](https://www.meanboyfriend.com/overdue_ideas/tag/openrefine/?orderby=date&order=ASC)
- [Identifying potential headings for Authority work using III Sierra, MS Excel and OpenRefine](https://epublications.marquette.edu/lib_fac/81/)
- [Free your metadata website](https://freeyourmetadata.org)
- [Data Munging Tools in Preparation for RDF: Catmandu and LODRefine by Christina Harlow](https://journal.code4lib.org/articles/11013)
- [Cleaning Data with OpenRefine by John Little](https://libjohn.github.io/openrefine/)
- [OpenRefine Blog](https://openrefine.org/category/blog.html)


