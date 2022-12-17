# CoraClassi

## Approach

Firstly, I decided not to use the cora.cites file in this first version of my machine learning model. There is information in what papers are adjacent in the graph, but I could not think of a satisfactory way to use this information. I would assume that adjacent papers are likely to share the same label and could therefore improve the prediction of the label of a particular paper. But whether its adjacent papers (at least those known in the training split) indicate the label of a specific paper or not will vary accross the dataset. Some papers might be adjacent to more papers with a different label than their own. So, in order to use the information contained in the graph, it is necessary to first better understand the graph structure. I assume then a more advanced model is possible which also has to learn when to rely on information contained in the graph to change the prediction implied by only using the word attributes. Open questions for me are whether the search depth in the graph should then be more than 1 and whether this approach generalizes to other data sets. In short, including the graph in the first machine learning model seemed beyond my time scope. I will try to include the graph to improve predictions in a second approach.

I started by loading the cora.content file and storing it in a pandas dataframe. Then I defined my model using the OneVsRestClassifier from the sklearn library. Since it is a multiclass classification problem and I assumed that all classes are probably independent from each other, it should be able to solve the problem. (I am not sure which classifier is the most suitable, I also considered the k-nearest neighbors algorithm.) I proceeded by splitting the dataset using the KFold method and then training and testing my model for each fold. The total accuracy of the model is then the mean over all scores achieved on different folds.

## How to execute

Since, I did not have a machine with a python installation available at the time, the easiest solution for me was to use a goole colaboratory file instead and upload it to GitHub. I hope that is not inconvient for you. You only need to provide the extracted cora.content file in the first execution box then the rest of the notebook will execute on its own. The predictions will be saved to the directory which can be expanded on the left and can be downloaded from there. The accuracy of the model for each fold will be printed to the screen as well as the mean accuracy over all folds.
