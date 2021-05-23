# CS6910-A3
The repository contains the code of assignment 3 of CS6910 Jan-May 2021 (Fundamentals of Deep Learning) course at IITM, written by *CS8B021* and *CS18B023*. 

Keras and Tensorflow v2.3 are used for training all the models. 

Description of all the files used for the assignment is given below:

**a3-wandb.ipynb**: This file contains the code for question 2 of the assignment. The code is used for building the training model and runs the WandB sweep over different hyperparameter configurations.

**a3-train.ipynb**: This file trains the best model with the hyperparameters found using the observations made from WandB sweep done by `a3-wandb.ipynb`. The best model is then loaded and the inference models, encoder and decoder, are built and stored. 

**best_model.h5**: The best sequence to sequence training model found using `a3-train.ipynb`.

**best_enc.h5**: The encoder model built using the weights of `best_model.h5`.

**best_dec.h5**: The decoder model built using the weights of `best_model.h5`.

**a3-inference.h5**: This file contains the code for question 4 of the assignment. The file loads the `best_enc.h5` (encoder) and `best_dec.h5 ` (decoder) models. It computes the accuracy using these models on test set. It contains the code for decoder beam search used for making predictions. It then stores the predictions made by the model in files `prediction_vanilla.csv` and `prediction_vanilla_beam.csv`. 

**prediction_vanilla.csv**: This file contains the prediction with highest score made using decoder beam search for the entire test set. It contains the original English word, the reference Hindi word and the predicted Hindi word with the highest score.

**prediction_vanilla_beam.csv**: This file contains the topmost 5 predictions made by decoder beam search with beam size of 5 for the entire test set. It contains the original English word, the reference Hindi word, and 5 topmost predictions made by beam search.

**a3-train-attention-wandb.ipynb**: This file contains the code for question 5(a) of the assignment. The file first builds a training model with attention using a custom attention layer. It then runs a WandB sweep over different hyperparameter configurations to find the hyperparameters for best validation accuracy.

**a3-train-attention.ipynb**: This file contains the code for remaining question 5 and question 6 of the assignment. It first builds the best training model with attention with the hyperparameters found using `a3-train-attention.ipynb`. The model is then trained. The inference models, encoder and decoder, are built using the weights of the trained model with attention. It then makes the prediction on the test set and stores them in files `prediction_attention.csv` and `predictio_attention_beam.csv`. It then computes the heatmaps using attention weights for several examples from the test set. It then contains the code for visualisation asked in question 6 of the assignment. It visualises the goal: when the model is decoding the i-th character, which is the input character it is looking at?

**prediction_attention.csv**: This file contains the prediction with highest score made using decoder (with attention) beam search for the entire test set. It contains the original English word, the reference Hindi word and the predicted Hindi word with the highest score.

**prediction_attention_beam.csv**: This file contains the topmost 5 predictions made by decoder (with attention) beam search with beam size of 5 for the entire test set. It contains the original English word, the reference Hindi word, and 5 topmost predictions made by beam search.

**compare_models.ipynb**: This file is used to compare the predictions made by the vanilla model and attention model for question 5(c) of the assignment.

**VesperLibre-Regular.ttf**: Font used for printing Hindi characters in plots.

**hi.translit.samples.dash.tsv**: The training (dash = train), validation (dash = dev), and test (dash = test) data used for training all the models.