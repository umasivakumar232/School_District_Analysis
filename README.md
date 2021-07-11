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



### School Summary
Next we create a DataFrame called school_summary_df using key metrics below for each school.   
•	School name
•	School type
•	Total students
•	Total school budget
•	Per student budget
•	Average math score
•	Average reading score
•	% passing math
•	% passing reading
•	% overall passing
The resulting DataFrame after some formatting for better readability looks as shown below
### Highest performing schools 
We get this by sorting the per_school_summary_df DataFrame on the % Overall Passing column from the highest % Overall Passing to the lowest. We print the top 5 and bottom 5 schools into a table for the purpose of our analysis
###Grade Level Summary
Here we create two new DataFrames, one that will display the average math scores for each grade, and the one that will display the average reading scores for each grade. These will be grouped by the name of the school.
### Spending Bins Summary
To create this DataFrame, we need to do the following: Group the schools into four bins, or ranges, based on the budget per student. For each spending range, get the following data: Average math and reading scores The percentage of students passing math and reading The overall passing percentage, which is the average of the percentage of students passing math and reading
### School Size Summary
We create 3 bins called small, medium and large based on the number of students in each school. For each bin, get the following data Average math and reading scores The percentage of students passing math and reading The overall passing percentage, which is the average of the percentage of students passing math and reading
### School Type Summary 
Here we'll group the scores by the type of school: district or charter. For each type of school, we'll calculate the average math and reading scores, math and reading passing percentages, and overall passing percentage for each bin
