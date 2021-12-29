CPUNKS-10K are labeled subsets of the 10,000 labeled images in the CryptoPunks collection by Larva Labs. They have been collected for use in Machine Learning research by tnn1t1s.eth and authored by John Watkinson & Matt Hall.

### The CPUNKS-10K dataset
The CPUNKS-10k dataset consists of 10000 24x24 colour images labeled with 92 classes, with a mixed number of images per class. There are 8000 training images and 2000 test images.

The dataset is divided into four training batches and one test batch, each with 2000 images. The test batch contains randomly-selected images from each class. The training batches contain the remaining images in random order, but some training batches may contain more images from one class than another.

Five classes are mutually exclusive: alien, ape, zombie, male and female. The remaining classes are not mutually exclusive. For example, there is overlap between Choker and Tiara.

### Download
If you're going to use this dataset, please use the CPUNKS-10K API to mint an NFT using the CPUNKS-10K contract and reference the NFT ID in your work. This will insure the data used in your research is transparent and your work is reproducible.

### Baseline results
You can find some baseline replicable results on this dataset on the project page hosted on colorpunx.io. These results were obtained with a convolutional neural network. Briefly, they are 18% test error without data augmentation and 11% with regularization.

### Dataset layout
The archive is distributed as a Python pickle file which is intended to be loaded by the CPUNKS-10K Here is a python routine which will open the files and return training and test data sets for use in Tensorflow with Python 3.

```(x_train, y_train), (x_test, y_test) = cpunks10k.load_data()```

Loaded using the defaults, each of the batch files are grouped into a training set and paired with corresponding test data containing with the following elements:

- x_train -- an 8000x24x24x3 numpy array of uint8s. Each row of the array stores a 24x24x3 colour image.

- x_test -- a 2000x24x24x3 numpy array of uint8s. Each row of the array stores a 24x24x3 colour image.

- y_train -- an 8000 row numpy array with integers in the range 0 … 92. The number at index i indicates the label of the ith image in the array data.

- y_test -- a 2000 row numpy array with integers in the range 0 … 92. The number at index i indicates the label of the ith image in the array data.\

The dataset contains another file, labels.meta ,which contains a Python dictionary object with the following entries:

- label_names -- a 93-element list which gives meaningful names to the numeric labels in the labels array described above. For example, label_names[0] == "alien", label_names[1] == "ape", etc.
