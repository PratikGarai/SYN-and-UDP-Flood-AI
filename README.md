# SYN-and-UDP-Flood-AI
## Detecting SYN and UDP Flood attacks using AI
The codes here try to predict the occurence of UDP Flood or SYN attack based on network activity of the system. 


## Dataset
The dataset is located here : <br />
https://data.mendeley.com/datasets/mfnn9bh42m/1#file-ba7d3a46-1dc3-452e-aeac-26d909389b29

## Task
There are 2 types of detection activities :
- SYN Attack
- UDP Flood Attack

## Files
For each, there are 3 variants of the file :
- RNN Approach
- RNN without time row approach (to remove all possible bias)
- CNN Approach


## Features
For each of these, I only consider the columns :

- Timestamp (optional)
- SYN
- ACK
- RST
- Frame Length

I pass these features to deep learning models to get the attack patterns analyzed 
and calculate accuracy based on correct detection rate. <br />


## The Strategy

- Slice the dataset based on attack and non attack times (provided with dataset).
- For training, select a contiguous sub-slice from these slices and pass 
	   appropriate class name adn feed it to the model.
- For validation, select a random sub-slice in a similar fashion and validate
	   the current state of the model.

<br />
The aim of all the files are to create a model that will receive the latest "n" logs
of the network and detect whether the network is under attack or not. Returns 1 or 0
for True or False.
