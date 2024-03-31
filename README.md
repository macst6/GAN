# GAN
Building GAN
———————————


First thing is first we will start with the data as we are building a GAN to generate clothing so for this purpose we are using TFDS library of Tensor flow
And we are going to be using Fashion MNIST dataset 




So the next step is to build a generator . Generator is going to take random values and generate an image
We have sizes like 28 x 28 x 1


Now our generator will take 128 values and it will have the convolution layers and then the sampling layers and then we output an image with the same size


Then comes in play the discriminator which outputs the values as 0 and 1 0 means that its a fake image and 1 means that it is a real image 
Discriminator takes the images from the original dataset and it has bunch of convolution layers which tells us if the images are same or not 





Pre-processing steps
————————————
Three steps for making a data pipeline 
Map
Cache
Shuffle
Batch
Pre-fetch



Then we created an encoder which tries to create an encoder with the convolution layer 

Dense -> Leaky relu -> reshape -> upsampling -> convolution 2D -> Leaky relu -> upsampling -> convolution 2D -> Leaky relu -> convolution 2D ->Leaky relu -> convolution 2D 




Then we create a discriminator which takes an image and tell us if the image is real or fake and it does same thing using upsampling which extracts the feature of the image 



convolution 2D -> Leaky relu -> Dropout -> convolution 2D -> Leaky relu -> Dropout -> convolution 2D -> Leaky relu -> Dropout -> convolution 2D -> Leaky relu -> Dropout -> Flatten -> Dropout -> Dense

