# LEDE Project 1
## After more than ten years, tech swimsuits are a thing of the past

This repository include the jupyter notebooks used to collect, clean and analyze data for the first project I've worked on as a part of the Lede program for Data Journalism, an intensive summer program from Columbia Graduate School of Journalism.

### Read the story : [After more than ten years, tech swimsuits are a thing of the past](https://marcodallastella.github.io/swimming)

### Notebooks:

* [1. Getting the data](1_swimming_data.ipynb)
* [2. Cleaning the data](2_swimming_cleaning.ipynb)
* [3. Analysing the data](3_swimming_analysis.ipynb)

### 1. Getting the data

This notebook uses the hidden API the World Aquatics to collect information regarding the top-50 times registered for every individual race since 1972 to 2023.

Because not all four strokes have the same races, it is composed of three sections:

* 1. Common races: collect data for the 50, 100, 200 meters in the four strokes
* 2. Freestyle-specific races: collect data for the 400, 800 and 1500m freestyle.
* 3. Medley-specific races: collect data for the 200 and 400 meters medley.

Then save the results in the `output.csv` file.

### 2. Cleaning the data

I used this notebook to clean the data and extract what I needed for my analysis.

* From the `output.csv` file, only selects columns that I am interested in, and change the date to have only the year of each time.

* I wanted to format the `time` value in a way that I could use to do some math. To do so, I formatted it in a `timedelta` object and used it to calculate the seconds of each time.

* Fix a mistake in the dataset, which I noticed only after, that included eleven times wrongly categorized as 800m instead of 1500m.

Output: `2_output_clean.csv`

* Reduce the dataset to havea coherent set of entries for each year and for yeach discipline. Because of a lack of data from World Aquatics, this passage was particularly painful as it forced me to reduce my analysis to the top-10 times since 1991.

Output: `2_output_top10.csv` file.

### 3. Analyzing the data

I used this notebook to analyze my dataset and see if I can spot some interesting trend. Eventually, I decided to focus on two aspects:

* Compare the average time for the top-10 times for each discipline, and focus on how this changed during the tech-swimsuit revolution of 2007 and 2008. To do so, I calculated average times in seconds for each discipline in each year, and then calculate the percentage change compared to the starting year of 1991.
Output: `3_pivot_average.csv`.

* See how many world records were set in each year.
Output: `3_wr_years.csv`

Marco Dalla Stella
[md3934@columbia.edu](mailto:md3934@columbia.edu)