# Autoencoder-Fashion-MNIST
This project is about doing dimension reduction from 2D with autoencoder algorithm.

Dataset: https://github.com/zalandoresearch/fashion-mnist

From that you can download: 
  - t10k-images-idx3-ubyte
  - t10k-labels-idx1-ubyte
  - train-images-idx3-ubyte
  - train-labels-idx1-ubyte

1. Data Preparation
    - Scaling data
    - Splitting data into 80% train, 10% test, 10% validation
2. Base Model
    ![image-3](https://github.com/user-attachments/assets/5c3701d8-3328-46e4-be25-ce6dfbb1589c)
3. Modified Model
     - Here’s a simple explanation of the code:
         - Encoder:
              - Takes the input image of size 28x28x1.
              - Two convolution layers are applied to extract features, each followed by max-pooling to reduce dimensions.
              - The result is flattened into a 1D vector.
              - A dropout layer is applied to prevent overfitting.
              - Finally, a dense layer reduces the feature size to 128, creating the encoded representation.

        - Decoder:
              - The encoded features are transformed back using a dense layer.
              - Reshaped into 7x7x128, followed by upsampling to increase the size.
              - Two Conv2DTranspose layers are used to reconstruct the image.
              - The final output is a reconstructed image with 1 channel and sigmoid activation to ensure pixel values are between 0 and 1.
