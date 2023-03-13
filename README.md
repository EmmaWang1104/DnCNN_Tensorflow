<h1> DnCNN_Tensorflow</h1>
A complement of <a href="http://www4.comp.polyu.edu.hk/~cslzhang/paper/DnCNN.pdf" title="Download paper">Beyond a Gaussian Denoiser: Residual Learning of Deep CNN for Image Denoising</a> using Tenorflow 2023
 <br><br>
<h2>Requirements</h2>
Tensorflow 2.11<br>
numpy<br>
opencv<br>
Colab Pro+

<h2>Preprocessing</h2>
Before training the model, resize the image to 180*180.<br>
Adding noise to resized image using addnoise.ipynb. <br>
The processed noisy and clean images are located under data file.

<h2>Train</h2>
Runing main.ipynb, setup paraeters and save file path. <br>
Input noisy and clean train images to calculate loss for learning and training evaluation. <br>
Set: parser.add_argument('--phase', dest='phase', default='train', help='train or test') to train.

<h2>Test</h2>
Runing main.ipynb.
Input noisy test images and output denoised images.<br>
Calculate evaluation metrics to compare denoised with clean images.<br>
Set: parser.add_argument('--phase', dest='phase', default='train', help='train or test') to test.

<h2>Experiment</h2>
<h3>Project Baseline:</h3> Implement the known-level(25) Gaussian image denoising test. 

Dataset: <a href="https://www2.eecs.berkeley.edu/Research/Projects/CS/vision/bsds/" title="Download dataset">BSD500</a>, 400 for training; 100 for testing

Noise: Gaussian noise, sigma=25

Depth: 20; Epoch: 10; Batch Size: 128; No. of Batches: 800

Performance Metrics: Peak Signal-to-Noise Ratio(PSNR)
![9601678661769_ pic](https://user-images.githubusercontent.com/113215711/224578928-2de64358-9499-4dfd-a64f-c11e2397908a.jpg)

![9591678661699_ pic](https://user-images.githubusercontent.com/113215711/224578866-0e5c825d-0a5a-4af4-a3e5-811777b9ee00.jpg)

<h3>Enhancement Test - 1: Decrease the dataset</h3> 

Dataset: BSD500, 200 for training; 100 for testing

Noise: Gaussian noise, sigma=25

Depth: 20; Epoch: 10; batch size: 128

Performance Metrics: Peak Signal-to-Noise Ratio(PSNR)

![9611678662006_ pic](https://user-images.githubusercontent.com/113215711/224579137-d5ea8107-a054-4278-9341-65305efbc9b9.jpg)

![9621678662019_ pic](https://user-images.githubusercontent.com/113215711/224579157-63bc2b40-e8ee-4551-bcab-3e28454c6b41.jpg)

<h3>Enhancement Test - 2: Adjust Depth of DnCNN</h3>

Train data: Gaussian Noise

Test data: Gaussian Noise

Training parameters: 10 epochs, 800 baches, batch size 128,  learning rate 0.001

<img width="979" alt="Screenshot 2023-03-13 at 12 04 19 AM" src="https://user-images.githubusercontent.com/71403547/224630479-35644049-adec-4eda-974f-847441249a29.png">


![9641678662168_ pic](https://user-images.githubusercontent.com/113215711/224579294-a1f26617-a55e-44dd-a01d-3f6402939751.jpg)

<h3>Enhancement Test - 3: Assess Generalizability With Salt-and-Pepper Noise</h3> 

Add 1% salt and pepper noise to training images 

Experiment with different combinations of Gaussian and SP images for training and testing the model

Evaluate test results with PSNR (dB), MSE, SNR (db)

<img width="1113" alt="Screenshot 2023-03-13 at 12 05 41 AM" src="https://user-images.githubusercontent.com/71403547/224630698-0abe059a-8cf0-4487-b7bd-68cd090d573e.png">

<img width="1109" alt="Screenshot 2023-03-13 at 12 06 42 AM" src="https://user-images.githubusercontent.com/71403547/224630907-02cea8da-d7cc-4a47-a37e-5bd6bdcdf33e.png">

<img width="1110" alt="Screenshot 2023-03-13 at 12 06 29 AM" src="https://user-images.githubusercontent.com/71403547/224630862-78004210-cb0c-44e1-b3a1-5cc34d0e8a8a.png">





