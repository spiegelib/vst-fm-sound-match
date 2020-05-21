# FM Synthesizer Sound Matching Experiment

Using machine learning and evolutionary algorithms to program a VST FM synthesizer. 

This repository contains python notebooks for an example experiment that highlights the use of the SpiegeLib software library for automatic synthesizer programming research and was published as a conference paper for the Audio Engineering Society Spring 2020 conference that was held virtually in June of 2020.

For more information on this experiment and SpiegeLib please visit the [experiment website](https://spiegelib.github.io/spiegelib/examples/fm_sound_match.html)

---

### Requirements

In order to run these notebooks, you will need:

1. Dexed FM VST https://asb2m10.github.io/dexed/
2. Python 3.6 > 
3. A way to run python notebooks, we recommend [Jupyter in an Anconda environment](https://jupyter.readthedocs.io/en/latest/install.html)
4. [SpiegeLib in a conda environment](https://spiegelib.github.io/spiegelib/getting_started/installation.html)

### Installation

* SpiegeLib can be installed via pip: `pip install spiegelib`
* All dependencies except for [RenderMan](https://github.com/fedden/RenderMan) will be installed by pip. RenderMan will need to be installed manually.
* Deatiled instructions on installing RenderMan in a conda environment can be found [here](https://spiegelib.github.io/spiegelib/getting_started/installation.html#installing-renderman-in-an-anaconda-environment). MacOSX only currently.

### Running

To recreate the experiment from start to finish, you can run the notebooks in this order:

1. [synth_config.ipynb](../master/synth_config.ipynb) : Configures Dexed synthesizer for this experiment by selecting a subset of parameters to automatically program and freezing the rest.
2. [dataset_generation.ipynb](../master/dataset_generation.ipynb) : Create datasets for training and validating deep learning models. Also creates 25 audio targets for evaluating results.
3. [train_deep_learning_models.ipynb](../master/train_deep_learning_models.ipynb) : Train deep learning models using the dataset we just created. 
4. [sound_match_deep_learning.ipynb](../master/sound_match_deep_learning.ipynb) : Estimate synthesizer parameters to match the 25 evaluation audio targets using the trained deep learning models.
5. [sound_match_genetic.ipynb](../master/sound_match_genetic.ipynb) : Estimate synthesizer parameters to match the 25 evaluation audio targets using genetic algoritmhs.
6. [evaluation.ipynb](../master/evaluation.ipynb) : Evaluate the results of sound matching. 

[Pre-trained models](../master/saved_models) are also included in this repo which can be used. And the datasets generated in the original experiment are available to download. 

