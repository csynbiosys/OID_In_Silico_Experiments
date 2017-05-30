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

The experiment code is in github: https://github.com/csynbiosys/AMIGO2R2016b

To run an experiment go to AMIGO2R2016b/Examples/In_Silico_Loop/ and run command such as
```
matlab -nodesktop -nosplash -r "run_in_silico_experiment('FooBar',20); quit;"
```
This will execute 20 runs of the experiment for each run output files called FooBar-*.dat and FooBar-*.mat. 


## How many loops of OID are optimal for a 60 hour experiment?

## Data and processing scripts

The data files are in the data directory. Additional runs that have not been included in these results (because I wanted
all approachs to have 30 runs) are in the data/notUsed directory.

There are two data processing scripts.  These use R and the knitr package. Both scripts are in the src directory.


