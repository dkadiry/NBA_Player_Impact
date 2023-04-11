# NBA_Player_Impact
## Content
The notebook in this repository contains the source code for a protocol that estimates the value of an NBA player to team success utilizing a Machine Learning Model designed to predict team wins.

## Design
###MLP based win predictor
We designed an MLP model that can accurately estimate how many games a team won in a particular season. The MLP model is trained utilizing NBA season data from 2000 to 2020/21 season excluding the 2017/18 season which was used for testing. The NBA team data consisted of a multitude of basic statistics which can be utilized directly or incorporated in various advanced statistics. These statistics act as inputs to the MLP to produce a predicted winning percentage. To save on computation and to prevent overfitting, only the statistics that were expected to produce the largest effect on winning were used to train the model. These were chosen to be offensive rating efficiency, defensive rating efficiency, points, true shooting percentage, a modified Player Efficiency Rating (PER), and Pythagorean win expectation [M7]. Our approach had an R2 score of 0.92 and an average accuracy using percent error of 91.7% 

For more details on the calculations of these statistics see the methodology section for the MLP in the final report [here](https://drive.google.com/file/d/16zH5h6bKNjRPzWOPVHJMTCran3_z5iSx/view?usp=share_link)

###New Player Impact Score
We create a team comprising of 15 average players using player statistics for the 2017-18 season. Our model predicts this team will win 42 games as expected. We then replace one of the average players with a player to be evaluated to see how many wins our player contributes to the average team. The extra wins contributed become our player impact score. We use this player impact score to estimate a new salary for this player based on the player's contribution to team success. For more details on the design and evaluation metrics of the Player Impact Score see the results & evaluation section of the final report.


## Pitfalls of our approach
During evaluation we found that this model does not accurately account for a player's defensive impact as those statistics are difficult to quantify. Our future works proposes designing a similar model trained on NBA play-by-play data.

