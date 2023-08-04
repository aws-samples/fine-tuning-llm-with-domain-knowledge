# Fine-tuning a large language model (LLM) using domain-specific knowledge

### Overview

This repo contains a notebook that will walk you through how to fine-tune a pre-trained large language model with domain specific knowledge.

The domain specific dataset that will be used to fine-tune the the model will be United Kingdom (U.K.) Supreme Court case documents. There are roughly 693 legal documents as part of the dataset that can be used to fine-tune the model.

### Dataset info

* <strong>Page count:</strong> ~17,718
* <strong>Word count:</strong> 10,015,333
* <strong>Characters (no spaces):</strong> 49,897,639

The entire dataset is publically available and can be download [here](https://zenodo.org/record/7152317#.ZCSfaoTMI2y)

## Notebook Steps

### Using the base model

1. Install needed notebook libraries
3. Configure the notebook to use SageMaker
4. Retrieve base model container
5. Deploy inference endpoint
6. Call inference endpoint to retrieve results from the LLM

### Using the fine-tuned model

1. Prep the dataset
2. Retrieve model container
3. Set hyper parameters for fine-tuning
4. Start training/tuning job
5. Deploy inference endpoint for the fine-tuned model
6. Call inference endpoint for the fine-tuned model
7. Parse endpoint results

### Next Steps

Now that you understand the purpose of the **fine_tuning.ipynb** notebook, you should have an understanding of what it will walk you through.

### Final Step

* Be sure you delete all models and endpoints

## Considerations when fine-tuning the model

The time that it took to fine tune the model on one GPU based instance was <placeholder> hours. The notebook has been configured to allow you to only use a subset of the entire dataset to fine-tune the model if you would like. There is a variable named _**doc_count**_ in the _**Data Prep**_ section. You can set this number to whatever you would like and it will only fine-tune the model based on the number of documents you set this variable to. The smaller this value the faster the model will fine-tune.


### Disclaimer

This notebook demos how you can fine-tune an LLM using transfer learning. Even though this notebook is using actual (U.K.) Supreme Court case documents you should not use this notebook for legal advise.
