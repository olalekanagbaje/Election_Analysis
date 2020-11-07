# Election_Analysis
## Overview of Election Audit:
The purpose of the election audit analysis is to generate and provide the following vital information (relating to a local congressional election) to the Colorado Board of Elections;

1. Total number of votes cast
2. A complete list of candidates that received votes
3. Total number of votes each candidate received
4. Percentage of votes each candidate won
5. The winner of the election based on popular vote
6. The voter turnout for each county
7. The percentage of votes from each county out of the total count
8. The county with the highest turnout

To generate these information for the Colorado Board of Elections, I utilized the following resources;

 - Data Source: election_results.csv
 - Softwares: Python 3.7.6 , Visual Studio Code 1.5.1


 ## Election-Audit Results:

 The following are the key outcomes / results from the analysis of the election_results.csv raw data file for the local congressional election in Colorado;

  - __Votes Cast in the Congressional Election:__ The total votes cast in the election was 369,711. The code block extract highlighted below was used to generate the total votes cast.
  
    _election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")_

    _txt_file.write(election_results)_  

  - __Breakdown of the Number of Votes and Percentage of Total Votes Per County:__ The preview highlighted below provides a breakdown of this data per county 

          County Votes:
          Jefferson: 10.5% (38,855)

          Denver: 82.8% (306,055)

          Arapahoe: 6.7% (24,801) 


  - __County with the Largest Number of Votes:__ The county with the largest number of votes in the election was Denver with a total of 306,055 votes (representing 82.8% of total county votes). The code block extract highlighted below was used to generate this data.

      _county_votenumbers = county_votes.get(county_name)_

  - __Breakdown of the Number of Votes and Percentage of Total Votes Per Candidate:__ The preview highlighted below provides a breakdown of this data per candidate

        Charles Casper Stockham: 23.0% (85,213)

        Diana DeGette: 73.8% (272,892)

        Raymon Anthony Doane: 3.1% (11,606)        


  - __Winning Candidate, Their Vote Count & Percentage Total Vote:__ The preview highlighted below provides a breakdown of this data

        Winner: Diana DeGette
        Winning Vote Count: 272,892
        Winning Percentage: 73.8%  


 ## Election-Audit Summary:
 In summary, I developed and used a python-based script to extract relevant outcomes from the raw data file (elections_results.csv file) of a local congressional election for the Colorado Board of Elections. This script was utilized to generate relevant audit information for the board such as the total votes in the election, winning candidate, winning candidate votes & percentage votes count, largest vote count & percentage vote count per county amongst others. 
 
 Furthermore, it is important to highlight to the Colorado Board of Elections that this python script can be easily modified and repurposed to analyze and provide relevant audit data for any election. To achieve this, we will need to make a few modifications to different sections of the script that receive and process unique "input information / data" about each election(s) we intend to analyze. Two examples of such areas of the script that can be modified are highlighted below;

  - A slight modifcation must be made to the line of code that references the folder location / path and the file name of the new election data(.csv file) that the board may wish to analyze. The actual line of code to be modified is shown below. The 2 input data in parenthses, in the line of code below will have to be adjusted accordingly for the script to work correctly for the new election data .csv file
  
    _file_to_load = os.path.join("Resources", "election_results.csv")_


 - If the .csv file that warehouses the fresh election data does not have thesame name format / positions for headers when compared to the .csv file used in generating this script, then slight modifcations should be made as appropriate to the index numbers referenced in the "For Loop" line of code extract below. The correct index number for "candidate name" and "county name" respectively must be inputed for "row" in the line of code highlighted below.  

        # for each row in the CSV file.
        for row in reader:

            # Add to the total vote count
                 total_votes = total_votes + 1

            # Get the candidate name from each row.
                 candidate_name = row[2]

            # 3: Extract county name from each row.
                 county_name = row[1]   