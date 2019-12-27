# Domain adaptation Workshop

In this repository, we can find the implementations for the *Workshop* project of the *Machine Learning* course. Each folder contains the code corresponding to the section of the article with the same name.

### Structure of the repository
* CLASS CRITERION
  * *MNIST_pretrained.ipynb*: pretraining of the neural network using the MNIST dataset.
  * *MNSIT_pretrained_model.h5*: file that stores the pretrained model obtained in the above notebook.
  * *usps_dataset.h5*: file that stores the USPS dataset.
  * *Basic_Transfer_Learning.ipynb*: performs the transfer learning in two different ways (freezing and fine-tuning).

* STATISTIC CRITERION
  * *usps_dataset.h5*: file that stores the USPS dataset (same as above).
  * *Statistic_Criterion.ipynb*: performs the statistic criterion approach

* ADVERSIAL METHODS
  * *usps_dataset.h5*: file that stores the USPS dataset (same as above).
  * *ADDA.ipynb*: performs ADDA method with tricks to stabilize the training process and ensure convergence.
  * *Trained_models*: Contains the trained models from the ADDA method. For each model, there is a .json file containing the        model structure and a .h5 file containing the weights. This folder contains the following models:
      * *source_encoder*
      * *source_classifier*
      * *source_discriminant*
      * *target_encoder*
      * *target_classifier*
      * *target_discriminator*
    In order to run the model, the source_encoder model mmust be used for the source data and the target_classifier must be  
    used for the target data.
    
### Instructions to load a model

In order to load a trained model, one can use the following code:

\# load json and create model
json_file = open("example_model.json", 'r')
loaded_model_json = json_file.read()
json_file.close()
model = model_from_json(loaded_model_json)
\# load weights into new model
model.load_weights("example_model.h5")
    
      
