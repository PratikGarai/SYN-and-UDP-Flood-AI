The codes here try to predict the occurence of UDP Flood or SYN attack based on
network activity of the system. The dataset is located here :
https://data.mendeley.com/datasets/mfnn9bh42m/1#file-ba7d3a46-1dc3-452e-aeac-26d909389b29


There are 2 types of detection activities :
	1. SYN Attack
	2. UDP Flood Attack

For each, there are 3 variants of the file :
	1. RNN Approach
	2. RNN without time row approach (to remove all possible bias)
	2. CNN Approach

For each of these, I only consider the columns :
	1. Timestamp (optional)
	2. SYN
	3. ACK
	4. RST
	5. Frame Length

I pass these feature to deep learning models to get the attack patterns analyzed 
and calculate accuracy based on correct detection rate.
The workflow :
	1. Slice the dataset based on attack and non attack times (provided with dataset).
	2. For training, select a contiguous sub-slice from these slices and pass 
	   appropriate class name adn feed it to the model.
	3. For validation, select a random sub-slice in a similar fashion and validate
	   the current state of the model.


The aim of all the files are to create a model that will receive the latest "n" logs
of the network and detect whether the network is under attack or not. Returns 1 or 0
accordingly got True or False.