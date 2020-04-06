
## query knowledgebase 
* Greet   # intention
  - utter_greet # actions
* Query_Knowledgebase
  -  utter_Get_Supermarket
  -  utter_Get_Hospital
  -  utter_Get_Trips
  -  utter_Get_pharmacies
 * Grateful_words
  - utter_thanks
  - utter_other_questions
> check_knowledgebase

## asking for recommendation to spend time
* Kill_Time_Intent{"is_helpful": "YES"}  # how to set a slot
  - utter_ recommendation
  - utter_did_that_help 
> check_recommendation

## query knowledgebase and 
> check_knowledgebase

* More_question
  - utter_waiting_for_question
* User_Sentiments_bad_Intent OR User_Sentiments_great_Intent
  - utter_cheer_up
* Kill_Time_Intent{"is_helpful": "YES"}  # how to set a slot
  - utter_ recommendation
  - utter_did_that_help
** affirm
  - utter_happy
  - utter_goodbey

## Handle spontaneous unhappiness
* mood_unhappy
  - utter_mood_unhappy

## happy path               <!-- name of the story - just for debugging -->
* greet
  - utter_greet
* User_Sentiments_great_Intent               <!-- user utterance, in the following format: * intent{"entity_name": value} -->
  - utter_happy
* Goodbey
  - utter_goodbey


## sad path 1               <!-- this is already the start of the next story -->
* greet
  - utter_greet             <!-- action of the bot to execute -->
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* affirm
  - utter_happy

## sad path 2
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* deny
  - utter_goodbye

## say goodbye
* goodbye
  - utter_goodbye

## bot challenge
* bot_challenge
  - utter_iamabot
