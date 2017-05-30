# OID_In_Silico_Experiments
Data and processing scripts for the in silico OID experiments

This repository contains the data and scripts for the in silico OID experiment work carried out by Ally Hume.

Essentially two sets of experiments were carried out:
* Comparison of OID with other input design approaches
* How many loops of OID are optimal for a 60 hour experiment

## Comparison of OID with other input design approaches

Several different approaches to designing the experiment input where tried.  These are described in the table below:

| Experiment name | Description | Git hub branch |
|-----------------|-------------|-----------------|
| OID         | Uses OID to design the full input (60 min steps)    | Experiment-CadBane |
| Random      | Randomly chooses a new input level (60 min steps) | Experiment-Ventress |
| Designed 13 | 13 input steps rising from minimum to maximum and back down again | Experiment-Biggs |
| Designed 61 | 61 input steps rising from minimum to maximum and back down again | Experiment-MazKanata |
| Pulse       | 10 minute maximum input pulse every hour, otherwise zero galactose | Experiment-Lobot |
| Step 60     | Alternate maximum and minimum galactose input for 6 hour periods | Experiment-Hondo |
| Step 1      | Alternate maximum and minimum galactose input for 1 hour periods | Experiment-Phasma |



## How many loops of OID are optimal for a 60 hour experiment?

