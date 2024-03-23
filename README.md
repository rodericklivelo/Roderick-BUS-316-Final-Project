# Roderick-BUS-316-Final-Project

The National Basketball Association is a professional basketball league based in North America. After every season, the league gives individual awards to their athletes for their outstanding efforts and achievements. 
The award that holds the highest regard is the Most Valuable Player award. This award is given to the player with the greatest individual performance throughout the entire season. 
This award is very important to business practices because this recognition positively affects a player’s name brand, gives leverage for the player’s next contract, as well as rewards the players with incentive payments if stated in their contract. 
What makes an MVP? This topic has been very controversial as of late as many question what makes a player the “most valuable”. Is it really just the individual stats that count? Does the team’s performance without the player matter? Should wins be accounted for? Many of these kinds of questions are asked when thinking about who should win MVP.
There is no “algorithm” which automatically selects the MVP once the season finishes. The MVP is voted on by a panel of 100 voters. 
For my final project I would like to create a regression model which predicts the share of MVP votes a player will receive. I would like to create a model with an accuracy score as high as I can get it. In order to do this, I would have to go through a process of trial and error with the X variables for the regression. Essentially, through finding a model with the highest accuracy score, I would be attempting to answer the question discussed before “What makes an MVP?”

The Process:

To start off, I need to gather the dataset. Using nba_api, I am able to get data frames on all player statistics. For this project, I decided to use just the past five seasons, reasoning being that since the standards and quality of play in the NBA change drastically very quickly through the years, I would like to use only recent seasons to ensure accuracy. Now I have ____ rows of every player’s stats from each of the past five seasons, excluding the current one.

Secondly, I must join this dataframes with two others, separately.

For regression, I will join dataframes to the data which will include the MVP voting share players had received for the respective season. For example, in the 2021-22 season, Nikola Jokic received 875 points out of the 1000 points that could be won through voting, which means that his MVP_Share is 0.875. The data frames will display the player name, season, their stats, and mvp share.

For classification, instead of using the voting share, I will join dataframes that indicate whether or not the player had won MVP that season. For example, Joel Embiid won MVP in the 2022-23 season, which means that his row for his 2022-23 statistics will include a value of 1 for the column “MVP”. Those who did not win MVP in their respective season will receive a 0.

I had also created a query that includes only players who averaged over 20 minutes and 20 points per game.

Now that these data frames are joined, the two of them are now ready to be used for a regression and classification model. 

Trial 1:
	
For this one, the Xs that I will use will be Points, Rebounds, and Assists. I will use this as the baseline since these three stats are the biggest three ones that are usually looked at when it comes to basketball.

Accuracy Score:

Trial 2: 

For the next one I will include more X values, including steals, blocks, fg%, min, turnovers, in order to see if it helps with the Accuracy Score:

Accuracy Score:

Trial 3: 

We know that MVP is an individual award, but NBA analysts believe that the amount of wins in their team contributes a lot to 
