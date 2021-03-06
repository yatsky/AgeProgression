# PyTorch Implementation of Age Progression/Regression byConditional Adversarial Autoencoder

We developed a few applications based on Jupyter Notebook to test the system with the trained modelsinteractively.  As inputs, users can choose between already labeled images from UTKFace, to observe theresults with regard to parameters such as age, gender, and race. 

## Motivation

As participants of the 2018 Workshop in Machine Learning Applications for Computer Graphics (Cohen-Or, Fogel), we were exposed to many interesting ideas in the fields of artificial intelligence and computervision,  such  as  variational  autoencoders  (VAE)  and  deep  convolutional  generative  adversarial  networks(DCGAN).  In  the  latter  part  of  the  course,  we  were  asked  to  choose  a  paper  to  study  and  implement.Skimming through articles, we discovered an interesting paper from 2017 titledAge Progression/Regressionby Conditional Adversarial Autoencoder(Zhang, Song, et al.).  The article presented a method to performage modification on a given face image, with exciting utilization from recreational applications to assistthe searches on missing children.

## System Architecture

The system architecture was written in Python 3.7 and PyTorch 0.4.1, with attempts to keep the code ascompatible as possible with older versions of Python 3 and PyTorch.  Other external packages that wereused are NumPy, scikit-learn, OpenCV, imageio and Matplotlib.

![alt  ](https://github.com/mattans/AgeProgression/blob/master/architecture.PNG)

### Encoder

Encoder with 5 convolutional layers and a fully connected layer.  Viewing from left to right, faceimages of dimensions 128�128�3 are transformed into unlabeled Z vectors of size 50 in a latent space.
![alt ](https://github.com/mattans/AgeProgression/blob/master/encoder.png)

### Generator

Generator with 7 deconvolutional layers and a fully connected layer.  Viewing from left to right,labeled Z vectors of size 70 in a latent space are transformed into face images of dimensions 128�128�3.
![alt  ](https://github.com/mattans/AgeProgression/blob/master/Generator.png)

### Descriminators:

Discriminator on Z with 4 fully connected layers.
![alt  ](https://github.com/mattans/AgeProgression/blob/master/disZ.PNG)

Discriminator on images with 4 convolutional layers and 2 fully connected layers.
![alt  ](https://github.com/mattans/AgeProgression/blob/master/disImg.PNG)

## Training

For  training,  we  used  the  UTKFace  dataset,  which  was  collected  by  the  original  authors  of  the  articleand tested in their implementation.  UTKFace contains over 20,000 aligned and cropped face images withtheir appropriate labels.  We wrote a special utility, the UTKFace Labeler, which sorts the dataset imagesto separated folders based on the label, to match with PyTorch demands that classes are determined byfolders structure.

```
how to train
```

## Results

### VAE Results

Every two columns are the input image and the reconstructed image where the input image is on the left
![alt  ](https://github.com/mattans/AgeProgression/blob/master/VAEResults.PNG)

### Age Progression/ Regression

```
how to run progressing
```

The input image is on the left and afterwards there's the result for each age group, starting from youngest.
![alt  ](https://github.com/mattans/AgeProgression/blob/master/ageManifest.PNG)

### Merge between two different inputs

As an input there are two different inputs and the output is the possible merged child of the individuals

Inputs:

![alt  ](https://github.com/mattans/AgeProgression/blob/master/im1.PNG)
![alt  ](https://github.com/mattans/AgeProgression/blob/master/im2.PNG)

Output:

![alt  ](https://github.com/mattans/AgeProgression/blob/master/morf.PNG)

## Authors

Mattan Serry, Hila Balahsan and Dor Alt

## License

This project is licensed under the TAU License 

## Acknowledgments

* https://arxiv.org/abs/1702.08423
* https://github.com/wangxiao5791509/Age-Progression-Regression-by-CAAE
* Founded by AWS
