# Resume-Parsing-and-Analysis-App using Spacy and NER

This project aims to automate the extraction of key information from resumes and match candidate resumes with job descriptions based on the extracted information.

This project speaks about a field in Natural language Processing and Information Retrieval called Named Entity Recognition and how we can apply it for automatically generating summaries of resumes by extracting only chief entities like name, education background, skills, etc.
It is often observed that resumes may be populated with excess information, often irrelevant to what the evaluator is looking for in it. Therefore, the process of evaluation of resumes in bulk often becomes tedious and hectic. Through our NER model, we could facilitate evaluation of resumes at a quick glance, thereby simplifying the effort required in shortlisting candidates among a pile of resumes.

## What is Named Entity Recognition?

Named-entity recognition (NER) (also known as entity identification, entity chunking and entity extraction) is a sub-task of information extraction that seeks to locate and classify named entities in text into pre-defined categories such as the names of persons, organizations, locations, expressions of times, quantities, monetary values, percentages, etc. NER systems have been created that use linguistic grammar-based techniques as well as statistical models such as machine learning. Hand-crafted grammar-based systems typically obtain better precision, but at the cost of lower recall and months of work by experienced computational linguists.

## NER For Resume Summarization

### Dataset :

To create manually annotated training data to train the model. For this purpose, 1014 resumes were downloaded from an online jobs platform. These documents were uploaded to our online annotation tool and manually annotated.
The tool automatically parses the documents and allows for us to create annotations of important entities we are interested in and generates json formatted training data with each line containing the text corpus along with the annotations.

