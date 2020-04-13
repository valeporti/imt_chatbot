## Asking for recommendation to spend time
* recommendation
  - utter_recommendation
* what_else
  - utter_chose_something_else

## Catch do Sport and ask for more
* rec_do_sport
  - utter_rec_do_sport
* thanks
  - utter_goodbye

## Catch watch videos and ask for more
* rec_watch_videos
  - utter_rec_watch_videos
* what_else
  - utter_chose_something_else

<<<<<<< HEAD
## query knowledgebase
> check_knowledgebase
=======
## Catch do Sport and leave
* rec_do_sport
  - utter_rec_do_sport
* what_else
  - utter_chose_something_else
>>>>>>> 60103a97045b5a14f47a1ce0ffa852429ca19ff9

## Catch watch videos and leave
* rec_watch_videos
  - utter_rec_watch_videos
* thanks
  - utter_goodbye

## Catch do Sport (recommandation)
* rec_do_sport
  - utter_rec_do_sport

## Catch watch videos (recommandation)
* rec_watch_videos
  - utter_rec_watch_videos

## query knowledgebase once
* greet
  - utter_greet
* query_knowledge_base
  - action_query_knowledge_base
* thanks
  - utter_goodbye

## query knowledgebase twice
* greet
  - utter_greet
* query_knowledge_base
  - action_query_knowledge_base
* query_knowledge_base
  - action_query_knowledge_base
* thanks
  - utter_goodbye

## Handle spontaneous KB query
* query_knowledge_base
  - action_query_knowledge_base

## Handle spontaneous unhappiness
* mood_unhappy
  - utter_cheer_up

<<<<<<< HEAD
## happy path             
* greet
  - utter_greet
* user_mood_great      
  - utter_happy
* goodbey
  - utter_goodbey


## sad path               
* greet
  - utter_greet            
* user_mood_unhappy
=======
## happy path
* greet
  - utter_greet
* mood_great
  - utter_happy

## sad path 1
* greet
  - utter_greet
* mood_unhappy
>>>>>>> 60103a97045b5a14f47a1ce0ffa852429ca19ff9
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
  - utter_recommendation
  - utter_goodbey

## say goodbye
* goodbye
  - utter_goodbye

## bot challenge
* bot_challenge
<<<<<<< HEAD
  - utter_iamabot
  - utter_greet
  - utter_how_do_you_feel
=======
  - utter_iamabot
>>>>>>> 60103a97045b5a14f47a1ce0ffa852429ca19ff9
