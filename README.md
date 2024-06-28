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

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/8187c55e-5e5c-4e81-919b-8438de67630d)

When training a model, we don’t just want it to memorize our examples – we want it to come up with a theory that can be generalized across unseen data. After all, we don’t just want the model to learn that this one instance of “Amazon” right here is a company – we want it to learn that “Amazon”, in contexts like this, is most likely a company. That’s why the training data should always be representative of the data we want to process. A model trained on Wikipedia, where sentences in the first person are extremely rare, will likely perform badly on Twitter. Similarly, a model trained on romantic novels will likely perform badly on legal text.

## Results and Evaluation of the model :

The model is tested on 20 resumes and the predicted summarized resumes are stored as separate .txt files for each resume.

For each resume on which the model is tested, we calculate the accuracy score, precision, recall and f-score for each entity that the model recognizes. The values of these metrics for each entity are summed up and averaged to generate an overall score to evaluate the model on the test data consisting of 20 resumes. The entity wise evaluation results can be observed below . It is observed that the results obtained have been predicted with a commendable accuracy.

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/3d55f26d-7d0b-4081-8b75-c6d7b13cf3d3)

## Model deployment and simple Web application using Flask

Flask is a lightweight and flexible web framework for Python. It is designed to make it easy to create web applications quickly with minimal overhead.

### Features of Web:

Home Page: 

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/b544d006-bb29-404e-bb46-0b9d2850582f)

1. HR can Post the Job

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/658a5231-640d-422a-b7a1-4c0262cf7781)

2. Candidates can apply for the job by uploading their resume.

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/9be6711e-6f97-45d4-aa02-b0117890e933)

3. HR can view the candidates details

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/a63e4625-14be-49e6-926e-6162588a9296)

4. HR can view the candidates who have applied, along with their matching percentage to the job description

![image](https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App/assets/92878457/ae055bfd-a40c-42f8-9000-c5258e693045)

## Initial Setup:
Clone repo and create a virtual environment
```
$ git clone https://github.com/Pacchu04/Resume-Parsing-and-Analysis-App.git
$ cd Resume-Parsing-and-Analysis-App
$ python -m venv venv
$ venv\Scripts\activate
```
Install dependencies
```
$ (venv) pip install -r requirements.txt
```
Replace GOOGLE_CLIENT_ID in app.py
```
$ Create OAuth Client ID and Download json file and add client_secret.json in main directory
```
Replace MONGO_URI
```
$ Create Database Service and generate API key replace it in app.py 
```
Add assets folder which contain trained model
```
https://drive.google.com/drive/folders/1cKpAZBPW-ijUFnc2aPlLhIGqt3aRUDxH?usp=sharing
```

Finally flask run to start the server
```
flask run 
```
