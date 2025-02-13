# Anomaly-Detection-Auto-Encoder

In preparation for building a more full scale, regularized auto-encoder for motor anomaly detection (which you can find [here](https://github.com/conjeevaram/Anomaly-Detection-Auto-Encoder)), I wanted to experiment with implementing one from scratch. This model is trained to replicate images from the MNIST dataset, while gaining an inert understanding for what certain classes present themselves as (what does a 7 typically look like). Learn more below.

## What is an Auto-Encoder?
Auto-encoders are neural networks used for [unsupervised learning](https://cloud.google.com/discover/what-is-unsupervised-learning), particularly for dimensionality reduction and feature learning. It consists of two main components: an **encoder** and a **decoder**.

- **Encoder**: The encoder compresses the input data into a lower-dimensional representation (latent space). This compressed representation captures the most important features of the input data.
    
- **Decoder**: The decoder takes the compressed representation and attempts to reconstruct the original input data from it. The goal is to minimize the difference between the input data and the reconstructed output, as measured by some loss function "L". 
    

Auto-encoders are widely used in various applications, including anomaly detection, image denoising, and data compression. In the process of encoding and decoding, the model learns to  identify patterns and structures in the data.

## Implementation
This implementation uses a Jupyter notebook for easy prototyping.
### Stack
1. PyTorch, for model architecture, training loops and tensor operations
2. Matplotlib, for visualization

## Results
The model provided great training feedback:

![image](https://github.com/user-attachments/assets/ad688530-9157-4461-9a12-37a83586d0f3)


Below are some reconstruction results from MNIST:

![image](https://github.com/user-attachments/assets/c0358750-a181-41d1-a7e4-0052953d4178)


As mentioned above, auto-encoders can also be used to de-noise images. This is because their "understanding" of features in an image can help it infer where pixels should be. I wanted to experiment with this myself. I applied a strong Gaussian blur to MNIST images, and fed them into the model to be reconstructed. 

![image](https://github.com/user-attachments/assets/067c17b2-6547-4a27-bdcc-dfbe93d3a722)

As seen above, the model is typically able to slightly denoise the image, using its understanding of various digits to infer pixel values (brightness). This was really cool to see.
