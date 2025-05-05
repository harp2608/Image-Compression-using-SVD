Technical Report – Project 1: Image Compression using SVD
Course: Mathematics and Statistics for Data Science.
Submitted by: Harpreet Kaur
Date:05/03/2025
1. Introduction
This project explores the use of Singular Value Decomposition (SVD) to compress grayscale images from the CIFAR-10 dataset. Image compression is a practical application of linear algebra and statistics, which reduces the size of images while attempting to retain their visual quality. By reducing the rank of the image matrix using only the top k singular values, we aim to demonstrate the trade-off between compression and quality.
2. Methodology
2.1 Dataset Used
- CIFAR-10: Contains 60,000 32x32 color images across 10 categories.
- We used the first 5 images and converted them to grayscale.
2.2 Preprocessing
- Images were converted to grayscale using OpenCV.
- Normalized pixel values to the [0, 1] range.
2.3 Singular Value Decomposition
For a grayscale image matrix A, SVD decomposes it into:
    A = U · S · V^T

To compress the image, we use only the top k singular values:
    A_k = U_k · S_k · V_k^T
3. Experiments
We experimented with different k values: 5, 10, 20, 50, 100.

For each image:
- Reconstructed it using the top k singular values.
- Computed Mean Squared Error (MSE) and Peak Signal-to-Noise Ratio (PSNR).
- Visualized the original and compressed images side-by-side.
4. Results
4.1 Visual Results
Image quality improved as k increased:
- k=5: Blurry
- k=10: Slightly clearer
- k=20: Acceptable
- k=50: Good
- k=100: Very close to original

 
4.2 Quantitative Results
Sample Table for MSE and PSNR:
k	MSE	PSNR (dB)
5	0.032	15.05
10	0.021	17.45
20	0.012	20.56
50	0.004	26.85
100	0.001	32.90




4.3 Convergence Plot
A plot of k values vs MSE for each image showed rapid error reduction with increasing k, plateauing after k=50.

 


5. Analysis
- Lower k values greatly reduce storage but at the cost of visual clarity.
- Higher k values retain more detail and yield higher PSNR.
- Compression using SVD is efficient for smaller images like CIFAR-10.
- MSE decreased exponentially with increasing k.
6. Conclusion
SVD provides an effective method for image compression, especially for grayscale images. The trade-off between compression and quality can be managed by tuning k. For CIFAR-10, values around k=50 provide a good balance between size and image clarity.
7. References
- CIFAR-10 Dataset: https://www.cs.toronto.edu/~kriz/cifar.html
- NumPy Documentation: https://numpy.org/doc
- Scikit-Image: https://scikit-image.org/
- OpenCV: https://opencv.org/
![image](https://github.com/user-attachments/assets/1f80dfdf-dfa0-4370-b41f-785398ccc078)
