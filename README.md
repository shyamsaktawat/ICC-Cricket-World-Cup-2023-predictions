# ML RESTful API for ICC Cricket World Cup 2023 Predictions

## Team Members:

### Team Member 1 (202311067)
- **Contributions:** Responsible for data collection and initial preprocessing. Gathered comprehensive data on past cricket matches, team performance, player statistics, match conditions, and venue details.
### Team Member 2 (202311066)
- **Contributions:** Conducted exploratory data analysis (EDA) to identify patterns and insights in the cricket dataset. Utilized data visualizations to highlight key trends and prepare the data for machine learning.Worked on model tuning, result reporting, and the analysis of model performance. 
- 
### Team Member 3 (202311048)
- **Contributions:** Specialized in designing, developing, and deploying the ML RESTful API. 

### Team Member 4(202311033) & 5(202311040)
- **Contributions:** Involved in feature engineering, data transformation, and model evaluation. Collaborated with Team Member 2 to ensure seamless integration of ML models into the API.Led the implementation of Artificial Neural Networks (ANNs/DNNs) for prediction tasks related to the ICC Cricket World Cup 2023.

- # Cricket Wickets Prediction API

Predict the winner of cricket matches using this simple API.

## Introduction

This API provides a straightforward way to predict the winner of cricket matches based on given match details such as teams, venue, toss winner, and toss decision.

## Getting Started

## API Documentation
You can use the API to predict the winner of a match by sending a POST request to the following endpoint:

/predict_winner
## Request Format
Send a JSON payload with the following attributes:

{ "team1": "India", "team2": "Pakistan", "venue": "Eden Gardens", "toss_winner": "India", "toss_decision": "bat" }
## Example using cURL
curl -X POST -H "Content-Type: application/json" -d '{"team1": "India", "team2": "Pakistan", "venue": "Eden Gardens", "toss_winner": "India", "toss_decision": "bat"}' http://http://shyamsaktawat.pythonanywhere.com/predict_winner
The API will respond with the predicted winner and additional match details.

## Use Now

 " http://matchwinner.pythonanywhere.com/ "


Overview
This repository contains a Flask API for predicting the highest wicket-taker in a cricket match. The API utilizes machine learning models to provide insights into which player is likely to take the most wickets based on match details.

API Endpoints
Predict Highest Wicket-Taker
Endpoint: /predict_most_wickets
Method: POST
Input Format: JSON payload with match details (team1, team2, venue, toss_winner, toss_decision)
Output Format: JSON response with predictions for each team's highest wicket-taker
Example Usage
Here is an example Python script demonstrating how to make a POST request to the API:


   # URL for the Flask API
   

    api_url = 'http://localhost:5000/predict_most_wickets'
    input_data = {'team1': 'IND', 'team2': 'NZ'}
    response = requests.post(api_url, json=input_data)
    if response.status_code == 200:
    predictions = response.json()['predictions']
    # Print the results
    print(f"Predicted Highest Wicket-Taker for {input_data['team1']}:")
    print(f"Player: {predictions['team1']['Player']}")
    print(f"Predicted Wickets: {predictions['team1']['Predicted_Wickets']}")

    print(f"\nPredicted Highest Wicket-Taker for {input_data['team2']}:")
    print(f"Player: {predictions['team2']['Player']}")
    print(f"Predicted Wickets: {predictions['team2']['Predicted_Wickets']}")
    else:
    print(f"Error: {response.json()['error']}")


## use curl
    curl -X POST -H "Content-Type: application/json" -d '{"team1": "IND", "team2": "NZ"}' http://localhost:5000/predict_highest_wicket_taker

Getting Started
To set up and run the API:

Clone this repository to your local machine.
Install the required dependencies using pip install -r requirements.txt.
Run the Flask API using python app.py.
Make POST requests to the specified endpoint with the required input data.


## Summary of the Cricket Dataset:

### Overview
The dataset encompasses comprehensive information on past cricket matches, including team performance, player statistics, match conditions, and venue details. The dataset's richness allows for a detailed analysis and prediction of outcomes related to the ICC Cricket World Cup 2023.

### Data Collection
Team Member 1 collected data from various reliable sources, including sports channels, the ICC website, and leading data repositories like Kaggle. The dataset covers a substantial period, including recent matches, to ensure accurate predictions.
### Match Data:

#### Overview
The match dataset contains detailed information about individual cricket matches, including match date, teams playing, venue details, toss outcome, and match result.

#### Attributes:
- `season`: Season of the match.
- `team1`: Name of Team 1.
- `team2`: Name of Team 2.
- `date`: Date of the match.
- `match_number`: Unique identifier for each match.
- `venue`: Stadium or venue where the match took place.
- `city`: City where the match was held.
- `toss_winner`: Team that won the toss.
- `toss_decision`: Decision made by the toss winner (batting/fielding).
- `player_of_match`: Player of the match.
- `umpire1`: First umpire.
- `umpire2`: Second umpire.
- `reserve_umpire`: Reserve umpire.
- `match_referee`: Match referee.
- `winner`: Winning team.
- `winner_runs`: Margin of victory in runs (if applicable).
- `winner_wickets`: Number of wickets taken by the winning team (if applicable).
- `match_type`: Type of the match.

### Player Stats Data:

#### Overview
The player stats dataset provides individual player statistics for each match, including runs scored, wickets taken, strike rate, and more.

