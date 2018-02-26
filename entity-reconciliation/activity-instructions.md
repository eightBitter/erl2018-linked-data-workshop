## Prerequisites

1. [Download and install](http://openrefine.org/download.html) the latest version of OpenRefine
2. If you haven't already, download the workshop materials from Github and save them to an easy-to-find location like Desktop or Documents

## Step 1: Load dataset into OpenRefine

1. Open OpenRefine
2. Click Create Project -> This Computer -> Choose Files. Navigate to the workshop materials and find/open `serials-records.txt`. Click Next
3. Keep all default settings. Name the project whatever you like, and click Create Project

## Step 2: Clean the data

1. Rename columns
	- For each column, click dropdown of column -> Edit column -> Rename this column
		- 022$a to ISBN
		- 245$a to title
		- 260$b to publisher
2. Split out multiple publishers into multiple columns
	1. Click dropdown next to publisher column
	2. Click Edit column -> Split into several columns. Choose semicolon for Separator, and click OK
3. Remove trailing commas
	1. For each publisher column, click dropdown -> Edit cells -> Transform
	2. Enter the following into the text box: `replace(value,/\,$/,"")`.
	1. Click OK
4. For each publisher column, click dropdown -> Edit cells -> Transform. Use GREL to remove square brackets

## Step 3: Reconcile publisher names

1. Click dropdown -> Reconcile -> Start reconciling
2. Click Add Standard Service. Enter the following URL: http://refine.codefork.com/reconcile/viaf
	- [More info about this reconciliation service](http://refine.codefork.com/)
3. Click VIAF. Choose Corporate Name. Click Start Reconciling. This will take a few minutes

## Review results

1. If there are multiple options, assess the options and choose the most appropriate one

## Pull out URIs

1. Click dropdown -> Edit column -> Add column based on publisher 1 column. Enter the following: `cell.recon.match.id`. Name the column VIAFID
2. Click dropdown of VIAFID column -> Edit column ->  Add column based on VIAFID column -> Enter the following: `“http://viaf.org/viaf/” + value`. Name the column VIAFURI

## Bonus: Pull in data using URI

1. Click dropdown of VIAFURI -> Add column by fetching URLs based on column VIAFURI
	- Enter the following into the text box: `value + ".rdf"`. This will take a few minutes
	- We'll discuss results and opportunities
