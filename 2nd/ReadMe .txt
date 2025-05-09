Step 1 . Use these 4 files

	access_log_short.txt
	SalesCountryDriver.java
	SalesCountryReducer.java
	SalesMapper.java
	
	
Step 2 :convert access_log_short.txt to csv file   //done
	
	
Step 3 :Go to Eclipse 
	  create Java Project 
	   Add Package with name "SalesCountry"
	   in this package create new 3 java files with name 	 	SalesMapper,SalesCountryDriver,SalesCountryReducer (copy or write code)
	   
	   Add 3 jars files through buildpath-->configure Build Path-->Libraries-->add external Jar file	 
	   	1. hadoop/mapreduce/hadoop-mapreduce-client-core-2.7.5.jar 
			/usr/local/hadoop/hadoop-2.7.0/share/hadoop/mapreduce      	 
	   	2. hadoop/mapreduce/hadoop-mapreduce-client-common-2.7.5.jar
	   	3. hadoop/common/hadoop-common-2.7.5.jar     /usr/local/hadoop/hadoop-2.7.0/share/hadoop
	  
Step 4: Creation of Jar file with Eclipse 	   	
	Export-->Java-->Jar files-->assign Name to jar files-->browse and select path of jar file

	
# create input2000 folder in home and paste the csv file in it.

# START HADOOP by start-all.sh 
#or start hadoop by 1. start-dfs.sh
	            2. start-yarn.sh

# Copying input to HDFS file System by following command:

	hdfs dfs -put ~/input2000 /
	
# Then to perform Map and Reduce: create output2000 folder in home
#copy jar1.jar file in home 
	
	hadoop jar analyzelogs.jar /input2000 /output2000   #instead analyzelogs.jar use jar1.jar
	
# See the Output by following command:

	hdfs dfs -cat /output2000/part-00000
