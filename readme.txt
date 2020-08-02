Documentation of most of the used functions:

Function: get_filters()
    Checking, whether the string input matches one of the dictionaries values by index.
    source for .key() function: https://www.geeksforgeeks.org/python-pandas-dataframe-keys/

    The values of the original dictionaries need to be stored in a list.
    After this we can go through each entry (0 - 2) and check for comparison.

    Because we are dealing with user input, we need to catch the exceptions.
    source for exception handling: https://wiki.python.org/moin/HandlingExceptions

    All other functions within get_filters function are ones with lower complexity.


Function: load_data():
    Loading the data with previous set filters into a variable, 
    like done in the practice part of the course.

    Converting 'Start Time' column into datetime, month, weekday and hour.
    Creating a column for the start-, stop-station combination.

    Applying the month and day filter to the dataframe, like in the practice part.

Function time_stats():
    The month and days variables also could be global variables, other than a second time used local variables.
    Anyway, created here a second time.

    The calculations for the most commons use the mode() function.
    source for mode(): https://docs.python.org/3.4/library/statistics.html#statistics.mode

    To get it to run as expected, I took a look at the practice part of the course again.
    This helped me to specify the index returned [0] and refine the month returned from the list months (- 1).

    Same for the rest.

Function station_stats():
    Using the mode() function worked just as great.
    But during tests, I found that many journeys start and end at the same station.
    This was a little harder to read, so I give back an explanation.

Function seconds_to_readable_data():
    The functions takes the seconds and returns it in ... a more readable form.
    source for seconds_to_readable_data(): https://stackoverflow.com/questions/4048651/python-function-to-convert-seconds-into-minutes-hours-and-days

Function trip_duration_state():
    Easy sum and mean calculations.

Function user_stats():
    We count the values of the column and use the value_count() functions that returns a series...
    source: https://www.w3resource.com/pandas/series/series-value_counts.php

    This series is converted to a dictionary by the to_dict() functions.
    Last it prints out the key, and value pair.
    source for key, value print: https://www.geeksforgeeks.org/python-accessing-key-value-in-dictionary/

    Some Datasets does not contain data for one of the desired values, with would throw an error.
    So instead we check before we use it.

    To return a sample, i use the sample funtion.
    source for sample: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sample.html
