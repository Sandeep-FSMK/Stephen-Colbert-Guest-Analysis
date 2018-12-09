# Stephen-Colbert-Guest-Analysis

Demographics analysis of guests appeared in  'The Late Show with Stephen Colbert'

1.Motivation for the project
2.Data Gathering and Preparation. 
3.Analysis. 
4.Blog Post. 
5.Summary of the results of the analysis

### 1.Motivation for the project 

Impartial analysis of the regular content we consume matters more than ever because of the filter bubble we are in.
Filter bubble is a state of intellectual isolation that can result from personalized searches . In the age of post-truth, we hear over and over again the truth which we would like to hear. Also, content makers tend to manufacture political dichotomies to grow the audience in an already divided nation.

With millions of Americans watching The Late Show with Stephen Colbert every night, the show has an unparalleled influence. There are academic studies on the Stephen’s real-world impact. Colbert Bump is a term coined by the social scientist James H. Fowler. It means an increase in popularity of a person or thing as a result of appearing as a guest on or being mentioned on the show. In Fowler’s research, it is found that contributions to Democratic politicians rose 40% for 30 days after an appearance on the show! Although this research was about Colbert Report -Stephen Colbert’s previous show — its validity remains.

### 2.Data Gathering and Preparation

I have taken the data from wikipedia https://en.wikipedia.org/wiki/List_of_The_Late_Show_with_Stephen_Colbert_episodes . I have used two programs for the data extraction Talkshow_Data notebook to scrape and clean data. This creates two CSV files. episode_details.csv and guest_details.csv.Basic wrangling and cleaning of the data is done in the notebook Talkshow_Data. episode_details.csv contains the individual episode details and guest_details.csv contains guest name and wikipedia link of the guest name. After that guest_details.csv undergoes some kind of cleaning steps to make the names standardized. For e.g in some places name wil be 'Vice President Joe Biden' but some episodes it would be 'Joe Biden'.These data cleaning was done manually and the new file is guest_details_01.csv

*guest_details_01.csv* will be the input for the next program profile_data. This program goes to the each record from guest details csv and pull out following information from the personal wikipedia page

1.Name.  
2.Age.    
3.Country born.   
4.State Born.   
5.City Born.   
6.Nationality.   
7.Almamater.   
8.Education.   
9.Occupation.   
10.Political party.  

It creates a CSV file called *profile_details.csv*.

*profile_details.csv* goes through various manual wrangling phases like filling in the missing information which program couldn't fetch from the wikipedia and correcting the formats. I have also used Tableau Prep to split the fields, identify duplicates. A short summary of the wrangling phases . I have preserved the files if some one is intereseted to go through the wrangling process

### These are the versions 

*profile_details_01.csv* - Cleaned the Occupation and Education categories in such a way that it can be read as a python list . Because of the non standard format of wikipedia data ,the downloaded data wasn't in a proper format. Manually checked the nationalities and cleaned up State , City and Country fields .

*profile_details_02.csv* - Added Gender field manually . And deleted some more duplicates

*profile_details_03.csv* - Splitted Education and Almamater fields to handle multiple values

*profile_details_04.csv* - Categorized different occupations to 7 groups for the sake of clarity and analysis

*profile_details_05.csv* - Created universities.csv from education and almamater fields and removed those fields from this file. Data_Cleaning program has been used for this . Also cross checked political affiliations.

The biggest challenge I have faced in data cleaning was the non uniform structure of the wikipedia data. It made it almost impossible to do certain wrangling programmitaclly.

### 3.Analysis.    

Much of the analysis and visualization has been done in Tableau and I have used profile_details_05.csv for this. I have included Tableau worksheet Medium_Post.twbx in this repository. In the program Data_Cleaning I have done some statistical analysis of the variable age.

### 4.Blog post.  

https://medium.com/@sandeep.tvla/these-5-data-visualizations-will-make-you-see-late-show-with-stephen-colbert-in-a-new-light-34e03cc2541d

This is the link to the blog post.

### 5.Summary of the results of the analysis

Entertainment and show business segment which contributes to 76% of the total guests. 

Gender gap in the show is 30 percentage points in favor of men. 

The average age of the guests is 47 years with a standard deviation of 13.56 which indicates the distribution of age.  

Out of 71 American guests whose political views are marked as either Republican or Democrat, there are three times more Democrats than Republicans.  



