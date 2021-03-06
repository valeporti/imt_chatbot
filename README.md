# UE TAL 2020 Chatbot

# About

This chatbot was created as the final project for the UE TAL (Traitement de la Langue et Fouille de Texte) cours at the [IMT Atlantique](https://www.imt-atlantique.fr/). The chatbot was implemented by using [rasa](https://rasa.com/) and created having in mind the coronavirus pandemic. So, some queries regarding subjects having to do with the coronavirus context, are possible.

# Getting Started

> To run, python 3.6+ should be intsalled

> Also, [rasa V1.7.4](https://rasa.com/docs/rasa/1.7.4/)

* *Recommended: to install in a new environnment (huge changes may be made, a lot of dependencies: tensorflow, sklearn, pandas, spacy, numpy, keras, nltk, ...)*

```
pip(3) install rasa==1.7.4
```

> Download the project
```
git clone https://github.com/valeporti/imt_chatbot.git
```
> *next instruction is to train the chatbot, but, if needed, the already trained model could be downloaded*
1. *download from [drive](https://drive.google.com/file/d/1yrBBqyFYrUyHH0sqRKkI9O5RVoyQ0sCg/view?usp=sharing)*
2. put inside model's folder *imt_chatbot/models/*

> Train the chatbot
```
cd imt_chatbot
rasa train
```
> Prepare the "playground"
* In a one terminal (always inside the imt_chatbot folder), run:
```
rasa run actions
```
*this part should be running in order to use the actions connection that, in this case, will give you access to a "database"*
* in another terminal (always inside the imt_chatbot folder), run:
```
rasa shell
```
> Use it! :)

*for exemple*:
```
Your input ->  do you know any supermarkets?                                                                                                                                                    
Found the following objects of type 'supermarkets':
1: Lidl Plouzané
2: Lidl Brest
3: U Express
4: Carrefour Plouzané
5: Carrefour Express
Your input ->  recommend me something to do                                                                                                                                                     
you could read a book :): https://outilstice.com/2020/03/la-liste-complete-des-livres-a-telecharger-gratuitement-pendant-la-periode-de-confinement/#gs.36qv1e
```

> Rasa x

* This makes easier the process of visualization, training and correction of the behavior of the bot. 

To install it alongside rasa preconfigured for spacy:
```
pip install rasa-x --extra-index-url https://pypi.rasa.com/simple
pip install rasa[spacy]
python3 -m spacy download em_core_web_md
python3 -m spacy link en_core_web_md en
```

To run it:
```
rasa x
```

# Subjects handled by our chatbot

### Options handled by this chatbot

```
Your input ->  What can you do?                                                 
You can ask me about:
- How I was built.
- How old I am.
- What time is it.
- The weather. 
- We can disscuss about how do you feel.
- I can give you some recommendations for activities to do. 
- I have information about supermarkets, pharmacies, medics and hospitals in the zone.
- I know some jokes too XD.
Your input ->  Great                                                            
I know, rigth?
Your input ->   
```

### Could show supermarkets, hospitals, medics, pharmacies 
*Just in Plouzané, Finistère, France*
+ An improvement for this fefature could be to implement an API that would let the user insert his country and postal code for exemple, and get the same answer as it do now but available worldwide.
+ This is a [knowledgebase solution](https://rasa.com/docs/rasa/1.7.4/core/knowledge-bases/) meaning that there should be a terminal running the actions and the when an intent is detected to be part of the knowledgebase, the query will be made. 
+ **Available information**
  + Get the list of (supermarkets/hospitals/medics/pharmacies)
  + Get some info about one of the listed items (most of them have: name/postal_code/address/link, others: express/home_delivery
    + For exemple:  
```
Your input ->  are there any supermarkets in Plouzané?     
Found the following objects of type 'supermarkets':
1: Lidl Plouzané
2: Carrefour Plouzané
Your input ->  which is the link for the first one?          
'Lidl Plouzané' has the value 'https://www.lidl.fr/fr/' for attribute 'link'.
Your input ->  which is its address?
'Lidl Plouzané' has the value 'Route de Tremaidic' for attribute 'address'.
Your input ->  which are the hospitals located in Plouzané
I could not find any objects of type 'hospitals'.
Your input ->  which are the hospitals in Brest 
Found the following objects of type 'hospitals':
1: CHRU Morvan
2: CHRU Cavale Blanche
can you give me the phone of the second one?
'CHRU Morvan' has the value '02 98 22 33 33' for attribute 'phone'.
```
