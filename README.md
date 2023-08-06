# Fine-tuning the HuggingFace GPTJ-6B large language model (LLM) using domain-specific knowledge

### Overview

This repo contains a notebook that will walk you through how to fine-tune a pre-trained large language model with domain specific knowledge.

The domain specific dataset that we will be using to fine-tune this model will be United Kingdom (U.K.) Supreme Court case documents. There is roughly 693 legal case documents in the training dataset.

### Prereqs

To run this notebook we assume you have knowledge about running a SageMaker Notebook instance or SageMaker Studio Notebook instance.

### SageMaker Studio Resources

[Introduction to Amazon SageMaker Studio - Video](https://www.youtube.com/watch?v=YcJAc-x8XLQ)

[Build ML models using SageMaker Studio Notebooks - Workshop](https://www.youtube.com/watch?v=1iSiN4sVMjE)

## Dataset info
* <strong>Page count:</strong> ~17,718
* <strong>Word count:</strong> 10,015,333
* <strong>Characters (no spaces):</strong> 49,897,639

The entire dataset is available to be downloaded [here](https://zenodo.org/record/7152317#.ZCSfaoTMI2y)

## Considerations when fine-tuning the model

The notebook has been configured to allow you to only use a subset of the entire dataset to fine-tune the model if you would like. There is a variable named _**doc_count**_ in the _**Data Prep**_ section. You can set this number to whatever you would like and it will only fine-tune the model based on the number of documents you set this variable to. The smaller this value the faster the model will fine-tune.

## Training/Tuning Time estimates

Here are the estimated training times based on total number of case documents in the training dataset.

#### All training was ran on 1 - *ml.p3dn.24xlarge* instance

#### <strong>Training dataset document count </strong> 250
Training time: 1 hour 41 minutes

#### <strong>Training document count</strong> 500
Training time: 2 hours 57 minutes

#### <strong>Training document count</strong> 693
Training time: 4 hours


## GPTJ-6B base model

Steps you will go through in the notebook to test the base model

1. Clone this repo in a SageMaker Studio Jupyter notebook
2. Install needed notebook libraries
3. Configure the notebook to use SageMaker
4. Retrieve base model container
5. Deploy the model inference endpoint
6. Call inference endpoint to retrieve results from the LLM

## Fine-tuned model

Steps you will go through in the notebook to test the fine-tuned model

1. Download dataset
2. Prep the dataset and upload it to S3
3. Retrieve the base model container
4. Set hyperparameters for fine-tuning
5. Start training/tuning job
6. Deploy inference endpoint for the fine-tuned model
7. Call inference endpoint for the fine-tuned model
8. Parse endpoint results

### Final Step

* Be sure you delete all models and endpoints to avoid incurring unneeded spend.

### Disclaimer
This notebook demos how you can fine-tune an LLM using transfer learning. Even though this notebook is fine-tuned using actual (U.K.) Supreme Court case documents you should not use this notebook for legal advise.

## Running notebook

To run the notebook clone this repo in a SageMaker Notebook instance or SageMaker Studio Notebook.

[Go to Notebook](fine_tuning.ipynb)
