# PB_lite_edge_detection

Classical edge detection algorithms, including the Canny and Sobel baselines we will compare against, look for these intensity discontinuities. The more recent pb (probability of boundary) boundary detection algorithm significantly outperforms these classical methods by considering texture and color discontinuities in addition to intensity discontinuities. Qualitatively, much of this performance jump comes from the ability of the pb algorithm to suppress false positives that the classical methods produce in textured regions.

In this repository we develop a somplified version of probabiltiy based edge detection.
![image](https://user-images.githubusercontent.com/50541542/189540846-0bdbf33a-1685-47cc-9d94-5377d2076a76.png)

In the first step we generate filter banks like LM, Gabor and Derivative of Gaussian filter bank.

DOG
![image](https://user-images.githubusercontent.com/50541542/189540911-f401b79c-fde8-4569-a654-2f8ce055971e.png)
LM filter bank 
![image](https://user-images.githubusercontent.com/50541542/189540923-22ecf836-7b96-47fc-b76c-5544a0a8bc5f.png)
Gabor filter bank
![image](https://user-images.githubusercontent.com/50541542/189540929-e0a5099a-ef94-4a48-9348-1b2d7cf814ac.png)

The we create a texton, brightness and color gradient map.

![image](https://user-images.githubusercontent.com/50541542/189540761-b615b451-9e08-49af-8e7f-0d9d73dc848e.png)
![image](https://user-images.githubusercontent.com/50541542/189540763-2b6ac157-9fad-4eb7-b556-339be6d7891b.png)


Using the chi square distribution we calculate the difference in the gradients in order to obtain the sharpe changes in the image which is the edge in the image.
Then we assign the 0.5 weight to the Canny and Sobel edge images and averaging all the result we obtain the final edege result. 
![image](https://user-images.githubusercontent.com/50541542/189540771-bf94dc8d-a1d7-424c-8397-7a555cc7a60e.png)
![image](https://user-images.githubusercontent.com/50541542/189540777-a18cc9bc-165a-478e-b879-8aca571112a8.png)
