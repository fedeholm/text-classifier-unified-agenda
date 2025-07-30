## Overview

This repository contains a series of files and tools to acquire data from the federal 'Unified Agenda of Regulatory and Deregulatory Actions' and run a series of simple text classifiers to predict if a given action is regulatory/deregulatory, based on past regulatory agendas that include such designation as part of the rule's information. 

This repo includes the following files:

1. README file.
2. A .csv file (*all_years_rules_links.csv*) including the Agency, Agenda Stage of Rulemaking, Rule	title, RIN, and Link. This last variable (Link) is the most important one, as it is the one needed by the web crawlers to perform the data mining tasks. This file contains all rules included in the Unuified Agenda for the periods Fall 2017, Spring 2018, Fall 2018, Spring 2019, Fall 2019, Spring 2020, and Fall 2020. The reason for this is that these agendas include a Executive Order (EO) 13771 Designation for each rule, that categorizes them into six different categories: Fully or Partially Exempt; Not subject to, Not significant; Regulatory; Deregulatory; Other; or Independent agency. We will use this information to train our classifiers later on.
3. A second .csv file (*TrainTest_designations_all_years*) required to train and test the text classifiers. The script includes everything necessary for the user to produce an equivalent file (after some minor manual data processing), but including this file streamlines the training of the classifiers. The file only includes those rules that were deemed Regulatory or Deregulatory, and excludes all other categories. It inlcudes three columns: Designation, Abstract, and Season.
4. A python script with a webcrawler to extract EO designations, a webcrawler to extract abstracts, and the necessary code to train and test a series of machine learning text clssifiers on the rules' abstracts. These are the predictors used by the classifier to determine whether a rule is regulatory or deregulatory.

The determination of the regulatory or deregulatory nature of the rule must be taken as an indicator of the potential nature of the rule. The final determination -in the absence of a formal categorization- must be made by engaging with the content of the rule itself. However, theis approach allows to make an educated guess about the overall trends and distribution of actions included in the Unified Agenda.
