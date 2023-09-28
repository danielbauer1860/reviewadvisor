# reviewadvisor

While this project is, as described in the paper, seperated into three major parts (training the generator, generating the synthetic data, training the classifiers), this repository contains three folders. First, the data-processing folder. This folder contains the necessary pre-processing necessary to handle both the HotelRec and Ott et al. dataset efficiently. Second, the generation folder. This contains both the fine-tuning of Llama 2 using QLoRA and the previously processed HotelRec sample dataset, as well as the actual generation of synthetic hotel reviews. Third, the classification folder, which consists in the fine-tuning/training of the described transformer models (DeBERTaV3, DistilBERT) and the NBSVM model, as well as the evaluation of said models on the Ott et al. dataset. Given this structure, I recommend that this repository be looked at in the following order:

1. The data-processing folder except for FakeReviewsPostProcessing (CreateRawDataset --> CreateGeneratorTrainingDataset --> GeneratorTrainingDatasetDescription; OttEtAlDataProcessing)
2. The generation folder (llama_2_fine_tuning --> generation_test --> generating_fake_dataset)
3. The FakeReviewsPostProcessing notebook in the data-processing folder
4. The classificaiton folder (deberta_fine_tuning --> distilbert_fine_tuning --> NBSVM --> roberta_base_openai_benchmark --> deberta_ott_et_al_scores --> distilbert_ott_et_al_scores)
