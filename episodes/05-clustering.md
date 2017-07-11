---
title: "Clustering"
teaching: 10
exercises: 10
questions:
- "What is Clustering in OpenRefine and when woud you use it?"
- "How does clustering work in OpenRefine?"
objectives:
- "Explain what clustering is in OpenRefine"
- "Use clustering to identify and fix replace varying forms of the same data with a single consistent value"
keypoints:
- "Clustering is a way of finding variant forms of the same piece of data within a dataset (e.g. different spellings of a name)"
- "There are a number of different Clustering algorithms that work in different ways and will produce different results"
- "The best clustering algorithm to use will depend on the data"
- "Using clustering you can replace varying forms of the same data with a single consistent value"
---

## Clustering
The Cluster function groups together values in a column that are 'similar' and enables you to merge together several different, but similar, values into a single value.

This is very effective where you have data where there can be minor variations in data values that are likely such as names of people, organisations and places.

To use the 'Cluster' function, click on the 'Edit Cells' menu option in the relevant column and choose 'Cluster and edit...'

The 'Clusters' are created automatically according to an algorithm. There are a number of different algorithms supported by OpenRefine - some experimentation maybe required to see which clustering algorithm works best with any particular set of data, and you may find that using different algorithms highlights different clusters.

For more information on the methods used to create Clusters see [https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

For each cluster you have the option of 'merging' the values together - that is replace with a single consistent value. By default OpenRefine uses the most common value in the cluster as the new value, but you can select one of the other values by clicking the value itself, or you can simply type the desired value into the 'New Cell Value' box.

The Clustering function can also be accessed via the drop down menu at the top of a column by selecting 'Edit cells->Cluster and edit …'

>## Use Clustering to clean up author data
>* Split out the author names into individual cells using 'Edit cells->Split multi-valued cells', using the pipe "\|" character as the separator
>* Choose 'Edit cells->Cluster and edit' from the author column (which should be split into individual values from the last exercise)
>* Using the 'key collision' method with the 'fingerprint' Keying Function work through the clusters of values, merging them to a single value where appropriate
>* Try changing the clustering method being used - which ones work well?
{: .challenge}
