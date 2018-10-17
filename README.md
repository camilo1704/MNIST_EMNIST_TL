# MNIST_ENMIST_TL

Transfer Learning **MNIST** with **EMNIST** features

I have trained a simple [CNN](model.png) with EMNIST data base, transfered the features learned to retrain the last full conected layers with 
the MNIST data.<br />

I used Keras with tensorflow as backend, the EMNIST dataset is a .mat file downloaded from the [official repository of NIST]( https://www.nist.gov/itl/iad/image-group/emnist-dataset).<br />
I used an enviroment set up with Anaconda of tensorflow=1.8.0 and keras=2.1.6. This enviroment handled the problems in the new paramenter lists of the softmax layer.<br />
The data comes split in the .mat file, where the training set has the address "file['dataset'][0,0][0][0][0][0]", the training labels file['dataset'][0,0][0][0][0][1], the test set "file['dataset'][0,0][1][0][0][0]" and its labels "file['dataset'][0,0][1][0][0][1]".<br />
The labels/categories come from 1 to 26, and they need to start from 0 so I subtracted 1 as you can see in the code.
<br />
Then I froze the weigth of the fetures learned (CNN) and then retrained changing the number of categories to 10 and using the [MNIST data](http://yann.lecun.com/exdb/mnist/).<br />
The results of the transfer learning were successful, obtaning **99.25%** of accuracy after 15 epoch of training and a batch size of 128. The accuracy obtained training the network with the MNIST data alone after 50 epoch is 99.67%, which is comparable to the results obtaining transfer learning here.
