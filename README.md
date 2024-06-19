# Resume-Parsing-and-Analysis-App using Spacy and NER

This project aims to automate the extraction of key information from resumes and match candidate resumes with job descriptions based on the extracted information.

This project speaks about a field in Natural language Processing and Information Retrieval called Named Entity Recognition and how we can apply it for automatically generating summaries of resumes by extracting only chief entities like name, education background, skills, etc.
It is often observed that resumes may be populated with excess information, often irrelevant to what the evaluator is looking for in it. Therefore, the process of evaluation of resumes in bulk often becomes tedious and hectic. Through our NER model, we could facilitate evaluation of resumes at a quick glance, thereby simplifying the effort required in shortlisting candidates among a pile of resumes.

## Techniques Used
1. NER
2. spaCy
   
## 1. What is Named Entity Recognition?

Named-entity recognition (NER) (also known as entity identification, entity chunking and entity extraction) is a sub-task of information extraction that seeks to locate and classify named entities in text into pre-defined categories such as the names of persons, organizations, locations, expressions of times, quantities, monetary values, percentages, etc. NER systems have been created that use linguistic grammar-based techniques as well as statistical models such as machine learning. Hand-crafted grammar-based systems typically obtain better precision, but at the cost of lower recall and months of work by experienced computational linguists.

## NER For Resume Summarization

### Dataset :

To create manually annotated training data to train the model. For this purpose, 1014 resumes were downloaded from an online jobs platform. These documents were uploaded to our online annotation tool and manually annotated.
The tool automatically parses the documents and allows for us to create annotations of important entities we are interested in and generates json formatted training data with each line containing the text corpus along with the annotations.

### Online annotate tool link: https://tecoholic.github.io/ner-annotator/

The dataset consisting of 1014 annotated resumes can be found in the dataset folder in my directory 

## 2. spaCy module

spaCy is an open-source library for advanced Natural Language Processing (NLP) in Python. It's designed specifically for production use and provides a robust and efficient way to process and analyze large volumes of text data.

### How spaCy works:
spaCy’s tagger, parser, text categorizer and many other components are powered by statistical models. Every “decision” these components make – for example, which part-of-speech tag to assign, or whether a word is a named entity – is a prediction based on the model’s current weight values. The weight values are estimated based on examples the model has seen during training. To train a model, you first need training data – examples of text, and the labels you want the model to predict. This could be a part-of-speech tag, a named entity or any other information.

Training is an iterative process in which the model’s predictions are compared against the reference annotations in order to estimate the gradient of the loss. The gradient of the loss is then used to calculate the gradient of the weights through backpropagation. The gradients indicate how the weight values should be changed so that the model’s predictions become more similar to the reference labels over time.
