# Subject-Drop

Paper title: Partial truths: Adults choose to mention agents and patients in proportion to informativity, even if it doesn’t fully disambiguate the message.

This repository serves as the supplemental materials for the submitted manuscript OPMI-D-16-00024.  It's currently anonymized for peer review. 

### Abstract

How do we decide what to say to ensure our meanings will be understood? The Rational Speech Act model (RSA, Frank & Goodman, 2012) asserts that speakers plan what to say by comparing the informativity of words in a particular context. We present the first example of an RSA model of sentence level (who-did-what-to-whom) meanings. In these contexts, the set of possible messages must be abstracted from entities in common ground (people and objects) to possible events (*Jane eats the apple, Marco peels the banana*), with each word contributing unique semantic content. How do speakers accomplish the transformation from context to compositional messages? In a communication game, participants described transitive events (e.g. Jane pets the dog), with only two words, in contexts where two words either were or were not enough to uniquely identify an event. Adults chose utterances matching the predictions of the RSA even when there was no possible fully successful choice. Thus we show that adults’ communicative behavior can be described by a model that accommodates informativity in context, beyond the set of possible entities in common ground.  This study suggests that full-blown natural speech may result from speakers who model and adapt to the listener’s needs.

### Repository Contents

#### Stims for Multi-distractor/

All stimuli used for the experiment reported in this paper. We include the original clip art used while generating the stimuli (objects), all context scenes (e.g. 1 person and 6 animals for the 'FEED' event, FEED_1_6.jpg), and all actions (FEED, DRINK, etc.)


#### Adult - Multidistractor/

##### Folders

* batch/
* log/

The data outputs from AMT and the willow script. The batch files are exactly as collected, and the response files in log/ are updated only by the inclusion of extra columns used to classify text responses. 

* MD11-20-12/

The willow script (randomizes order/condition assignments, displays trials to participants, records responses to our server)

* Response coding/

Files used during the initial coding of raw responses to category (e.g. 'dog' -> PATIENT). This folder also contains a full description of how coding of edge cases were handled during this step.

##### Files

* MD_turk.R, lab-misc.R

The main analysis pipeline, which starts from the raw data and produces all analyses reported in Experiment 1. This file generates *humandata.csv* [includes just the 'normal' ({AVP} choose 2) responses, used to calculate parameters for the models] and *humanPerformance.jpg*

* snazzy potato 11-20.txt

IDs of AMT workers who participated in a pilot version of the study and thus shouldn't be included in analysis (we told them not to sign up if they had been in that experiment but some did anyway)

#### MODELS/

* humandata.csv

Identical to the version in Adult - Multidistractor/, copied here for convenience

* mainFun.m, modelInformativeUtt.m

Two matlab scripts that instantiate the models described in the paper; outputs are saved to the (many) csv files; note that the loop produces outputs for both the A human data and B human data, but in cases where there are no data-fit parameters these wind up being identical)

* CompareModelToData.R

Computes all the correlations and graphs reported in the modeling section of the paper, plus some new exploratory plots of human vs. model predictions by word. This script produces all the jpgs.

* CSVs: dummycost, informative_baserate, informative_nobaserate, succeedorfail, etc. 

Outputs of the models, produced by mainFun.m

* one word models/

Contains versions of the models used earlier on; they generated predictions for 1 word productions followed by sampling 2 words w/o replacement from those likelihoods (this is much more confusing to read about than the 2 word version)
