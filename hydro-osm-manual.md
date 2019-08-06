#!/bin/bash

# this model has been developed to check the missing data on collected information
#the model produce the file called flag which provide the information that are collected and not
#it is the simple way  of analysing the collected information of large amount within few minutes
#it run in both linux machine and window in window it use .bat and in linux use .ini and .sh files

#first you need to have git on your computer by using sudo apt-get install git



#Clone hydro-osm form 

 -git clone https://github.com/openearth/hydro-osm

#install Fiona

-sudo apt update
-sudo apt-get install fiona

#install gdal, prefferable version 2.0.1 and above

 -sudo apt-get install gdal

#gdal version

 -gdalinfo --version

#Install rtreee

 -sudo apt-get install python-rtree

#Install Pandas

 -sudo apt-get install python3-pandas

#Install r-cran-optparse

 -sudo apt-get install r-cran-optparse

#open the file on the downloaded data from git and name it in your own way( data that are to be analysed). This file is where you should be using store your data
 
#another important thing to note is that you have to really understand your directories to where you will perform the work
 
#there are four file that you should configure them with the same naming and spelling format(within the folder that your working on)
 
1. #data folder(this one contain the shapefile that you want to check them)

2. #.in file eg.check_connectivity_general.ini (this one has the information that will set the format and specification.there naming should be the same as the shapefile used) 

3. #.sh file eg check_connectivity_general.sh ( this file contain scripts that run model and redirect the output file to the folder your working on it's in this format eg 


 
 
python ../../run_osm_dq.py -i check_connectivity_general.ini -c data_model -d . -p general_conn_20180220
 



4. #the ODK form that was used to collect data that your analysing
 
#after setting up with all this you need to run by following the directories to where you save the folder which contain all four files and the run by using ./check_connectivity_general.sh 

# after running the model will give you three new files 
 
Report file which contain excel format report of the result
Gis file report and which contain geojson file of which you will add to qis and check which segment mis data on flag file 1 ,2,3,4 where number 3 are the one that should be collected but not collected so you should work on these
The other file is osm validation ( this one has the osm validation information for each segment you can check the way model analyse each segment)




