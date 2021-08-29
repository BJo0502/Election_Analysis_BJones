# Module 3: PyPoll Challenge

## Overview of the Project:

Our task is to help Seth and Tom submit election audit results to the election commission. Initially, we were asked to submit the results for the candidates; however, the election commission has asked for us to add some additional information regarding the county results to our final deliverable. Using python, our task is to parse through a large .csv of election results and output the following details

1.)	Voter turnout for each county

2.)	The percentage of votes from each county compared to the total votes cast

3.)	Identify the county with the largest turnout

4.)	Total votes each candidate received

5.)	The percentage of votes cast for each candidate

6.)	Identify the winning candidate

## Election-Audit Results:
Below are the following code blocks that we used to solve for the specific output details.

### Setting up the script
![Slide1](https://user-images.githubusercontent.com/88041368/131259182-e6add327-3271-42b0-8d44-cb72f494b268.PNG)

### How many votes were cast in this congressional election?
![Slide2](https://user-images.githubusercontent.com/88041368/131259629-2952c058-7a9b-40aa-b80e-7c8ca3393428.PNG)
![Slide3](https://user-images.githubusercontent.com/88041368/131259633-7f8133a5-198f-4d46-9ab7-240449a4806c.PNG)

### Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.
![Presentation2](https://user-images.githubusercontent.com/88041368/131259741-61a2922d-bca1-4467-80e7-ec49b06c77fd.png)

## Which county had the largest number of votes?
![Presentation3](https://user-images.githubusercontent.com/88041368/131260060-a4b81699-efe3-4306-b337-a80952e356a2.png)

## Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.
This bit of code we have already solved for so we are able to reuse it without modifcation:

      for candidate_name in candidate_votes:
        #Retrieve vote count and percentage
          votes = candidate_votes.get(candidate_name)
          vote_percentage = float(votes) / float(total_votes) * 100
          candidate_results = (
              f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
              
## Which candidate won the election, what was their vote count, and what was their percentage of the total votes?
This bit of code we have already solved for so we are able to reuse it without modifcation:

    #Determine winning vote count, winning percentage, and candidate.
          if (votes > winning_count) and (vote_percentage > winning_percentage):
              winning_count = votes
              winning_candidate = candidate_name
              winning_percentage = vote_percentage

      #Print the winning candidate (to terminal)
     winning_candidate_summary = (
          f"-------------------------\n"
          f"Winner: {winning_candidate}\n"
          f"Winning Vote Count: {winning_count:,}\n"
          f"Winning Percentage: {winning_percentage:.1f}%\n"
          f"-------------------------\n")
     print(winning_candidate_summary)

## Election-Audit Summary:

Most of the python code that we have written can be borrowed and applied to other election results. By using variables for both script inputs and outputs vice hard coding, we ensure that our code is dynamic. We also used F-strings to format our output results, which further ensures that out output text file will look consistently the same. Despite our efforts there are still some steps we must make prior to applying our python code to other election results. We need to make sure that our file_to_load and file_to_save paths are modified based on where the raw results are stored and need to be saved on our computer. We also must make sure any new election results csv’s are formatted the same as the sample we used to write our code. For example, if there are additional columns of data in the csv or if they are ordered differently, we will need to adjust our row index in the script to reflect this. The script is currently written for examining election results at the county level; however, if there was ever a need compile all county results in each state, additional script would need to be added to our code. Steps to merge multiple csv’s of county election results would need to be written, followed by script that solved for the state totals, similarly to how we solved for the total county results.

