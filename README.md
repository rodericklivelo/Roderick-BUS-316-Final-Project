# Roderick-BUS-316-Final-Project

The National Basketball Association is a professional basketball league based in North America. After every season, the league gives individual awards to their athletes for their outstanding efforts and achievements. 
The award that holds the highest regard is the Most Valuable Player award. This award is given to the player with the greatest individual performance throughout the entire season. 
This award is very important to business practices because this recognition positively affects a player’s name brand, gives leverage for the player’s next contract, as well as rewards the players with incentive payments if stated in their contract. 
What makes an MVP? This topic has been very controversial as of late as many question what makes a player the “most valuable”. Is it really just the individual stats that count? Does the team’s performance without the player matter? Should wins be accounted for? Many of these kinds of questions are asked when thinking about who should win MVP.
There is no “algorithm” which automatically selects the MVP once the season finishes. The MVP is voted on by a panel of 100 voters. 
For my final project I would like to create a regression model which predicts the MVP of a season. I would like to create a model with an accuracy score or RMSE as high as I can get it. In order to do this, I would have to go through a process of trial and error with the X variables for the regression. Essentially, through finding a model with the highest accuracy score, I would be attempting to answer the question discussed before “What makes an MVP?”

The Process:

To start off, I need to gather the dataset. Using nba_api, I am able to get data frames on all player statistics. For this project, I decided to use just the past five seasons, reasoning being that since the standards and quality of play in the NBA change drastically very quickly through the years, I would like to use only recent seasons to ensure accuracy. Now I have 2742 rows of every player’s stats from each of the past five seasons, excluding the current one.

Secondly, I must join these dataframes with two others, separately.

For regression, I will join dataframes to the data which will include the MVP voting share players had received for the respective season. For example, in the 2021-22 season, Nikola Jokic received 875 points out of the 1000 points that could be won through voting, which means that his MVP_Share is 0.875. The data frames will display the player name, season, their stats, and mvp share.

For classification, instead of using the voting share, I will join dataframes that indicate whether or not the player had won MVP that season. For example, Joel Embiid won MVP in the 2022-23 season, which means that his row for his 2022-23 statistics will include a value of 1 for the column “MVP”. Those who did not win MVP in their respective season will receive a 0.

I had also created a query that included only players who averaged over 20 minutes and 20 points per game, since this is a standard baseline for what MVP’s should be averaging.

Now that these data frames are joined, the two of them are now ready to be used for a regression and classification model. 

Trial 1:
	
For this one, the Xs that I will use will be Points, Rebounds, and Assists. I will use this as the baseline since these three stats are the most looked at stats when it comes to basketball.

RMSE: 0.154
Accuracy Score: 0.980 (Recall for MVP: 50%)

Trial 2: 

For the next one I will add and include more X values, including steals, blocks, fg%, min, and turnovers, in order to see if a more variety of data helps with the models:

RMSE: 0.148 (-0.006 improvement)
Accuracy Score:  0.980 (Recall for MVP: 50%)

Trial 3: 

We know that MVP is an individual award, but many argue whether or not team wins/success contribute towards one’s MVP chances. For this trial, we will include WIN_PCT for the X to see if it affects the models.

RMSE: 0.144 (-0.004 improvement)
Accuracy Score:  0.980 (Recall for MVP: 50%)

Trial 4: 

For this trial, I will try a completely different approach. What I have noticed with the other trials is that it does not take into account that comparison between players matters. One player in a season could have MVP worthy stats in one year but does not win MVP because another player had better stats. This time, instead of using the stat counts for the X’s, I will use the rank in which the player had gotten with those stats compared to the other players. (Ex: PTS_RANK: 1)

RMSE: 0.162 (+0.18 worse)
Accuracy Score: 0.960 (Recall for MVP 0%)

Trial 5:

In this trial, I will combine both Xs used in both trial 3 and 4.

RMSE: 0.134 (-0.010 improvement compared to trial 3, -0.028 improvement compared to trial 4)
Accuracy Score: 0.960 (Recall for MVP 0%)



Conclusions:

Adding more stat categories decreases the RMSE.
Ranks alone are not as effective as raw stats but help when added.
Win pct (not an individual stat) decreases the RMSE.
Classification is not too useful with very little MVP data, considering I am using only the past five NBA seasons. Recall score for MVP never reached 100%
If I were to run a linear regression model to predict a future MVP, I would use trial 5.
