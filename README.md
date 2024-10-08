# Datamodels

## Intruction
In the following work we tried to reproduce the results obtained by --- in the paper ---. Here the authors used a shallow neural network, called datamodel, to learn how to predict the output of another neural network (not necessarly shallow)  trained on a certain dataset D, for some given input X. In particoular, the idea is to train the datamodels using input output coples with as input a select subset of the training set derived from D (used to train the model for which we want to predict the outpu), and for output the result obtained from a model trained on the subset of D when X is given as input. Using it the datamodel will learn how to predict outputs for the original model trained on the whole training set derived form D.

The dimension of those dataset obtaine from the original training set is equal to alpha (costant with value between 0 and 1) times the original size of the dataset.

In particoular the couples of the subset used to train that model and the result from the model given X are stored and used to train the datamodel. The subset in particoular is stored in the form of a one-hot vector. 
In the paper they showed how, starting from a CNN that was built to perform classification on the cfar10, it was possible to exploit the base idea to assolve also differents task than just predicting the output of the considered model. In particoular we decided to focus on the task proposed in section ---.

Here the goal is to train the datamodel and use its parameters to identify the most similar and dissimilar images in the cifar10 training set to the one selected to learn how to predict.

Those images are found exploiting the structure of the datamodel, in fact the shallow neural network that represent the datamodel is composed by 50000 nodes, one for each image of the original training set of the cifar10. The idea is that since we are using one-hot vectors that represents the precens or absence of the i-th element of the training set with the i-th entry as input, we can then exploit the final magnitude of the parameters as a measure of positive or negative correlation between the i-th element of the dataset and the image that is feed in input. In particoular those with higer magnitude have higer positive correlation while the lowest one have an higher negative correlation.


## Conclusions

## How to Run the code
The code can be runned in its completnes in the colab notebooks, as all the libraries used and required, as the used dataset, are installed and imported at the beginning of the code, so there no particolar action needed to run it. However even if the project worked starting from the cifar10 dataset, to actually train the datamodels and obatain the wanted results it was necessary to build new datasets and to train many different models to then work on their results with the datamodels.

However since it required a lot of time and resources it is not possible to run everything in only one free-colab session. For this reason we runned the code over more than one session, building the required datasets step by step using auxiliary dataset to build the final ones, using Huggingn Face to store the datasets and update them at each step. HF gave us the possibility to avoid to compute the datasets from scratch at each iteration simplifying a lot our work.

In order to avoid to over ride the existing dataset and modifying them you will find some part of the code commented in order to avoid their execution(those are the parts used tobuilt new dataset object and update them on HF repository, overraiding the one already existing and are commented to avoid it). Those parte that required special attention are properly signaled other than commented.

To obtain a final accuracy of the datamodel we evaluated the results "by hand" as done in the paper.

