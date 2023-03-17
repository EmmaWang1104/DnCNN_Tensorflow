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




