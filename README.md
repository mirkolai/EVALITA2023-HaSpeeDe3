# [HaSpeeDe3@Evalita 2023](http://di.unito.it/haspeede3)

The HaSpeeDe 3 (Hate Speech Detection) shared task will be organised within Evalita 2023, the 8th evaluation campaign of Natural Language Processing and Speech tools for Italian, which will be held in Parma on the 7th-8th September 2023.

This shared task has reached the third edition, with a share, always increasing, of a highly diverse audience that, in many cases, participated in both the two previous editions organised within [Evalita 2018](https://www.evalita.it/campaigns/evalita-2018/) and [Evalita 2020](https://www.evalita.it/campaigns/evalita-2020/).

The new edition differs from the previous one while maintaining the continuity in analysing and contrasting HS on social media. HaSpeeDe (Bosco et al., 2018) and HaSpeeDe 2 (Sanguinetti et al., 2020) focused on HS against immigrants, Muslims and Roms; whereas HaSpeeDe 3 explores hate speech in strong polarised debates, in particular concerning political and religious topics. Attention on strong polarised debates leads the task to explore contextual information about the authors of the tweets by means of their social media network, since political and religious self-identification may lead to hard conflict with the members of other political affiliations or worships.

#
# Introduction

The focus of this task is the detection of **hate speech** in strong polarised debates, in particular concerning political and religious topics. 

We then created two different datasets called **PolicyCorpusXL** and **ReligiousHate**. 

- **PolicyCorpusXL**:

7,000 tweets about political debates (5,600 training, 1,400 test)

- **ReligiousHate:** 

3,000 tweets about the three main monotheistic religions, namely Christianity, Islam and Judaism (only test)

We collected tweets using the Twitter’s API for Academic Research by querying for

key terms specific to each topic.

PolicyCorpusXL (Celli et al., 2022) contains 7,000 tweets collected employing a snowball sampling from three starting hashtags (#dpcm, #legge, #leggedibilancio). 

ReligiousHate corpus (Ramponi et al., 2022)  is composed of 3,000 tweets collected between December, 2020 and August, 2021 with keywords that refer to the three main monotheistic religions, namely Christianity, Islam and Judaism. Due to the different nature of the two topics, the collection methods are not the same, but in both cases we looked for query terms that did not include offensive words
# Task Description

With this task proposal, we invite participants to explore features based on the textual content of the tweet, but also features based on contextual information (such as metadata that describe both the tweet and her/his author or information about the social media community of the participants of the debate).

Furthermore, we proposed two different setups: an in-domain and a cross-domain one. Both tasks aim to solve a binary classification problem and the systems have to predict whether a tweet contains hatred or not.

This proposal focuses on Hate Speech in Twitter proposing two tracks and 2 sub-task for each track:

- **Task A** - **Political Hate Speech Detection**: a binary classification task aimed at determining whether the message contains Hate Speech or not
  - **Textual**: participants can only use the provided textual content of the tweets from PolicyCorpusXL for development.
  - **Contextual**: participants can employ for development the textual content of the tweets plus contextual information that will be given to them (i.e., metadata of the tweet and author, friends, retweets, and reply relations)
- **Task B - Cross-domain Hate Speech Detection**: a binary classification task with test data from different domains. The main objective is to explore cross-domain hate speech detection in two evaluation settings. 
  - **XPoliticalHate**: the test set will consist of tweets from PolicyCorpusXL (the same as in Task A)
  - **XReligiousHate**: the task here will be recognizing religious hate, therefore the test set will consist of tweets from the ReligiousHate corpus
  
  For dealing withTask B, participants can use any kind of external data, even from other hate domains (obviously, participants can also use textual and contextual PolicyCorpusXL development data)
  
We decided to provide **four** separate official rankings, one for each sub-task.

**Two runs for each sub-task are available.**

Participants are not required to participate in all sub-tasks or to submit 2 runs.

Systems will be evaluated using F1-score computed over the two binary classes (HS or ¬HS). 

Therefore, submissions will be ranked by the averaged F1-score over the two classes, according the following equation:

F1 avg= (F1 HS+F1 ¬HS)/2

# Output files guidelines
Let's suppose the team name is **EVALITA**

The participants have to create an output for each run using the following file name structure:

**EVALITA**\_taskA\_textual\_run\_1.csv

**EVALITA**\_taskA\_textual\_run\_2.csv

**EVALITA**\_taskA\_contextual\_run\_1.csv

**EVALITA**\_taskA\_contextual\_run\_2.csv

**EVALITA**\_taskB\_XPoliticalHate\_run\_1.csv

**EVALITA**\_taskB\_XPoliticalHate\_run\_2.csv

**EVALITA**\_taskB\_XReligiousHate\_run\_1.csv

**EVALITA**\_taskB\_XReligiousHate\_run\_2.csv

The files have to be created using the format CSV (**comma** separated values).

The header of the file have to include the following two columns:

- anonymized\_tweet\_id
- label

The only admitted values for the column label are 0 or 1

#
# Important Dates

~~**7th February 2023**: development data available to participants~~

~~**30th April 2023**: [CFI closes](https://www.evalita.it/campaigns/evalita-2023/cfi/)~~

~~**7th May 2023:** test data available to participants~~

**12th – 19th May 2023**: evaluation windows and collection of participants results

**30th May 2023**: assessment returned to participants

**30th May 2023**: gold data available to participants


##
# from 7th February 2023: development data available to participants

Decrypt files with the password obtained filling this [form](https://forms.gle/jKvZLWfTUgWxxy7CA)
## Development description
The development set consist of 5,600 tweets belonging to **PolicyCorpusXL**

The available files are:
### training\_textual.csv
It contains the following fields:

- **anonymized\_tweet\_id**

The original tweet id has been replaced by a pseudo random integer that identifies a specific tweet.

- **anonymized\_text**

Urls have been replaced by the placeholder [URL].


|**original content**|#cronaca #ultimenotizie Tg Politico Parlamentare, Draghi: 'Sul recovery in gioco il futuro dell'Italia' - https://t.co/KBfgz9V6jR - #Letta #MarioDraghi #Meloni #Putin #Salvini #WalterBiot https://t.co/0c85wZIGlE|
| :- | :- |
|**anonymized content**|#cronaca #ultimenotizie Tg Politico Parlamentare, Draghi: 'Sul recovery in gioco il futuro dell'Italia' - [URL] - #Letta #MarioDraghi #Meloni #Putin #Salvini #WalterBiot [URL]|

Mentions have been replaced and mapped by a pseudo random integer that identifies a specific user.


|**original content**|@AndreaScanzi Devi rinascere forse 100 volte per poter solo nominare il tuo incubo #Renzi|
| :- | :- |
|**anonymized content**|@203951222958528 Devi rinascere forse 100 volte per poter solo nominare il tuo incubo #Renzi|

It means that the pseudo random integer 203951222958528 identifies all mentions of @AndreaScanzi, @AndreaScanzi if he is an author of a tweet, a source or a target in friends, retweets, and replies relations from/to @AndreaScanzi.

- **label**: 1 hateful tweets, 0 elsewhere
- **dataset**: training\_politics

### training\_contextual.csv
- **anonymized\_tweet\_id**

The original tweet id has been replaced by a pseudo random integer that identifies a specific tweet.

- **created\_at**

`	`the posting date of the tweet \*

- **retweet\_count**

the number of times the tweet has been retweeted \*

- **favorite\_count** \*

Indicates approximately how many times this tweet has been liked by Twitter users

- **source** \*

the source used for posting the tweet (e.g. Android, iOS, web)

- **is\_reply** \*

1 if the tweet is a reply. 0 elsewhere

- **is\_retweet** \*

1 if the tweet is a retweet. 0 elsewhere

- **is\_quote** \*

1 if the tweet is a quote. 0 elsewhere

- **anonymized\_user\_id**

the original author id has been replaced by a pseudo random integer (if available)

- **user\_created\_at** \*

the date the author created her/his account

- **statuses\_count** \*

the number of tweets posted by the author

- **followers\_count** \* 

the number of Twitter users that follow the author

- **friends\_count** \*

the number of Twitter users the author follows

- **anonymized\_description**

the self-description of the author of the tweet. We applied the same anonymization process applied to the field anonymized\_text of the file train\_textual.csv

\*  the value could be unavailable or set to 0 due to the fact that we were unable to recover the metadata of the tweet in 2022 (many months after the posting date). The tweet cold be removed by Twitter or deleted or made unavailable by the author)
###
### training\_contextual\_friends.csv
- **source**

An user identified by her/his anonymized\_user\_id that follows target

- **target**

`	`An user identified by her/his anonymized\_user\_id that is followed by source

N.B. it was not possible to recover to recover the friend list for all the authors of the dataset

all sources are authors at least one tweet of the training corpus
### training\_contextual\_retweet.csv
- **source**

An user identified by her/his anonymized\_user\_id that retweeted target

- **target**

`	`An user identified by her/his anonymized\_user\_id that has been retweeted by source

- **date**

The day source retweeted target

- **count**

`	`The number of times the source retweeted target that day

N.B. it was not possible to recover the retweet relations for all the authors of the dataset. All sources are authors at least one tweet of the training corpus
### training\_contextual\_reply.csv
- **source**

An user identified by her/his anonymized\_user\_id that replied target

- **target**

`	`An user identified by her/his anonymized\_user\_id that has been replied by source

- **date**

The day source replied target

- **count**

`	`The number of times the source replied target that day

N.B. it was not possible to recover the reply relations for all the authors of the dataset. All sources are authors at least one tweet of the training corpus


#
# from 7th May 2023: test data available to participants

Decrypt files with the password obtained filling this [form](https://forms.gle/jKvZLWfTUgWxxy7CA)
# Test description

The test set consists of 1,400 tweets belonging to **PolicyCorpusXL** and 3,000 tweets belonging to **ReligiousHate.**

An author that posted tweets belonging to both development and test sets, is identified by the same anonymized\_user\_id.

An user mentioned in both development and test sets, is identified by the same anonymized\_user\_id.

The test set is self-consistent. It means that, for that author that posted tweets belonging to both development and test sets, friends, retweets, and replies relations of that author are included in both training and test files.

The available files are:
### test\_textual.csv
It contains the following fields:

- **anonymized\_tweet\_id**

The original tweet id has been replaced by a pseudo random integer that identifies a specific tweet.

- **anonymized\_text**

Urls have been replaced by the placeholder [URL].

Mentions have been replaced and mapped by a pseudo random integer that identifies a specific user.

- **dataset**: test\_politics or test\_religious

- ~~**label**: 1 hateful tweets, 0 elsewhere~~

### test\_contextual.csv
- **anonymized\_tweet\_id**

The original tweet id has been replaced by a pseudo random integer that identifies a specific tweet.

- **created\_at**

`	`the posting date of the tweet \*

- **retweet\_count**

the number of times the tweet has been retweeted \*

- **favorite\_count** \*

Indicates approximately how many times this tweet has been liked by Twitter users

- **source** \*

the source used for posting the tweet (e.g. Android, iOS, web)

- **is\_reply** \*

1 if the tweet is a reply. 0 elsewhere

- **is\_retweet** \*

1 if the tweet is a retweet. 0 elsewhere

- **is\_quote** \*

1 if the tweet is a quote. 0 elsewhere

- **anonymized\_user\_id**

the original author id has been replaced by a pseudo random integer (if available)

- **user\_created\_at** \*

the date the author created her/his account

- **statuses\_count** \*

the number of tweets posted by the author

- **followers\_count** \* 

the number of Twitter users that follow the author

- **friends\_count** \*

the number of Twitter users the author follows

- **anonymized\_description**

the self-description of the author of the tweet. We applied the same anonymization process applied to the field anonymized\_text of the file train\_textual.csv

\*  the value could be unavailable or set to 0 due to the fact that we were unable to recover the metadata of the tweet in 2022 (many months after the posting date). The tweet cold be removed by Twitter or deleted or made unavailable by the author)
### test\_contextual\_friends.csv
- **source**

An user identified by her/his anonymized\_user\_id that follows target

- **target**

`	`An user identified by her/his anonymized\_user\_id that is followed by source

N.B. it was not possible to recover to recover the friend list for all the authors of the dataset

all sources are authors at least one tweet of the test corpus
### test\_contextual\_retweet.csv
- **source**

An user identified by her/his anonymized\_user\_id that retweeted target

- **target**

`	`An user identified by her/his anonymized\_user\_id that has been retweeted by source

- **date**

The day source retweeted target

- **count**

`	`The number of times the source retweeted target that day

N.B. it was not possible to recover the retweet relations for all the authors of the dataset. All sources are authors at least one tweet of the test corpus
### test\_contextual\_reply.csv
- **source**

An user identified by her/his anonymized\_user\_id that replied target

- **target**

`	`An user identified by her/his anonymized\_user\_id that has been replied by source

- **date**

The day source replied target

- **count**

`	`The number of times the source replied target that day

N.B. it was not possible to recover the reply relations for all the authors of the dataset. All sources are authors at least one tweet of the test corpus
#
#
# **from 30th May 2023**: gold data available to participants
Decrypt files with the password obtained filling this [form](https://forms.gle/jKvZLWfTUgWxxy7CA)
### gold\_textual.csv

It contains the following fields:

- **anonymized\_tweet\_id**

The original tweet id has been replaced by a pseudo random integer that identifies a specific tweet.

- **anonymized\_text**

Urls have been replaced by the placeholder [URL].

Mentions have been replaced and mapped by a pseudo random integer that identifies a specific user.

- **dataset**: test\_politics or test\_religious
- **label**: 1 hateful tweets, 0 elsewhere
#
# References

Cristina Bosco, Felice Dell’Orletta, Fabio Poletto, Manuela Sanguinetti, and Maurizio Tesconi. 2018. **Overview of the evalita 2018 hate speech detection task.** In Proceedings of the 6th evaluation campaign of Natural Language Processing and Speech tools for Italian (EVALITA 2018), Online. CEUR.org.

Fabio Celli, Mirko Lai, Armend Duzha, Cristina Bosco, and Viviana Patti. 2022. **Policycorpus xl: An Italian corpus for the detection of hate speech against politics**. In Proceedings of the Eighth Italian Conference on Computational Linguistics (CLiC-it 2021), volume 3033 of CEUR Workshop Proceedings, Aachen, Germany. CEUR-WS.org.

Armend Duzha, Cristiano Casadei, Michael Tosi, and Fabio Celli. 2021. **Hate versus politics: detection of hate against policy makers in italian tweets**. SN Social Sciences, 1(9):1–15.

Alan Ramponi A, Benedetta Testa, Sara Tonelli, Elisabetta Jezek 2022. **Addressing religious hate online: from taxonomy creation to automated detection**. PeerJ Computer Science 8:e1128 https://doi.org/10.7717/peerj-cs.1128

Manuela Sanguinetti, Gloria Comandini, Elisa Di Nuovo, Simona Frenda, Marco Stranisci, Cristina Bosco, Tommaso Caselli, Viviana Patti, and Irene Russo. 2020. **Overview of the evalita 2020 second hate speech detection task (haspeede 2)**. In Proceedings of the 7th evaluation campaign of Natural Language Processing and Speech tools for Italian (EVALITA 2020), Online. CEUR.org.



