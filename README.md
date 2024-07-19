# industrial-cta
In this repository we share an equipment ontology file equipment_onto.owl and the diagram explaining it. We share the queries that we used for extracting keywords from POSC Caeser and QUDT, and the lists of keywords that we used for the labeling functions. Below, we present the results of the additional experiments done after the Objection & Responce phase.

The upper ontology ISO 15926-14 can be accessed [here](https://rds.posccaesar.org/ontology/lis14/ont/core/).
The pretrained TURL model which is used as table-encoder in the paper is accessible on this [link](https://github.com/sunlab-osu/TURL).

Here is the diagram of the equipment ontology
![Domain ontology](https://user-images.githubusercontent.com/10827830/167885189-0772edc9-73f8-4ab6-ae07-4acf2a9fc682.png)

## Evaluation models

The **weakly-supervised model** is the domain adapted TURL model. The input to the model are the tables from the training set with the labels from the Snorkel model used as a weak supervision. After training for 10 epochs, we evaluate the performance of the model on the test set. 
![Supervised](https://user-images.githubusercontent.com/10827830/216993393-7bf5bef3-d8f4-46e0-a287-22f529a5292a.jpg)

We use the **Snorkel generative model** to generate predictions for the column types based on the defined Snorkel labeling function. The training set together with the pre-defined labeling functions are the input to the Snorkel model. We evaluate the performance of the model on the test set.

In the case when there are no labels, we use **unsupervised method - DBSCAN clustering**. After clustering the whole dataset (columns from train, validation and test set), first, we use the columns from the validation set to calculate the probability distribution over all of the classes for every cluster which contains points from the validation set. We then rank the classes according to the calculated distribution. For assigning a label to a cluster, we count the majority class of the annotated columns from the test set. 

![eval_models](https://user-images.githubusercontent.com/10827830/216995262-16f4d1d1-860c-4c01-9f34-aacccd79491b.png)

