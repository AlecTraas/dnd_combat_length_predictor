# D&D Combat Length Predictor
A Dungeons and Dragons data science project using the large FIREBALL dataset to predict the length of a given combat in number of rounds.

## FIREBALL Dataset
The dataset we are using has a GitHub repo here: https://github.com/zhudotexe/FIREBALL We have gotten permission from the managers of this dataset to use it for this project. The data consists of a collection of 24,748 JSONL files, each one containing a script for one full combat encounter run on Discord with the help of the Avrae bot. Each line contains an utterance by a player, and then is followed by an action, with periodic updates on the current game state (each character and their remaining health and resources). The original use of this dataset was a natural language processing project where they attempted to produce dialogue to accompany a particular action, or transform dialogue into an action that Avrae would understand. We will instead be using it to predict the length of a combat in number of rounds given the starting state.

## High Level Approach
Since each JSONL file consists of a single full combat encounter, each one will naturally become a single observation in our cleaned dataset. We will need to write scripts to extract the starting state from each file, and then pick from these features to try and predict the corresponding combat length from the same combat.

## Stakeholders
- Wizards of the Coast (Dungeons and Dragons publisher)
- Roll20, D&DBeyond, and other online tabletop systems which already have a wealth of tools to help dungeon masters with session planning

## KPIs
- Measure the difference in performance for our model compared to a baseline model, e.g. average combat length over the dataset.
- Count how many independent features we can extract which are good predictors for combat length.
