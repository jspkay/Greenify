# Greenify (a.k.a. "Image colorizer")

## Why
This project was developed for a Machine Learning course attended at [Politecninco Di Torino](http://www.polito.it). The project consists in (you guessed it) image colorization.

## Who
It was developed by Salvatore Pappalardo (@jspkay) and Sofia Caterini.

## What
The developed neural networks aimed to colorize Black and white images. Unlike most of the methods out there, we used a mapping from BW space to RGB space. Other methods commonly use HSV representation for images. The network were completely trained on Google Colab using Keras API for tensorflow. In addition to the neural network, we implemented some useful custom metrics, in order to rate the performance of the network, and also a custom Perceptual Loss, to best train the model.
### Two models
We actually trained two different models:
- A classic U-net,
- and a Pix2Pix.

We aimed to use the U-Net as the generator in the Pix2Pix in addition with our custom Perceptual Loss, but there was no time and it wasn't going so great, but there are already the basis to accomplish such goal, so... Who knows? Maybe one day we'll do that!

## Results
You can see the complete report (in italian unluckily) in the file "Risultati.pdf". It is written based on a template, given by our professors, used in CVPR conferences.
Here we'll report some results.
### Pix2Pix
![Flower](https://github.com/jspkay/Greenify/blob/main/Risultati%20Pix2Pix/16.png "Flower example")
![Mountain](https://github.com/jspkay/Greenify/blob/main/Risultati%20Pix2Pix/5.png "Mountain example")
![Armadillo?](https://github.com/jspkay/Greenify/blob/main/Risultati%20Pix2Pix/17.png "Armadillo(?) example")
### U-Net
![Dog](https://github.com/jspkay/Greenify/blob/main/Risultati%20U-Net/16.png "Flower example")
![Mountain](https://github.com/jspkay/Greenify/blob/main/Risultati%20U-Net/5.png "Mountain example")
![Flower 2](https://github.com/jspkay/Greenify/blob/main/Risultati%20U-Net/17.png "Flower 2 example")

As written in the report, there's a lot of underfitting. That's due to multiple reasons:
- We were using Google Colab. Believe me, it's a mess if you are to use it as a professional tool. It's ok for little demonstrations, but train an entire neural network on it?! C'mon man, you want too much.
- The dataset had to be loaded from Google drive to Colab. This is also why we counldn't test our network with canonical datasets. There's a great lag dut to the transfer of files from Drive servers to Colab servers (that's a guess) and that's just unfeasible. To train just the first epoch we had to wait more than 1 hour!
- Images are big. Every image is 256x256! We had much problem because of this. Since the dataset is quite large for thi platform we couldn't use much other imges! Plus they had to be in double copy (both Black&White and RGB colored.)
But after all, the results are quite impressive, if you think what we went through!

## Notebooks
Here some notebooks we used to train the network:
- [U-net](https://colab.research.google.com/drive/1Oc13XBfAiW94X6ecEijdqkfVESdxNKTE?usp=sharing)
- [NoGan](https://colab.research.google.com/drive/177jTPdPgVU0cUOj-jn4bnxhtZpAyCctM?usp=sharing)
- [Pix2Pix](https://drive.google.com/file/d/1tvIKepWVUoh1mVL8Bwy-7LLkPMxKAgeD/view?usp=sharing)
Keep in mind that the reference notebooks are those in this repo. They are complete and working. Unluckily there isn't the actual notebook training of the U-net. It was lost because, during one training session, it grew so much in size (more than 2GB!) that it was completely unreadable from any software, it was just too much big... But in any case there are a lot of other trining we tried and all the used material is available on Google Drive at the following links:
- [Everthing we used - first account](https://drive.google.com/drive/folders/1o3Ql0-DUIy90nSV8Qgca9lZrbYpJw_yv?usp=sharing)
- [Everthing we used - second account](https://drive.google.com/drive/folders/1zYaWNVpt8_hKogIkX9GN-KjBmQaorkj1?usp=sharing)
