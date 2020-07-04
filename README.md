# covid19_bubble_map
Bubble map made with covid 19 data

To see the output in kaggle go to https://www.kaggle.com/vbprojects/covid-visualization/data

This was made with 2 datasets.

https://www.kaggle.com/fireballbyedimyrnmom/us-counties-covid-19-dataset - covid dataset

https://data.healthcare.gov/dataset/Geocodes-USA-with-Counties/52wv-g36k - geocode dataset

note that the geocode dataset was made in 2013



The first steps to replicating the bubble map was to tidy up both datasets. For the covid dataset I did the following

removed all rows with unkown county field

changed all state names to their abreviations

turned all county names to lowercase



For the geocode data I

Turned the csv into a json structured as {State: {County:{lattitude,longitude}}}

made all counties lowercase

removed substring parish from counties in LA

added New York City to the dataset


After that I mapped all the State and county fields from the covid data set to the dictionary made from the geocode dataset and generated a list 
of lattitudes and longitudes for each data point. Whenever the county could not be found in the dictionary, that point was removed from the frame.
I then used plotly to graph the data.

If I could do this project differently I would use more recent geocode data as almost 1000 data points were excluded because they did not show up in the geocode dictionary.

