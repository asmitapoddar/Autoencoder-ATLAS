# Autoencoder-ATLAS

Here, you can find the codes for implementation of autoencoder-decoder network to compress the data from the ATLAS experiments from 4 to 3 variables, and reconstruct the same.

## Data

The ATLAS experiments being conducted at the Large Hadron Collider at CERN produce millions of proton-proton collision events. Here, I analyse the variables from the 4-momentum from the leading jets.
- [Training Set](https://github.com/asmitapoddar/Autoencoder-ATLAS/blob/master/processed_data/all_jets_train_4D_100_percent.pkl) 
- [Test Set](https://github.com/asmitapoddar/Autoencoder-ATLAS/blob/master/processed_data/all_jets_test_4D_100_percent.pkl)

### The 4 Variables:
- transverse momentum pT 
- pseudorapidity η 
- azimuthal angle φ 
- energy E

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
- Custom standardisation 4 variables  in the following way:
* m = log(m+1)/1.8 
* pt = log(pt-1.3)/1.2 
* phi = phi/3 
* eta = eta/ 5 
2. Histogram to visulaise the data distribution. 
3. Load model and data as tensors

## Usage

##### 1. Install dependencies
##### 2. Downloading the dataset.
Download the datasets and store them in a folder `processed_data`:
##### 2. Run the Jupyter notebook.
The various plots can be visualised in the Jupyter Notebook




