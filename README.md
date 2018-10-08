# MNIST_ENMIST_TL

Transfer Learning **MNIST** with **EMNIST** features
I have trained a simple CNN with EMNIST data base, transfered the features learned to retrain the last full conected layers with 
the MNIST data.<br />
I used Keras with tensorflow as backend, the EMNIST dataset is a .mat file downloaded from the [official repository of NIST]( https://www.nist.gov/itl/iad/image-group/emnist-dataset).
The data comes split in the .mat file, where the training set has the address "file['dataset'][0,0][0][0][0][0]", the training labels file['dataset'][0,0][0][0][0][1], the test set "file['dataset'][0,0][1][0][0][0]" and its labels "file['dataset'][0,0][1][0][0][1]".
The labels/categories come from 1 to 26, and they need to start from 0 so I subtracted 1 as you can see in the code. 
