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
    1.  The first step in the process of creating teh muli-line plot showing Total Fares by City Type, is to confirm that we can read the merged dataframe.  This was created for us in the starter code provided.  
    
    IMAGE DELIVERABLE 1

    2.  Using the groupby function as we did during the Summary df process, we can create a new data frame that is filtered.  The filtering request was that we use both 'date' and 'type'  within the groupby function.  This requires small adjustments to the previously utilized code, as seen below.  Similarly to our previous steps we used the sum function on our filtered df to get the fare by date and city type. 

    IMAGE DELIVERABLE 2

    3.  Next we are asked to reset the index of our filtered df from the previous step.  The example code provided a clear direction to derive the use of the reset_index function.  Adding in the numbered index allows us to utilize the new pivot function in our next step. 

    IMAGE DELIVERABLE 3

    4.  Using the pivot function we are meant to create a pivot table off of our updated data frame some step 3.  Having accumulated the totals by city and by time, the pivot function would allow for a more legible design of the chart.  Using the .pivot_table function allows us to set, the variables for index, columns & values for our pivot chart.  In the example below you can see that we opted to add the date as the index, the type of city as the columns and the fares as the crossectional values. 

    IMAGE DELIVERABLE 4

    5.  This next step was more difficult to solve since the request necessitated that we filter our dataframe even further, to only those dates that are between 2019-01-01 & 2019-04-29.  Having limited experience with such a request, it took me several failed attempts and searches to find the appropriate adjusment to the loc function. However, suprisingly the code resounded rather similarly to that of an excel code, using the >= & <= operators to determine the start and end dates, as seen below.  

    IMAGE DELIVERABLE 5

    6.  Next we are asked to update the index datatype to be datetime.  Luckily I was able to use the video hint as an assistance as it proved rather difficult to understand the example provided.   

    IMAGE DELIVERABLE 6
    
    7.  Following the change of the datatype we double check that the change was in fact effective, by running the .info() function.  As shown in the 2nd line of the output 'DatetimeIndex' is now the identifier for the roughly 2,200 entries betwee our requested dates. 
    
    IMAGE DELIVERABLE 7

    8.  After some quick research on the proper use of the resample function.  I was able to update our dataframe so that we could group the daily data into weekly data.  Which should prove significantly easier to understand when charted.
    
    IMAGE DELIVERABLE 8

    9.  Finally we create the chart using the object oriented method.  While a better method for our particular data set I find it more difficult to utilize, by comparison to the pyplot method.  We begin by importing the matplotlib style, so that we can use the provided 'fivethirtyeight' style for the chart design.  
    
    Using our latest data base as the major component of the ax.plot(x,y) function, allowing the fucntion to determine the x & y componenets automatically.  Then I provided the city types listed as labels to match the data being imported from our latest dataframe. 

    Finally, I created the y_axis label, the Title of the chart, added a legend, and included the plt.show() function to ensure the chart was being created.  Having made several attempts at generating the chart, I found that I could not replicate that of the chart in the modeule 5 outline. 

    IMAGE DELIVERABLE 9

# Summary of Analysis & Next Steps.

    Having throughly reviewed the results of our analysis.  I believe that we have several clear items that require additional contextual research to determine a significant action oriented result.  
    
    Specifically, I would like to dig deeper into the uniform up-tick in fare rates in late February.  A better understanding of that situation may allow us to more efficiently predict such outliers in the future.  

    Similarly, we should look into the asymetrical dip in fares within Suburban neighborhoods in the begining of April.  Again this could be due to several factors, but digging deeper into the context of these changes may allow for us to better predict negative indicators.

    My final recommendation would be to attempt to push our rural neighborhoods to see if we could improve fares or number of rides.  I imagine that would be best achieved by marketing & hiring effors.  Providing additional incentives to join the Pyber community, as either driver or passenger.