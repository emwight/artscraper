# FBI API: Art Crimes
This repository contains code used to collect and clean data from the [FBI art crimes API](https://api.fbi.gov/docs#!/) and the resulting dataset. All information obtained from the API is public and can also be accessed through the [National Stolen Art File](https://www.fbi.gov/investigate/violent-crime/art-theft/national-stolen-art-file).

## Collection and Cleaning Process
I randomly sampled pages through API created the initial dataset, then went through extensive cleaning to create the stolen_art csv. For a more extensive explanation of the process, see [my blog post](https://emwight.github.io/stat386-projects/2022/10/19/Last-Seen-the-FBI-API-for-Art-Crimes.html)!

Additionally, check back in by November 9th for an EDA of these art crimes!

## Data Description
The `stolen_art.csv` file, created using the `artscrape.ipynb` code, has 400 observations with the following variables:

**title:** Title of the stolen art piece

**maker:** Creator of said art piece, ranging from specific people to countries

**crimeCategory:** General type of art piece stolen, such as painting, sculpture, and book

**materials:** Within each general category, the materials used to make the art piece. Painting, for example, includes oil paint, board, canvas, and wood

**period:** The century the art piece was created

**size:** Quantitative size of the art piece

**units:** Whether the size is a measure of length (inches), area (square inches), or volume (cubic inches)

