# Auto_encoders

* **auto_encoders** are used to compress data, as well as image denoising.

* **auto_encoders** build a network that tries to generate it's input data, but with a narrow hidden layer that serves as a compressed representation of the input data.

![screenshot capture - 2017-06-17 - 03-00-16](https://user-images.githubusercontent.com/17912055/27245680-959fc01e-530a-11e7-8170-858c4753dfa4.png)

# Simple auto_encoders

* Start off by building a **simple autoencoder** to compress the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset. 

### Architecture

* Pass input data through an **encoder** that makes a compressed representation of the input .
* Then, this representation is passed through a **decoder** to reconstruct the input data.
* Generally the **encoder and decoder** will be built with neural networks, then trained on example data.

![screenshot capture - 2017-06-17 - 03-00-43](https://user-images.githubusercontent.com/17912055/27245913-b3a65608-530b-11e7-8d76-56fc074cc5f5.png)

* train an **autoencoder** with these images by flattening them into 784 length vectors. 
* The images from this dataset are already normalized such that the values are between 0 and 1.
* Let's start by building basically the **simplest autoencoder** with a single **ReLU hidden layer**.
* This layer will be used as the compressed representation. Then, the **encoder** is the input layer and the hidden layer.
* The **decoder** is the hidden layer and the output layer. 
* Since the images are normalized between 0 and 1, there is need to use a **sigmoid activation** on the output layer to get values matching the input.

# Results 

![mnist_examples](https://user-images.githubusercontent.com/17912055/27246025-814e225c-530c-11e7-8604-f9b0864f1baa.png)

 * `Top row    -   Original Images`
 * `Bottom row -   Reconstruted Images by **simple auto_encoders**`

 
 
 
 
 
 
 # Convolutional Autoencoder
 
 * Let's improve the  **autoencoder's** performance using **convolutional** layers.
 * Start off by building a **Convolutional autoencoder** to compress the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset.
 
 ### Architecture
 
 * The **encoder** part of the network will be a typical **convolutional pyramid**. 
 * Each **convolutional** layer will be followed by a **max-pooling** layer to reduce the dimensions of the layers. 
 * The **decoder** needs to convert from a narrow representation to a wide reconstructed image. 
 
 ![screenshot capture - 2017-06-17 - 03-02-52](https://user-images.githubusercontent.com/17912055/27246323-7a374db6-530e-11e7-93d5-c6b69582531d.png)

* So the decoder has these **Upsample** layers.
* Usually, we see **deconvolutional** layers used to increase the width and height of the layers. They work almost exactly the same as **convolutional layers** but in reverse.
* **Deconvolution** is often called **transpose convolution**.
* **Deconvolutional** layers can lead to artifacts in the final images, such as checkerboard patterns. This is due to overlap in the kernels which can be avoided by setting the stride and kernel size equal.



##### Do checkout [Distill article](http://distill.pub/2016/deconv-checkerboard/) from Augustus Odena, et al, the authors show that these checkerboard artifacts can be avoided by resizing the layers using nearest neighbor(**upsampling**) followed by a **convolutional** layer.



# Results 

![screenshot capture - 2017-06-17 - 03-48-11](https://user-images.githubusercontent.com/17912055/27246523-d34d4b2a-530f-11e7-91e0-786a32e2866c.png)

 * `Top row    -   Original Images`
 * `Bottom row -   Reconstruted Images by **simple auto_encoders**`

 


 
 
 ##### In practice, **autoencoders** aren't actually better at `compression` compared to typical methods like `JPEGs and MP3s`.But, they are being used for `noise reduction`.
 
 
 
 # Denoising
 
 * "autoencoders" can be used to **denoise** images quite successfully just by training the network on **noisy** images.
 *  Create the **noisy** images ourselves by adding **Gaussian noise** to the training images, then clipping the values to be between 0 and 1. 
 * Use the **noisy** images as input and the original, **clean** images as targets. 
 
 ###### Here's an example of the noisy images I generated and the denoised images.
 
 ![denoising](https://user-images.githubusercontent.com/17912055/27247144-da97cd52-5313-11e7-9a31-629dfe2546cb.png)



 
`



 

 
 
 



