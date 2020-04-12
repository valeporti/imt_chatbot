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

# Subjects handled by our chatbot

### Could show supermarkets, hospitals, medics, pharmacies 
*Just in Plouzané, Finistère, France*
+ An improvement for this fefature could be to implement an API that would let the user insert his country and postal code for exemple, and get the same answer as it do now but available worldwide.
+ This is a [knowledgebase solution](https://rasa.com/docs/rasa/1.7.4/core/knowledge-bases/) meaning that there should be a terminal running the actions and the when an intent is detected to be part of the knowledgebase, the query will be made. 
+ **Available information**
  + Get the list of (supermarkets/hospitals/medics/pharmacies)
  + Get some info about one of the listed items (most of them have: name/postal_code/address/link, others: express/home_delivery
    + For 