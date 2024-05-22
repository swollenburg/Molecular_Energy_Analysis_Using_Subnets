# Molecular Energy Analysis Using Subnets
Sam Wollenburg

Date: Dec 11, 2023

### Subdirectories

- data/ : Contains the datasets used for training. (Should be created.)

### Files

- AN11-models_kfold.ipynb : Reads in the provided files in data and trains the selected model, there is an ANI1 recreation, a resdiual neural network, and a linear model. The notebook provides detailed documentationa and analysis.
- data.tar.gz : Compressed file containing data. Extraxt this file to the `./data` subdirectory.
- README.md : This file.

### Analysis
Detailed analysis can be found in the `ANI1-models_fkold.ipynb` notebook. A cooncluding summary is provided below.

Three models were tested: an ANI1 recreation, a Residual neural network, and a linear model. It was found that the recreated ANI1 model performed the best showing the lowest average training, validation, and evaluation loss. The other two models did not train as quickly given the same parameters (number of epochs, optimizer, learning rate, etc.). Something that can be seen in the plots produced for each model is that both the ResNet and the ANI model produced periodic spikes in the loss and validation curves that were not present with the linear model training. While the linear model did not train to a lower loss than the other models, it appears that it was more resiliant to fluctuations in the dataset that produced these large loss spikes. Adding the linear features back into the model through the skip connection caused more noise to be introduced into the baseline when compared to the recreated ANI model.

With more time it would be worth training all three of these models significantly longer to see if the peridoic loss spikes disipate, or if the linear model continues to learn past the other two models. It would also be interesting to see how the ResNet's noisy baseline evolves over time. Based on the profile of the training and validation curves alone, it seems that the linear regression had the most consistent training and perhaps these characteristics can be transfered to the other models. Further development of the ResNet's architecture should be explored to see if there is a manner where this can be done.