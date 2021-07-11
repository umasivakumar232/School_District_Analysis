# School District Analysis

## Overview of the school district analysis

Here we are tasked with helping Maria the chief data scientist for a city school district analyze data from different schools in the district. Her role involves preparing all standard test data for analysis, reporting and presentation to the school board. Her insights are used to inform discussions and assist the school board in making strategic decisions at the school and district levels regarding school funding and priorities. The data for this analysis comes from two datasets both in csv format.  

* school_complete.csv - school ID, school_name, school_type, size, budget 
* student_complete.csv -   student ID, name, gender, grade, school_name, reading_score and math_score

## Resources

   * Anaconda – versions 4.10.3
   * Jupyter Notebook – version 6.10.0
   * Python – version 3.8.8

## Initial Analysis

The stepwise process we followed to analyze the PyCitySchool data in below 

### Check CSV   

   * Its easy enough to look at the school_complete.csv and check if there are any missing data because it has only 15 rows of data. 
   * Student_complete.csv however has 39000+ records and hence its cumbersome to do this manually. We use pandas to help us fix certain anomalies.
   * Dealing with null values
   * Handling missing data if any
   * Determine the data types are correct 
   * Correct Incorrect prefixes and suffixes
   * Create a clean_student_complete.csv which we use for further analysis

### Merge DataFrames

In order to do our analysis we need to merge the two DataFrames and perform analysis on the single merged DataFrame. 
We use the **school_name** column which is common to both DataFrames when we merge. We call this **school_data_complete_df**.
Now we can begin analyzing our data to obtain the insights.

### School District Summary

The school district summary is a high-level snapshot of the district's key metrics and contains 
     
     * Total number of students 
     * Total number of schools
     * Total budget
     * Average math score
     * Average reading score
     * Percentage of students who passed math
     * Percentage of students who passed reading
     * Overall passing percentage
We create a new DataFrame called school_district_df with all the above. We format it for better readability and visualize it as shown below

<img width="691" alt="Original_district_summary" src="https://user-images.githubusercontent.com/85518330/125210695-0b0f6800-e267-11eb-9211-24496c8640c7.png">

### School Summary

Next we create a DataFrame called school_summary_df using key metrics below for each school.   
    
    * School name
    * School type
    * Total students
    * Total school budget
    * Per student budget
    * Average math score
    * Average reading score
    * % passing math
    * % passing reading
    * % overall passing
The resulting DataFrame after some formatting for better readability looks as shown below

<img width="486" alt="Original_per_school_summary" src="https://user-images.githubusercontent.com/85518330/125210773-7c4f1b00-e267-11eb-96bf-aefc9c9d350f.png">

### Highest performing schools 

We get this by sorting the per_school_summary_df DataFrame on the % Overall Passing column from the highest % Overall Passing to the lowest. We print the top 5 and bottom 5 schools into a table for the purpose of our analysis

* Top 5 performing Schools
<img width="723" alt="Original_top_5_schools" src="https://user-images.githubusercontent.com/85518330/125210821-bd472f80-e267-11eb-9df9-8263eac43652.png">

* Bottom 5 performing Schools
<img width="726" alt="Original_bottom_5_schools" src="https://user-images.githubusercontent.com/85518330/125210822-c6d09780-e267-11eb-90b8-cf2996365ef3.png">

### Grade Level Summary

Here we create two new DataFrames, one that will display the average math scores for each grade, and the one that will display the average reading scores for each grade. These will be grouped by the name of the school.

   * Gradewise Math Scores
<img width="173" alt="Original_gradewise_math_scores" src="https://user-images.githubusercontent.com/85518330/125210906-35adf080-e268-11eb-9535-b0c965ffec02.png">

  * Gradewise Reading Scores
<img width="175" alt="Original_gadewise_reading_scores" src="https://user-images.githubusercontent.com/85518330/125210882-14e59b00-e268-11eb-95af-e18c9ee96376.png">


### Spending Bins Summary

To create this DataFrame, we need to do the following: Group the schools into four bins, or ranges, based on the budget per student. For each spending range, get the following data: Average math and reading scores The percentage of students passing math and reading The overall passing percentage, which is the average of the percentage of students passing math and reading

<img width="480" alt="Original_spending_bins_scores" src="https://user-images.githubusercontent.com/85518330/125210947-6db53380-e268-11eb-9ede-1ae9a0f1c57e.png">


### School Size Summary

We create 3 bins called small, medium and large based on the number of students in each school. For each bin, get the following data Average math and reading scores The percentage of students passing math and reading The overall passing percentage, which is the average of the percentage of students passing math and reading

<img width="439" alt="Original_school_size_scores" src="https://user-images.githubusercontent.com/85518330/125210965-802f6d00-e268-11eb-8d85-05217edeab76.png">


### School Type Summary 

Here we'll group the scores by the type of school: district or charter. For each type of school, we'll calculate the average math and reading scores, math and reading passing percentages, and overall passing percentage for each bin

<img width="428" alt="Original_school_type_scores" src="https://user-images.githubusercontent.com/85518330/125210980-8aea0200-e268-11eb-9d77-5fe7e9836a46.png">


## Summary of Findings

The data provided gives us details of the math and reading scores of 39170 students in grades 9th-12th studying across 15 schools.

  * At a district level overall passing % of both math and reading is 65%, math has a lower passing % compared to reading 
  * Cabrera, Thomas, Griffin, Wilson and Pena High School are the top 5 performing schools based on overall % passing
  * Rodriguez, Figueroa, Huang, Hernandez, Johnson High School are the bottom 5 performing schools based on overall % passing 
  * Grade wise performance of top 5 schools indicates that math scores are generally lower than reading scores but the scores remain consistent across grades
  * Ironically schools where per student spending is higher have performed more poorly. This means that, increasing the per student budget has little impact on performance 
  * Smaller and medium sized schools are performing much better than larger schools. Perhaps that is because the schools are able to focus more on their students 
  * Charter schools are performing much better than district schools

 
