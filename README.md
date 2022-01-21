# PyBer_Analysis

# Project Overview 
    The goal of this excercise was to see how we can aggregate and reorganize data to be viewed in different ways.  Specifically, formatting the data to be utilized in Charts through Matplotlib in Jupyter Notebook

# Summary of Ride-Sharing by City DataFrame
    1. After compiling the data of the 2 csvs, the city & rider data, our first task is to establish the total number of rides for each city type.  Using the 'groupby' function in association to our completed data table('pyber_data_complete_df), we can filter to the 3 types of cities within our completed table.  In addition to the 'groupby' function, we will need to use the count function in conjunction with the 'ride_id' column to total number of rides per city. 

    IMAGE DELIVERABLE 1 

    2. Next we need to find the total number of drivers per city type.  However, instead of using the combined database we revert to using the 'city_data_df'.  If we had not changed the DF then we would have run into a multiplied driver count, since each ride_id is also associated to the city type and driver count - in the coomplete data table.  Again we rely on the 'groupby' function in conjuntion with the sum function using the 'driver_count' column as its focus. The output, pictured below, provides the city types broken out with the total number of drivers. 

    IMAGE DELIVERABLE 2

    3. In the next step we follow a similar technique to capture the fares per city type.  Copying the functions used in finding the ride count, we adjust the variable of the sum to be the fares.  The formula will allow for the 3 city types to total their collective and respective fares.

    IMAGE DELIVERABLE 3

    4.  The average fare for ride was easy enought to calculate after solving problems 1 & 3.  I created a variable to hold the calculation avg fare per ride and divided the fares by city by the rides by city, as seen below.

    IMAGE DELIVERABLE 4
    
    5. Similarly, the average fare per driver was calculated by dividing the fares by city by the drivers by city.

    IMAGE DELIVERABLE 5
    
    6. Creating the summary df was repeating a process we followed several times in the last excercise with the school.  First, we create the DataFrame - then we add each of the series we have created to the list assigning more legible column names.   

    IMAGE DELIVERABLE 6
    
    7.Next we removed the index name from the column header.

    IMAGE DELIVERABLE 7
    
    8.Then we format the columns to make things neater.  We assign dollar values out to the hundreth place for 'Total Fares' 'Average Fare per Driver' and 'Average Fare per ride.  We clean up the remaining categories by assigning ',' as the deliminator in the thousands place. 

    IMAGE DELIVERABLE 8

# The Multiple Line Plot
    1.  
    
    IMAGE DELIVERABLE 1

    2.

    IMAGE DELIVERABLE 2

    3.

    IMAGE DELIVERABLE 3

    4.

    IMAGE DELIVERABLE 4

    5.

    IMAGE DELIVERABLE 5

    6.

    IMAGE DELIVERABLE 6
    
    7.
    
    IMAGE DELIVERABLE 7

    8.
    
    IMAGE DELIVERABLE 8

    9.

    IMAGE DELIVERABLE 9