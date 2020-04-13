## happy path
* greet OR nicetomeetyou
  - utter_greet
  - utter_nicetomeetyou
* mood_great
  - utter_happy
> checkpoint_greet
## sad path 
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* affirm OR deny
  - utter_happy
  - utter_cheer_up
> checkpoint_sad


## Asking for recommendation to spend time video
* recommendation{"domain": "video"}
  - utter_rec_watch_videos
* what_else OR thanks
  - utter_chose_something_else
  - utter_goodbye
> checkpoint_recommendation_video


## Asking for recommendation to spend time sport
* recommendation{"domain": "sport"}
  - utter_rec_do_sport
* what_else OR thanks
  - utter_chose_something_else
  - utter_goodbye
> checkpoint_recommendation_sport

## Asking for recommendation to spend time music
* recommendation{"domain": "music"}
  - utter_rec_do_music
* what_else OR thanks
  - utter_chose_something_else
  - utter_goodbye
> checkpoint_recommendation_music  
 
 
## Asking for recommendation to spend time recipe
* recommendation{"domain": "recipe"}
  - utter_rec_do_recipe
* what_else OR thanks
  - utter_chose_something_else
  - utter_goodbye
> checkpoint_recommendation_recipe 


## Handle spontaneous unhappiness
* mood_unhappy
  - utter_cheer_up
  
## feel sad and ask for recommendation sport
> checkpoint_sad
> checkpoint_recommendation_sport
  
## feel sad and ask for recommendation video
> checkpoint_sad
> checkpoint_recommendation_video

## feel sad and ask for recommendation music
> checkpoint_sad
> checkpoint_recommendation_music

## feel sad and ask for recommendation recipe
> checkpoint_sad
> checkpoint_recommendation_recipe

## greet and ask for recommendation sport
> checkpoint_greet
> checkpoint_recommendation_sport

## greet and ask for recommendation video
> checkpoint_greet
> checkpoint_recommendation_video

## greet and ask for recommendation music
> checkpoint_greet
> checkpoint_recommendation_music

## greet and ask for recommendation recipe
> checkpoint_greet
> checkpoint_recommendation_recipe



## Handle spontaneous KB query
* query_knowledge_base
  - action_query_knowledge_base
  
## query knowledgebase once
> checkpoint_greet
* query_knowledge_base
  - action_query_knowledge_base
* thanks
  - utter_goodbye

## query knowledgebase twice
> checkpoint_greet
* query_knowledge_base
  - action_query_knowledge_base
* query_knowledge_base
  - action_query_knowledge_base
* thanks
  - utter_goodbye

## say goodbye
* goodbye
  - utter_goodbye

## bot challenge
* bot_challenge
  - utter_iamabot
  

## Asking for a joke
* telljoke
  = utter_telljoke

## Greet, Asking for a joke
> checkpoint_greet
* telljoke
  = utter_telljoke
* what_else OR thanks
  - utter_chose_something_else
  - utter_goodbye