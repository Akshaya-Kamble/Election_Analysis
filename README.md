# Election Analysis 

## Overview of Election Audit

In this Election audit we are helping Tom who is a Colorado Board of election employee. 
We have initially calculated the total number of votes cast, the total number of votes for each candidate, the percentage of votes for each candidate and the winner of the elections based on the popular vote.Also as per election comission's request we have calculated the voter turnout for each county,the percentage of votes from each county out of the total count, and the county with the highest turnout.We have automated the process of calculations and displayed the results using python. This code can also be use to audit data for other congrestional districts, senotorial districts and local elections.

## Election-Audit Results 

We have calculate the below election results by importing the data from the election_results csv file,making connections to the os by refering a path of the saved file,initilizing variables,lists and dictionaries as required for the calculations, using loops for iterating through the rows of data and collecting data with conditional statements,display data to the command line and store results in a txt file.
Attached image ![Final_Result](https://github.com/Akshaya-Kamble/Election_Analysis/Final_result_capture.PNG) for final result display.

### Breakdown of election audit with results.

	1. In this congressional election, the total number of votes cast were 369,711.
	   We were able to get this data by initializing a variable called total_votes to 0 and then incrementing this variable by 1 inside a for loop. With 	   the help of for loop we were able to calculate the total votes buy iterating through all the rows.


	2. We calculated the total number of votes and the percentage of total votes for each county and below are the results.
		- Jefferson: 10.5% (38,855)
		- Denver: 82.8% (306,055)
		- Arapahoe: 6.7% (24,801)
	   Using the below code inside for loop, we were able to populate the above results.

	   for county_name in county_votes :
	   	votes2 = county_votes.get(county_name)
		vote2_percentage = float(votes2) / float(total_votes) * 100
		county_results = (f"{county_name}: {vote2_percentage:.1f}% ({votes2:,})\n")
        	print (county_results)

	3. Looking at the statstics in the output on the command line we can see that Denver county had the largest number of votes (306,055) that is 82.8%.
	   We were able to get the resuls by using conditional statement if inside the for loop.By initializing three variables and using if condition 	   	   	   to assign the winners to the variables and printing out the winners assigned to respective variables.Below is the code.

	   	if (votes2 > winning_county_votes) and (vote2_percentage > winning_county_percentage):
           		winning_county_votes = votes2
           		winning_county = county_name
           		winning_county_percentage = vote2_percentage
	    
	   winning_county_summary = (f"\n"
           f"----------------------------------------\n" 
           f"The largest county Turnout is : {winning_county}\n"
           f"----------------------------------------\n" )
           print(winning_county_summary)


	4. We have calculated the total number of votes and the percentage of total votes for each candidate and below are the results.
		- Charles Casper Stockham: 23.0% (85,213)
		- Diana DeGette: 73.8% (272,892)
		- Raymon Anthony Doane: 3.1% (11,606)

	   Using the below code inside for loop, we were able to populate the above results.
	   for candidate_name in candidate_votes:
		votes = candidate_votes.get(candidate_name)
        	vote_percentage = float(votes) / float(total_votes) * 100
        	candidate_results = (f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
		print(candidate_results)

	5. The winner of the election is Diana DeGette with a winning Vote Count of 272,892 that is 73.8%.
	   Using similar logic for calculating winning county , we have calculated the election winner. Below is the code.

	   	if (votes > winning_count) and (vote_percentage > winning_percentage):
            		winning_count = votes
            		winning_candidate = candidate_name
            		winning_percentage = vote_percentage 

	   winning_candidate_summary = (
           f"----------------------------------------\n"
           f"Winner: {winning_candidate}\n"
           f"Winning Vote Count: {winning_count:,}\n"
           f"Winning Percentage: {winning_percentage:.1f}%\n"
           f"----------------------------------------\n")
           print(winning_candidate_summary)

## Election-Audit Summary

The script has been written with a lot of variabes and this makes its easy to work with any kind of data .With this code we can analyze any data' provided we have the same fields in the files.The csv file provied has three fields that are id,county and candidate name, with similar information we can calculate  results for any county or district.As we are writing the final results to a text file ,this data can also be modified within the print statments.We can resuse the code with very minimum changes and this could save time for calculating results every time.

### Examples of modifying the script
1. Changing the import depending on the type of file. 
Since the data can be available in any format, while importing the file the command will change depending on the file type we are importing.
In our code we have used import csv and this can be different depending on the file

2. Changing the path for operating system connections
Depending on the location of the file the path will change and this can be done by changing the code and joining the appropriate files to the os.
		



																					



