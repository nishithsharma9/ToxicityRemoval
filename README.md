# FDS Project: Toxicity Removal from Text
In this paper, we present an analysis of the removal of toxicity and analyze its effects on mitigating bias to determine the relationship between them. We suggest two approaches to remove toxicity from text. A base model by building a toxicity classifier and removing the text predicted as toxic. An advanced solution to remove toxicity by training a language model to mask the toxic spans in text.

We use a bag-of-words representation for sentences in the dataset. Essentially, we are calculating fixed-length vectors for every instance in the dataset using a bag-of-words model. We trained our model using the trainer libraries of RoBERTa-based trans- formers. For training on toxic spans detection, we transform the dataset into SpaCy documents con- taining text and entities (toxic spans) as labels.

## Data:
1. ToxicSpanDetectionData: Dataset consisting of toxic span indexes over tweets data, used in the paper Chhablani et al., 2021.
2. ToxicTextClassifierData: Dataset multi-class toxicity dataset. https://www.kaggle.com/competitions/jigsaw-toxic-comment-classification-challenge
3. BiasPredictionScores : This has the output predictions from the external evaluations run over raw unmasked datapoints and the masked outputs of the transformer. We use this in building the evaluation metrics for the transformers performance.
4. GenderWordData: 
5. SentimentAnalysisData:

## Transformer: 
###### *The repo contains the POC, the final submission will have the final models files. It will still take multiple training iterations to get the flow and results at par.
<img src="https://github.com/nishithsharma9/NLUProject/blob/0c40c0d102f1d4bc26e90e927d976ca4b195f1ce/Images/transformer.jpg" width="50%" height="50%"><br>
1. Training Transformer: The POC of training procedures are stored in python notebooks independently executable. Were eventually run on HPC for training.
2. Models: The saved models serialized files stored here which are then loaded into the analysis notebooks to generate outputs of the transformer.
3. Analysis: Read the model files and run the flow of execution for the detoxification and masking of toxic elements. The evaluation of the external model analysis is also present here where the raw input and the masked output of the transformer is passed through an external evaluation metrics to generate the toxicity prediction outputs and generating the evaluation metrics on how much datapoints was the transformer able to detoxify by masking toxic spans.

<img src="https://github.com/nishithsharma9/NLUProject/blob/0c40c0d102f1d4bc26e90e927d976ca4b195f1ce/Images/DetoxificationEvaluation.jpg" width="40%" height="40%"><br>

<br>
