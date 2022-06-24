# industrial-cta

This is a repository with the supplementary material files for the paper "Beyond the Lookup: Learning to Annotate Tables Using Semantic Data Models in Industry" which is submitted to the ISWC In-Use Track. 


Here we share the equipment ontology file equipment_onto.owl and the diagram explaining it. We share the queries that we used for extracting keywords from POSC Caeser and QUDT, and the lists of keywords that we used for the labeling functions. Below, we present the results of the additional experiments done after the Objection & Responce phase.

The upper ontology ISO 15926-14 can be accessed [here](https://rds.posccaesar.org/ontology/lis14/ont/core/).
The pretrained TURL model which is used as table-encoder in the paper is accessible on this [link](https://github.com/sunlab-osu/TURL).

Here is the diagram of the equipment ontology
![Domain ontology](https://user-images.githubusercontent.com/10827830/167885189-0772edc9-73f8-4ab6-ae07-4acf2a9fc682.png)

## Extended evaluation results

[Table 3](https://user-images.githubusercontent.com/10827830/175645684-f40c23c3-d106-43c9-9f95-d0b68d5eb901.png) shows the achieved MAP in the unsupervised setting, averaged by the number of test columns in a cluster.  


[Table 4!](https://user-images.githubusercontent.com/10827830/175647212-3f14f966-ada2-477e-bd19-6bb25ee1d5da.png) shows the achieved F1 score, micro averaged, for each of the semantic classes in the the three different settings.
Unsupervised - the calculated F1 score per class in all of the clusters, averaged over the number of clusters that we can evaluate.
Supervised - the achieved F1 score per class in the multi-label classification setting where we use the labeles learned with the Snorkel model as supervision
Weak sup. - in this setting we calculate the F1 score same as in the supervised setting, but in this case the predictions for the column types are generated only based on the Snorkel labeling function

[Table 5](https://user-images.githubusercontent.com/10827830/175645743-a1b80b88-51ec-418e-9655-2bf32cd0a1a4.png) shows the evaluation of the supervised approach in terms of the achieved Precision, Recall and F1 score per class.


