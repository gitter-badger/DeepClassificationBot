**Classification Bot**
----------------------
Welcome to the Classification Bot codebase. Classification Bot is an attempt of simplifying the collection, extraction and preprocessing of data as well as providing an end to end pipeline for using them to train large deep neural networks.

The system is composed of scrapers, data_extractors, preprocessors, deep neural network models using Keras and an easy to use deployment module.

**To Install**
Make sure you have a GPU as the training is very compute intensive

1. Install CUDA_toolkit 7.5
2. Install cuDNN 4
3. Install theano, using `pip install theano`
4. Make sure you have Python 2.7.6 and virtualenv installed on your system
5. Install Python dependencies

```
$ virtualenv --python=python2 env
$ . env/bin/activate
$ pip install -r requirements.txt
```

3. Install theano, using `sudo pip install git+git://github.com/Theano/Theano.git`
4. Run `pip install -r requirements.txt`

**To download images**

1. Edit google_image_scraper.py using your favourite editor. In the main loop add classes in the "list" or use your own custom category extractor to find classes online, such as species of dogs.
types of fruits, names of gundams etc. Set the number of images to the number of images per class, we suggest a number between 200-1000.
2. Then run `python google_image_scraper.py` to get all of the required images.
3. Wait until images have been downloaded. You should be able to see them in folders under downloaded_images, in classes.

**To extract and preprocess data ready for training**

1. Once you have your data ready, run `python data.py extract_preprocess` to get all of your data ready and saved in .npy files.
2. In case you prefer to extract and preprocess data without saving them, and send them straight for training use `python train.py run`

**To train your network**

1. Once all of the above have been met then you are ready to train your network, by running `python train.py run -load=True` to load data from .npy files or
2. Without loading from .npy use `python train.py run`

**Deploying a model**

1. Once your training has finished and a good model has been trained then you can deploy your model.
2. To deploy a model on a single image use `python deploy.py predict_file -path path/to/image/file`
3. To deploy a model on a folder full of images use `python deploy predict_folder -path path/to/folder

Once deployed the model should return the top 3 predictions on each image in a dictionary form, e.g. {"image_01.txt": "class_1", "class_2", "class_4"}`

**Getting started**

Things to try:
