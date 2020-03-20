# Autoencoder-ATLAS

Here, you can find the codes for implementation of autoencoder-decoder network to compress the data from the ATLAS experiments from 4 to 3 variables, and reconstruct the same.

## Data

The ATLAS experiments being conducted at the Large Hadron Collider at CERN produce millions of proton-proton collision events. Here, I analyse the variables from the 4-momentum from the leading jets.
- [Training Set](https://github.com/asmitapoddar/Autoencoder-ATLAS/blob/master/processed_data/all_jets_train_4D_100_percent.pkl) 
- [Test Set](https://github.com/asmitapoddar/Autoencoder-ATLAS/blob/master/processed_data/all_jets_test_4D_100_percent.pkl)

### The 4 Variables:
- *pt*: transverse momentum pT 
- *eta*: pseudorapidity η 
- *phi*: azimuthal angle φ 
- *eta*: energy E

## Environment
Python 3.5    

## Dependencies  
- numpy      
- pandas 
- matplotlib 
- sys 
- torch  
- fastai 
- scipy 
- seaborn
- corner 

# Code
The Jupyter Notebook consist of the following modules:
1. Loading the dataset.  
The analysis has been done by preprocessing the data in two ways and comparing the results by auto-ecoding the two sets of preprocessed data. Preprocessing of the data:
- Normalisation of data: Subtract the mean of the training set and divide by standard deviation of the training set. 
- Custom standardisation of 4 variables  in the following way:
  - *m* = log(m+1)/1.8 
  - *pt* = log(pt-1.3)/1.2 
  - *phi* = phi/3 
  - *eta* = eta/ 5 
2. Histogram to visulaise the data distribution. 
3. Load model and data as tensors.  
The model used is the [AE_3D_200](https://github.com/asmitapoddar/Autoencoder-ATLAS/blob/master/nn_utils.py). 
4. Reconstruction of the data using the auto encoder-decoder model.  
The plots for both the reconstructed normalised as well as custom standardised data are shown.  
5. Reconstruction Loss (Residual).  
`Residual = (Predicted Data - Original Data) / Original Data`  
The plots for the residuals for both the reconstructed normalised as well as custom standardised data are shown.  
6. Correlations between the variables' residuals
The residual of *eta* and *pt* of the standardised data are nagatively correlated.

# Analysis  
The custom standardised variables have been reconstructed by the autoencoder-decoder model more faithfully than the normalised variables.  
- Sum of absolute errors between original data and reconstructed data (on custom standardising the data):
  - *m* : 4210.5957  
  - *pt* : 1573.8503 
  - *phi* : 415.63806
  - *eta* : 2487.95 
- Sum of absolute errors between original data and reconstructed data (on normalising the data):
  - *m* : 1.154388e+10  
  - *pt* : 180858.6   
  - *phi* : 26188.15  
  - *eta* : 62703.69  

## Usage

##### 1. Install dependencies
##### 2. Downloading the dataset.
Download the datasets and store them in a folder `processed_data`:
##### 2. Run the Jupyter notebook.
The various plots can be visualised in the Jupyter Notebook




