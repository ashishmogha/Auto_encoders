# Auto_encoders

* **auto_encoders** are used to compress data, as well as image denoising.

* **auto_encoders** build a network that tries to generate it's input data, but with a narrow hidden layer that serves as a compressed representation of the input data.

![screenshot capture - 2017-06-17 - 03-00-16](https://user-images.githubusercontent.com/17912055/27245680-959fc01e-530a-11e7-8170-858c4753dfa4.png)

# Simple auto_encoders

* Start off by building a simple **autoencoder** to compress the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset. With **autoencoders**.

* Pass input data through an **encoder** __that__ makes a compressed representation of the input. Then, this representation is passed through a decoder to reconstruct the input data. Generally the encoder and decoder will be built with neural networks, then trained on example data.