#### Attributes:
- `Match_ID`: Unique identifier linking to the match dataset.
- `Player_Name`: Name of the player.
- `Team`: Team to which the player belongs.
- `Runs_Scored`: Total runs scored by the player.
- `Wickets_Taken`: Total wickets taken by the player.
- `Strike_Rate`: Batting strike rate of the player.
- `Economy_Rate`: Bowling economy rate of the player.
- `Catches`: Number of catches taken by the player.

### Team Performance Data:

#### Overview
The team performance dataset aggregates team-level statistics for each match, including total runs scored, total wickets taken, and overall team performance.

#### Attributes:
- `Match_ID`: Unique identifier linking to the match dataset.
- `Team`: Team name.
- `Total_Runs_Scored`: Total runs scored by the team in the match.
- `Total_Wickets_Taken`: Total wickets taken by the team in the match.
- `Team_Performance`: Overall performance of the team in the match.

### Venue Details Data:

#### Overview
The venue details dataset provides information about each stadium or venue, including location, seating capacity, and historical match data.

#### Attributes:
- `Venue`: Name of the stadium or venue.
- `Location`: Location of the venue.
- `Seating_Capacity`: Maximum seating capacity of the venue.
- `Matches_Hosted`: Number of matches hosted at the venue.

### Tournament History Data:

#### Overview
The tournament history dataset contains historical data about the ICC Cricket World Cup, including previous winners, host countries, and tournament statistics.

#### Attributes:
- `Year`: Year of the ICC Cricket World Cup.
- `Host_Country`: Country hosting the tournament.
- `Winner`: Team that won the tournament.
- `Runner_Up`: Team that finished as the runner-up.
- `Top_Scorer`: Player with the most runs in the tournament.
- `Leading_Wicket_Taker`: Player with the most wickets in the tournament.

### Points Table Data:

#### Overview
The points table dataset provides information about the ranking, matches won, lost, tie, and other statistics for each team.

#### Attributes:
- `Ranking`: Current ranking of the team.
- `Team`: Team name.
- `Matches`: Total matches played.
- `Won`: Matches won.
- `Lost`: Matches lost.
- `Tie`: Matches tied.
- `No_Results`: Matches with no result.
- `Points`: Total points earned.
- `Net_Run_Rate`: Net run rate.
- `Series_Form`: Form of the team in the series.
- `Next_Match`: Details about the next match.
- `For`: Total runs scored.
- `Against`: Total runs conceded.

### Attribute Types
The dataset comprises a mix of attribute types, including categorical (team names, player names, venue details), numerical (runs scored, wickets taken), and temporal data (match dates, tournament history). This diversity provides opportunities for feature engineering and model development.

## Tasks for ML RESTful API:

### Task 1: Unleash Your Creativity
Choose two specific problem statements or prediction tasks related to the ICC Cricket World Cup 2023. Examples include predicting the top run-scorer, leading wicket-taker, or the number of sixes/boundaries for a player or team. Team Member 2's EDA insights can guide the selection of interesting prediction tasks.

### Task 2: Predicting the Finalist Teams and Players
Develop models to predict the two finalist teams in the ICC Cricket World Cup 2023 and the 11 players likely to be part of each team. This task involves team composition prediction and requires collaboration between Team Members 2, 4, and 5.

### Task 3: Predict the Winner of ICC Cricket World Cup 2023
Implement a model to predict the overall winner of the ICC Cricket World Cup 2023. This task involves combining insights from Task 2 and considering overall team performance. Team Member 3 and Team Members 4 and 5 can collaborate on this predictive task.

## ML RESTful API Development:

### Technologies Used:
- **Python Framework:** Flask
- **ML Library:** TensorFlow for ANN/DNN implementation
- **Data Processing:** Pandas, NumPy
- **API Deployment:** Docker for containerization

### API Development Steps:

1. **Data Preprocessing:**
   - Handle missing values.
   - Encode categorical variables.
   - Feature scaling and transformation.

2. **Model Building:**
   - Design and train ANN/DNN models for each prediction task.
   - Utilize insights from EDA for feature selection.

3. **Hyperparameter Tuning:**
   - Optimize model hyperparameters for better performance.

4. **API Development:**
   - we have Used Flask to develop a RESTful API.
   - Integrate trained models into the API for real-time predictions.

5. **API Deployment:**
   - Used Docker for containerization to ensure consistent deployment across different environments.

## Instructions to Get Started:

1. Clone this GitHub repository to your local machine.
2. Download the cricket dataset provided (or use your own) and place it in the project directory.
3. Install the necessary Python libraries and packages using the following command:

    ```bash
    pip install flask pandas numpy tensorflow docker
    ```

4. Open your preferred programming environment and start working on the API development.

## API Endpoints:

### 1. Task 1: Unleash Your Creativity
- **Endpoint:** `/predict_task_1`
- **Method:** POST
- **Input:** JSON payload with relevant features
- **Output:** Predicted outcome for the chosen prediction task

### 2. Task 2: Predicting the Finalist Teams and Players
- **Endpoint:** `/predict_finalist_teams_players`
- **Method:** POST
- **Input:** JSON payload with relevant features
- **Output:** Predicted finalist teams and players

### 3. Task 3: Predict the Winner of ICC Cricket World Cup 2023
- **Endpoint:** `/predict_winner`
- **Method:** POST
- **Input:** JSON payload with relevant features
- **Output:** Predicted winner of the ICC Cricket World Cup 2023

## License

This project is released under the [MIT License](LICENSE.md).

---
