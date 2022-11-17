# FBI API: Art Crimes
This repository contains code used to collect and clean data from the [FBI art crimes API](https://api.fbi.gov/docs#!/) and the resulting dataset. All information obtained from the API is public and can also be accessed through the [National Stolen Art File](https://www.fbi.gov/investigate/violent-crime/art-theft/national-stolen-art-file).

## Collection and Cleaning Process
I randomly sampled pages through API created the initial dataset, then went through extensive cleaning to create the stolen_art csv. For a more extensive explanation of the process, see [my blog post](https://emwight.github.io/stat386-projects/2022/10/19/Last-Seen-the-FBI-API-for-Art-Crimes.html)! I also cleaned a new dataset with more observations for [this EDA](https://emwight.github.io/stat386-projects/), with major changes to my process documented below.

### Changes to Data Cleaning Process Since Blog Post

 - **API**: While I originally thought that there were 50 max pieces per page, and asking the API for 25 pieces would sample the first 25 pieces from that page of 50, I discovered that the number of pieces requested determined how long the pages were and how many pages there were in total. In other words, if there were 30 pages of 50 pieces each, asking the API for 25 pieces would increase the number of pages to 60. This was corrected in my new code to get a more random and representative sample of pages.

 - **Categories:** General changes were made to reduce the number of categories for each quantitative variable. One major change was changing all categories with 5 or fewer cases to "other"

 - **materials**: To improve grouping, this variable was split into two variables as explained in the New Data Description below
 
 - **size and units**: The pattern of "Diameter: 2" to "3.14" was correct mathematically, but didn't account for the dimensional move from length to area. This was changed to "3.14 x 1" to preserve the 2D measurement

## New Data Description
The `stolen_art_new.csv` file, created using the `artscrape_new.ipynb` code, has 1000 observations with the following variables:

 - **title:** Title of the stolen art piece

 - **maker:** Creator of said art piece, ranging from specific people to countries

 - **crimeCategory:** General type of art piece stolen, such as painting, sculpture, and book

 - **primaryMaterials:** The material that was first listed for each piece
 
 - **numMaterials:** The total number of materials used to create each piece

 - **period:** The century the art piece was created

 - **size:** Quantitative size of the art piece

 - **units:** Whether the size is a measure of length (inches), area (square inches), or volume (cubic inches)

## Old Data Description
The `stolen_art.csv` file, created using the `artscrape.ipynb` code, has 400 observations with the following variables:

 - **title:** Title of the stolen art piece

 - **maker:** Creator of said art piece, ranging from specific people to countries

 - **crimeCategory:** General type of art piece stolen, such as painting, sculpture, and book

 - **materials:** Within each general category, the materials used to make the art piece. Painting, for example, includes oil paint, board, canvas, and wood

 - **period:** The century the art piece was created

 - **size:** Quantitative size of the art piece

 - **units:** Whether the size is a measure of length (inches), area (square inches), or volume (cubic inches)

