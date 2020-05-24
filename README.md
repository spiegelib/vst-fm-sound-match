# FM Synthesizer Sound Matching Experiment

### Machine learning and evolutionary algorithms to program a VST FM synthesizer.

In synthesizer sound matching, algorithms are used to attempt to find parameters for a synthesizer in order to replicate a target sound as closely as possible. In this experiment six different algorithms are compared in their ability to sound match Dexed, a VST emulation of the Yamaha DX7 synthesizer. Four deep learning models are compared: a multi-layer perceptron (MLP), a long short term memory (LSTM) recurrent neural network, a LSTM model with highway layers (LSTM++), and a convolutional neural network. Two genetic algorithms are also included for comparison: a simple single objective genetic algorithm, and a multi-objective non-dominated sorting genetic algorithm (NSGA III). 

This repository contains python notebooks for an example experiment that highlights the use of the SpiegeLib software library for automatic synthesizer programming research and was published as a conference paper for the Audio Engineering Society Spring 2020 conference that was held virtually in June of 2020.

Original datasets and sound files used for evaluation can be downloaded from [zenodo](https://doi.org/10.5281/zenodo.3722784). For more information on this experiment and SpiegeLib please visit the [experiment website](https://spiegelib.github.io/spiegelib/examples/fm_sound_match.html)

---

### Requirements

In order to run these notebooks, you will need:

1. Dexed FM VST https://asb2m10.github.io/dexed/
2. Python 3.6 > 
3. A way to run python notebooks, we recommend [Jupyter in an Anconda environment](https://jupyter.readthedocs.io/en/latest/install.html)
4. [SpiegeLib in a conda environment](https://spiegelib.github.io/spiegelib/getting_started/installation.html)

### Installation

* Deatiled instructions on installing SpiegeLib in a conda virtual environment are available [here](https://spiegelib.github.io/spiegelib/getting_started/installation.html)
* SpiegeLib can be installed via pip: `pip install spiegelib`
* All dependencies except for [RenderMan](https://github.com/fedden/RenderMan) will be installed by pip. RenderMan will need to be installed manually.

### Running

To recreate the experiment from start to finish, you can run the notebooks in this order:

1. [synth_config.ipynb](../master/synth_config.ipynb) : Configures Dexed synthesizer for this experiment by selecting a subset of parameters to automatically program and freezing the rest.
2. [dataset_generation.ipynb](../master/dataset_generation.ipynb) : Create datasets for training and validating deep learning models. Also creates 25 audio targets for evaluating results.
3. [train_deep_learning_models.ipynb](../master/train_deep_learning_models.ipynb) : Train deep learning models using the dataset we just created. 
4. [sound_match_deep_learning.ipynb](../master/sound_match_deep_learning.ipynb) : Estimate synthesizer parameters to match the 25 evaluation audio targets using the trained deep learning models.
5. [sound_match_genetic.ipynb](../master/sound_match_genetic.ipynb) : Estimate synthesizer parameters to match the 25 evaluation audio targets using genetic algoritmhs.
6. [evaluation.ipynb](../master/evaluation.ipynb) : Evaluate the results of sound matching. 

[Pre-trained models](../master/saved_models) are also included in this repo which can be used. The datasets used in the original experiment are also available to download, see https://doi.org/10.5281/zenodo.3722784. 

