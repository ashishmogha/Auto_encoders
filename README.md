# Auto_encoders

* **auto_encoders** are used to compress data, as well as image denoising.

* **auto_encoders** build a network that tries to generate it's input data, but with a narrow hidden layer that serves as a compressed representation of the input data.

![screenshot capture - 2017-06-17 - 03-00-16](https://user-images.githubusercontent.com/17912055/27245680-959fc01e-530a-11e7-8170-858c4753dfa4.png)

# Simple auto_encoders

* Start off by building a simple **autoencoder** to compress the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset. With **autoencoders**.

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
 
 
 
 * In practice, **autoencoders** aren't actually better at `compression` compared to typical methods like `JPEGs and MP3s`.
 * But, they are being used for `noise reduction`.
 
 
 # Convolutional Autoencoder
 
 * Let's improve the  **autoencoder's** performance using **convolutional** layers.
 
 



