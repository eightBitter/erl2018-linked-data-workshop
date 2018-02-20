## Prerequisites
1. You have [downloaded and installed](http://marcedit.reeset.net/downloads) MarcEdit onto your computer
2. You have downloaded the workshop materials from Github and saved them to an easy-to-find location like Desktop or Documents
## Step 1: Convert MARC records to .mrc 
1. Open MARCEdit
2. Click on the MARC Tools icon
3. Click on the yellow folder icon next to the Input File field and locate the file “marc_records” in the activity folder. You may need to show all file types to see the file
4. Assign the same file path to the input file, but with a .mrk file extension
5. Confirm that the MarcBreaker function is selected
6. Click Execute
![MARCEdit ready to convert ILS export to .mrk file](https://github.com/eightBitter/erl2018-linked-data-workshop/blob/master/uris-marc/screenshots/step_1.6.png)
7. Return to the folder where you saved your file and open marc_records.mrk
8. Choose File>Save as and save the file as “marc_records.mrc”
9. You should now have the .mrk and .mrc files in your folder
![Activity folder with .mrk and .mrc files](https://github.com/eightBitter/erl2018-linked-data-workshop/blob/master/uris-marc/screenshots/step_1.9.png)
## Step 2: Harvest URIs
1. Return to the MarcEdit home screen
2. Choose MARCNext, then Link Identifiers
3. Click on the yellow folder icon next to the Source File field and locate the .mrc file you created in the previous step
4. Assign the same file path to the Save File, but add an “ld” to the file name and change the extension to .mrk
5. Under ID Services, select the following check boxes:
 * AutoDetect Main/Added entry
 * AutoDetect Subject ID
 * OCLC VIAF
![MARCEdit ready to harvest URIs](https://github.com/eightBitter/erl2018-linked-data-workshop/blob/master/uris-marc/screenshots/step_2.6.png)
6. Click Process. The file should take about 3 minutes to process
## Step 3: Explore the results
1. Return to your project folder and open the file marc_records_ld.mrk
2. Choose a few records and look at the URIs that have been imported to the $0 of the following fields:
  * 100
  * 6XX
  * 7XX
3. Visit some of the HTTP URIs
![URI in MARC file](https://github.com/eightBitter/erl2018-linked-data-workshop/blob/master/uris-marc/screenshots/step_3.2.png)
## Discussion
1. What kind of information can you find?
2. What linked data sources have been used?
3. How is the data quality? Can you find any errors?
4. What could you do with this data?
