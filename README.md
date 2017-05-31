# OID_In_Silico_Experiments
Data and processing scripts for the in silico OID experiments

This repository contains the data and scripts for the in silico OID experiment work carried out by Ally Hume.

Essentially two sets of experiments were carried out:
* Comparison of OID with other input design approaches
* How many loops of OID are optimal for a 60 hour experiment

## Comparison of OID with other input design approaches

Several different approaches to designing the experiment input where tried.  These are described in the table below:

| Experiment name | Description | Git branch |
|-----------------|-------------|-----------------|
| OID         | Uses OID to design the full input (60 min steps)    | Experiment-CadBane |
| Random      | Randomly chooses a new input level (60 min steps) | Experiment-Ventress |
| Designed 13 | 13 input steps rising from minimum to maximum and back down again | Experiment-MazKanata |
| Designed 61 | 61 input steps rising from minimum to maximum and back down again | Experiment-Biggs |
| Pulse       | 10 minute maximum input pulse every hour, otherwise zero galactose | Experiment-Lobot |
| Step 60     | Alternate maximum and minimum galactose input for 6 hour periods | Experiment-Hondo |
| Step 1      | Alternate maximum and minimum galactose input for 1 hour periods | Experiment-Phasma |

The experiment code is in github: https://github.com/csynbiosys/AMIGO2R2016b

To run an experiment clone the repository, checkout the appropriate branch then go to `AMIGO2R2016b/Examples/In_Silico_Loop` and 
a run command such as
```
matlab -nodesktop -nosplash -r "run_in_silico_experiment('FooBar',20); quit;"
```
This will execute 20 runs of the experiment for each run output files called `FooBar-n.dat` and `FooBar-n.mat`. 

The github commit versions used were:

| Branch name |  Version|
|-------------|---------|
| Experiment-CadBane   |  fc25742547975bcbae60d1683428fa048ebaea5  |
| Experiment-Ventress  |  5af21b6ed4ec07c32cea1b1d2f79afc5e0697123 |
| Experiment-Biggs     | 27141c2d65942aef7f5ed7c078fdafe5e897e105  |
| Experiment-MazKanata |  31b15e633a8f2a65966be1b53287cee0351d8c70 |
| Experiment-Lobot     | 6dfa7704c2fba572e75ed64be22ed80d0276c95d  |
| Experiment-Hondo     |  45b477e8cb20597e5f34501ee25458b99bf41c58 |
| Experiment-Phasma    |  22149e39961806e5ad1aeb863690cfa1454dc08e |


## How many loops of OID are optimal for a 60 hour experiment?

Here we varied how many OID loops we execute in the 60 hours. For example, are 2 executions of OID each planning the input for 30 hours better or worse than, say, 30 executions of OID each planning for 2 hours.

The experiments executed were:

| Number of loops |  Duration of each OID input (hours) | Github branch |
|-----------------|-----------------------------|---------------|
| 2 | 30 | Experiment-Gungi |
| 3 | 20 | Experiment-Gungi |
| 4 | 15 | Experiment-Gungi |
| 5 | 12 | Experiment-Gungi |
| 6 | 10 | Experiment-Gungi |
| 8 | 4x8 and 4x7 | Experiment-BB8 |
| 10 | 6 | Experiment-Gungi |
| 12 | 5 | Experiment-Gungi |
| 15 | 4 | Experiment-Gungi |
| 20 | 3 | Experiment-Gungi |

To run the experiment in the `Experiment-Gungi` branch, checkout the branch and then go to `AMIGO2R2016b/Examples/In_Silico_Loop` and run a command such as
```
matlab -nodesktop -nosplash -r "run_in_silico_experiment('FooBar',5,20); quit;"
```
This will execte 20 runs of the 5-loops experiments.

To run the 8-loop experiment in the Experiment-BB8 brach, checkout the branch then go to `AMIGO2R2016b/Examples/In_Silico_Loop` and run a command such as
```
matlab -nodesktop -nosplash -r "run_in_silico_experiment('FooBar',20); quit;"
```
This will execte 20 runs of the 8-loops experiments.

Note that these scripts seem to take up more and more memory as they run and this can cause them to slow down considerably. I prevent that in the final execution I always executed just two or three runs at a time then executed more with another matlab invocation. The `-wait` flag was very useful here to prevent the command line from terminating until all the runs had been executed.

The github commit versions used were:

| Branch name |  Version|
|-------------|---------|
| Experiment-Gungi  |  bb42b49df1cb5efd2b9286ae6c24edd485823ff7  |
| Experiment-BB8    |  df49044ac80804c67f745ed3603f623f05300265  |


## Data and processing scripts

The data files are in the `data` directory. Additional runs that have not been included in these results (because I wanted
all approachs to have 30 runs) are in the `data/notUsed` directory.

The example input data can be found in the 'data/exampleInputs' directory.

There are two data processing scripts.  These use R and the knitr package. Both scripts are in the `src` directory.


