# ChEA-KG: Exploring a Novel Human Gene Regulatory Network
### Table of Contents
1. [The ChEA-KG GRN](#introduction)
    1. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Searching the KG](#grn-search)
		1. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Single Term Search](#single-search)
        2. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Subnetwork Search](#subgraph-search)
		3. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Two Term Search](#two-term-search)
    1. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Interacting with the network](#interact-network)
        1. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Adjust network view](#adjust-vew)
        2. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Download network](#download)
2. [Enrichment analysis with ChEA-KG](#chea-enrichment)
	1. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Subnetwork](#enrichment-subnetwork)
	2. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Search parameters](#enrichment-params)
	3. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Perform a query](#perform-query)


## **The ChEA-KG GRN** <a name="introduction"></a>
***Nodes***
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Nodes in the ChEA-KG are human transcription factors cataloged by [ChEA3](https://maayanlab.cloud/chea3/). 
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Each node is associated with an **id, label**, and **URI** that points to the NCBI gene page for that gene.

<p>&nbsp;</p>
***Edges***
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Edges in the GRN indicate regulatory relationships between source and target TFs, inferred from enrichment analysis.  
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; There are two edge types: 
    1. <span style="color: red;">Red</span> plungers indicate downregulation
    2. <span style="color: green;">Green</span> arrows inidcate upregulation
<p>&nbsp;</p>

### **Searching the ChEA-KG GRN** <a name="grn-search"></a>
Click and drag on any node to move it. 

#### *One-term search* <a name="single-search"></a>
Generate a subnetwork of itneractions between a single transcription factor and its neighboring nodes by inputting the gene symbol for a transcription factor into the search bar under "Start with". Type in the gene symbol. If it exists in the network, it will be shown in the autocomplete menu. Click on the matching name to view the results. 

#### *Subgraph search* <a name="subgraph-search"></a>
Generate a subnetwork with a given number of relationships by toggling the "End Node" switch. Leave the "End with" field **blank**. Control the size of the subnetwork using the slider above the network view. 

#### *Two-term search* <a name="two-term-search"></a>
The two-term search generates a shortest path between two transcription factor nodes. Enter a starting transcription factor in the "Start with" field. Toggle the "End Node" switch, then input a desired end node in the "End with" field. The result displays a shorest path between the two nodes. In the case where there is a tie for a shortest path length, all paths of that length are shown. 

### **Interacting with the network** <a name="interact-network"></a>
The toolbar above the network view provides several buttons to further interact with the network. From left to right, these are Size, Full-screen, Network view, Table view, Save subnetwork, Download graph as an image file, Show tooltip, Switch graph layout, Show edge labels, and Show legend.  

To move a node in the network view, click and drag. 

#### *Adjust the network view:* <a name="adjust-view"></a>
The toolbar above the network view provides the following buttons to further interact with the network, from left to right: 
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Adjust subnetwork size: Adjust the size slider to limit the number of relationships displayed for that network
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Full-screen: Click the full-screen button to view the network search page in full-screen
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Enable the tooltip: The tooltip displays the ID, label, and URI for each node when the mouse hovers over a node in the network. It also provides options to remove or expand a ndoe.  
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Remove or expand a node: With the tooltip enabled, hover over the node of interest and click on the remove or expand buttons. 
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Network and table view: Toggle between network and table view by clicking on their respective buttons
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Switch graph layout: Switch between force-directed, geometric, or hierarchical graph layouts. 
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Show edge labels: Display the edge labels ("upregulates", "downregulates") over the edges
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Show legend: Show the legend. An additional toolbar button is displayed that adjusts the size of the legend when clicked. 
<p>&nbsp;</p>

#### *Download the subnetwork:*  <a name="download"></a>
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Save subnetwork: Save the subnetwork to a file. This produces two files: 
    - nodes.csv has the fields [id, label, kind, uri, color]
    - edges.csv has the  fields [source, target, relation, source_label, target_label, kind, p_value, z_score]
- &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Download graph as an image file: Save a PNG, JPG, or SVG image of the network view

## **Enrichment analysis with ChEA-KG** <a name="chea-enrichment"></a>
The enrichment analysis page provides an option to visualize a subnetwork of the GRN based on ChEA3 enrichment analysis results. 

### Enrichment analysis subnetwork <a name="enrichment-subnetwork"></a>
The subnetwork returned by this feature contains transcription factors with the highest integrated mean rank for that gene set. By default, the top 10 ranked TFs are returned. The ChEA3 integrated mean rank is calculated from the average rank across six libraries: Enrichr Queries, GTEx Coexpression, ARCHS4 Coexpression, ENCODE ChIP-seq, Literature ChIP-seq, and ReMap ChIP-seq. For more information on how the ChEA3 Integrated Mean Rank is calculated, visit the [ChEA3 website](https://maayanlab.cloud/chea3/). 

### Enrichment analysis search parameters: <a name="enrichment-params"></a>
There are three advanced search options that can be adjusted by toggling "Advanced Options". 
1. Minimum libraries: This filters out nodes from the enrichment results if they occur in fewer than the specified number of ChEA3 libraries (maximum of 6)
2. Maximum edge p-value: Specify the maximum p-value of an edge. 
3. Specify number of nodes: Specify how many top ranked nodes. 
<p>&nbsp;</p>

### Perform a query:<a name="perform-query"></a>
To perform a query, input a list of newline-separated Entrez gene symbols into the text box. Alternatively, click "try an example" to use an example gene set. Add a description under the "Description" field. Adjust the advanced options as necessary. Click submit. 