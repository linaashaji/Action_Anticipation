# Action_Anticipation

<h1>This repository is dedicated to the action anticipation code of the paper:
<b>'Is attention to bounding boxes all you need for pedestrian action prediction?'</b>
<p>
https://arxiv.org/abs/2107.08031
</p></h1>

<h1>
<b>Problem Formulation:</b>
</h1>

We formulate the pedestrian action prediction as a binary classification problem where the objective is to predict whether the pedestrian will start crossing the street at some time t given the observation of length m. The event is at the time that the pedestrian starts to cross or at the last frame the pedestrian is observable in case no crossing takes place. 

The observation data sequence for each pedestrian is sampled so that the last frame of observation is between 1 and 2s (or 30 − 60 frames at 30 fps) prior to the crossing event start (the critical crossing frame is provided directly in the dataset annotations).


<h1>
<b>Data Preprocessing:</b>
</h1>

For every pedestrian, we generate observation sequences going from the lower bound of the time to event interval into its upper bound (TTE = [30 - 60] in our case), where each obs_sequence is 0.5 sec (16 frames) along with an overlap of 60% with the next obs_sequence.



<h1>
<b>Models Training/Testing:</b>
</h1>

The training and testing of our methods is done on the PIE dataset. Download the PIE dataset from the link below and place it under the PIE_dataset directory:
https://github.com/aras62/PIE

We applied multiple Transformer variations for the classification task.

* Encoder-only architecture with classifier on the top: TEO model.
* Encoder-only architecture with pooling layers between the Encoder Layers and a classifier on the top: TEP model.
* Full Transformer Encoder-Decoder model with weighted average of the regression and classification Loss: TED model.


<b>For testing the pre-trained models:</b>

1- Download the models from:
https://drive.google.com/drive/folders/1FMB1ywiQ9-mT2g3YO6GrN7hOZ9bdqyUF?usp=sharing

2- Place them in the checkpoints folder.

3- run the Test_TEO.py, Test_TEP.py, or Test_TED.py file according to the tested variant model.

<b>For training the models from scratch:</b>

1- run the TEO_experiment.py, TEP_experiment.py, or TED_experiment.py file according to the training variant model.



<h1>
<b>CP2A dataset:</b>
</h1>

We simulated a new dataset using CARLA for pedestrian action prediction.
For more details about the dataset, check the following github repository:

https://github.com/linaashaji/CP2A


<h1>
<b>Authors</b>
</h1>

* [Lina Achaji](https://scholar.google.com/citations?user=RMO2zJAAAAAJ&hl=en)

Please send an email to lina.achaji@stellantis.com or lina.achaji@inria.fr if there are any problems with using the data or the code.


