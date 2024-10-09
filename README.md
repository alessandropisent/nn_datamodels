# Datamodels

The following code is an implementation of the paper : Datamodels: Predicting Predictions from Training Data^[1] 

The project team is composed by:
Capomagi Federico Andrea 1842169
Pisent Alessandro 2085678

## How to Run the code
The code can be run in its completeness in the colab notebooks. All the libraries used and required, like the used dataset, are installed and imported at the beginning of the code, so there is no particolar action needed to run it. 

However even if the project worked starting from the cifar10 dataset, to train the datamodels and obtain the wanted results, we need to build new Datasets that we will upload to Huggin Face, to simplify the project. 

However since it required a lot of time and resources it is not possible to run everything in only one free-colab session. For this reason we runned the code over more than one session, building the required datasets step by step using auxiliary dataset to build the final ones, using Huggingn Face to store the datasets and update them at each step. HF gave us the possibility to avoid to compute the datasets from scratch at each iteration simplifying a lot our work, we want to stress out that without HF it would  not be possible to build these datasets in one colab session since for example, the running time was about a couple of weeks to train the 5K CNNs.

In order to avoid to over ride the existing dataset and modifying them you will find some part of the code commented in order to avoid their execution(those are the parts used tobuilt new dataset object and update them on HF repository, overraiding the one already existing and are commented to avoid it). Those parte that required special attention are properly signaled other than commented. Furthermore the part of code that was used to generate the code step by steps will run normally but produce a small part of it, and will upload just that part that was computed.  


[1]: Andrew Ilyas, Sung Min Park, Logan Engstrom, Guillaume Leclerc, Aleksander Madry, Datamodels: Predicting Predictions from Training Data, https://arxiv.org/abs/2202.00622
