# Autoencoder-ATLAS

Here, you can find the codes for implementation of autoencoder-decoder network to compress the data from the ATLAS experiments from 4 to 3 variables, and reconstruct the same.

## Data

The ATLAS experiments being conducted at the Large Hadron Collider at CERN produce millions of proton-proton collision events. Here, I analyse the variables from the 4-momentum from the leading jets.
### The 4 Variables:
- transverse momentum pT 
- pseudorapidity η 
- azimuthal angle φ 
- energy E

## Environment
Python 3.5    

## Dependencies  
#### Python  
- numpy      
- pandas 
- matplotlib 
- sys 
- torch  
- fastai 
- scipy 
- seaborn
- corner 

  
The 4 variables standardised in the following way for the encoder-decoder network:
m = log(m+1)/1.8
pt = log(pt-1.3)/1.2
phi = phi/3
eta = eta/ 5



