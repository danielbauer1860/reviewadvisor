# ReviewAdvisor - Training and Evaluating Classification Models on Fake Reviews generated by Llama 2
Daniel Bauer, September 2023

Project in 'Natural Language Engineering 2'

Final Grade: 1,3

## Goals
The main goal of this project consists in the training and evaluation of classification models to detect fake reviews. Furthermore, I also test the validity of synthetically generated data in this context. For this, there are four key steps:

1. Fine-tune a state-of-the-art generator model to produce fake reviews. 
2. Fine-tune a state-of-the-art text classification model to distinguish between the reviews produced by the generator model and authentic ones. 
3. Compare the state-of-the-art classifier to previous approaches.
4. Evaluate the performance of the fine-tuned classifier on human-generated reviews.

## Structure

While this project is, as described in the paper, seperated into three major parts (training the generator, generating the synthetic data, training the classifiers), this repository contains three folders. First, the data-processing folder. This folder contains the necessary pre-processing necessary to handle both the HotelRec and Ott et al. dataset efficiently. Second, the generation folder. This contains both the fine-tuning of Llama 2 using QLoRA and the previously processed HotelRec sample dataset, as well as the actual generation of synthetic hotel reviews. Third, the classification folder, which consists in the fine-tuning/training of the described transformer models (DeBERTaV3, DistilBERT) and the NBSVM model, as well as the evaluation of said models on the Ott et al. dataset. Given this structure, I recommend that this repository be looked at in the following order:

1. The data-processing folder except for FakeReviewsPostProcessing (CreateRawDataset --> CreateGeneratorTrainingDataset --> GeneratorTrainingDatasetDescription; OttEtAlDataProcessing)
2. The generation folder (llama_2_fine_tuning --> generation_test --> generating_fake_dataset)
3. The FakeReviewsPostProcessing notebook in the data-processing folder
4. The classificaiton folder (deberta_fine_tuning --> distilbert_fine_tuning --> NBSVM --> roberta_base_openai_benchmark --> deberta_ott_et_al_scores --> distilbert_ott_et_al_scores)
