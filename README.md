# MNIST_ENMIST_TL

Transfer Learning **MNIST** with **EMNIST** features

Se entreno una red neuronal convolucional con la arquitectura mostrada [CNN](model.png) con la base de datos de EMNIST, se transfirieron posteriormente las características aprendidas de las capas convolucionales para posteriormente reentrenar las últimas capas (full conected layers) con la base de datos de [MNIST](http://yann.lecun.com/exdb/mnist/).<br />

I used Keras with tensorflow as backend, the EMNIST dataset is a .mat file downloaded from the [official repository of NIST]( https://www.nist.gov/itl/iad/image-group/emnist-dataset).<br />
Se usó keras con Tensorflow como backend en un ambiente virtual creado con Anaconda para lsa versiones  tensorflow=1.8.0 and keras=2.1.6. (estas versiones arreglan el problema de la compatibilidad de la lista de parámetros de las capas sofmax).<br/> 
Los datos vienen separadados previamente en un archivo .mat [download](https://www.nist.gov/itl/iad/image-group/emnist-dataset), donde el set de entrenamiento tiene la dirección "file['dataset'][0,0][0][0][0][0]", las categorías están en file['dataset'][0,0][0][0][0][1], y el set de testeo está en "file['dataset'][0,0][1][0][0][0]" con las categorías "file['dataset'][0,0][1][0][0][1]".<br />
Las categorías en el archivo son de 1 a 26, y como necesitan empezar por 0 se sustrajo 1 como se observa en el codigo.<br />
Los resultados obtenidos se observan en 
The results of the transfer learning were successful, obtaning **99.25%** of accuracy after 15 epoch of training and a batch size of 128. The accuracy obtained training the network with the MNIST data alone after 50 epoch is 99.67%, which is comparable to the results obtaining transfer learning here.
