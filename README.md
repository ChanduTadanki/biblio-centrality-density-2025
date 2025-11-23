# biblio-centrality-density-2025
Sep-2025: Bibliometrics Centrality vs Density from VOSViewer Data

## Motivation 
1. I use [VOSViewer](https://www.vosviewer.com) for Bibliometric analysis.  
2. [VOSViewer](https://www.vosviewer.com) does not show the Centrality vs Density strategic diagram of Author Keywords. [SciMAT](https://sci2s.ugr.es/scimat/) does.
3. However, I was not able to get them using [SciMAT](https://sci2s.ugr.es/scimat/) (I could get either Centrality or Density but not both).
4. So, decided to write my own code for it. 

## Definitions: 
1. Keywords Clusters: Density is the number of links WITHIN a cluster, whereas Centrality is BETWEEN clusters. 

## What my code does:
1. Build a graph/matrix of keywords co-occurrence (links).    
2. Map keywords to clusters. Use the clusters from GenAI from an earlier work (file: `2025-07-29a_4.7_Keywords_Clusters_k10.xlsx`).    
3. Compute each cluster's Centrality and Density    
4. Show them in a bubble chart ... bubble size depends on: #docs, or sum(citations), or avg(citations)

## Input Data Files 
1. File1: From the Scopus search, export the data. Copy this a new file with minimal columns as: `doc_id`, `citations`, `keywords`.
  1. We will use this to create a new file as: `(DocID, Keywords) (1:n) -> (Keyword, DocIDS) (1:n)`.
  2. Build a Co-Occurrence matrix of Keywords. 
3. File2: Keyword Clusters data (built using GenAI). The minimal data columns are: `Keywords`, `Cluster`. 
