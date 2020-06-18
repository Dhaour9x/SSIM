# Structural Similarity Index 

 SSIM is able to perceive the change in structural information of the image by comparing local regions of the image instead of globally.
-----------------------------------
To measure the structural similarity between ground truth map and generated SLAM algorithm maps, the SSIM index of Wang et al was used \cite{imagequality}. The SSIM index attempts to quantify the visible difference between a distorted image (generated SLAM algorithm map) and a reference image (ground truth map). This index is based on the Universal Image Quality (UIQ) index \cite{UIQ}.  The algorithm defines the structural information in an image that represents the structure of the objects in the scene regardless of the average luminance and contrast. The index is based on a combination of luminance, contrast and structure comparison. The comparisons are performed for local windows in the image, the total IQ is the average value of all these local windows. The SSIM is given as :


<a href="https://www.codecogs.com/eqnedit.php?latex=SSIM(x,y)=[l(x,y)]^\alpha&space;[c(x,y)]^\beta[s(x,y)]^\gamma" target="_blank"><img src="https://latex.codecogs.com/gif.latex?SSIM(x,y)=[l(x,y)]^\alpha&space;[c(x,y)]^\beta[s(x,y)]^\gamma" title="SSIM(x,y)=[l(x,y)]^\alpha [c(x,y)]^\beta[s(x,y)]^\gamma" /></a>
    


Whereby

<a href="https://www.codecogs.com/eqnedit.php?latex=l(x,y)=\frac{2\mu_x\mu_y&plus;C1}{\mu^2_x&plus;\mu^2_y&plus;C1}," target="_blank"><img src="https://latex.codecogs.com/gif.latex?l(x,y)=\frac{2\mu_x\mu_y&plus;C1}{\mu^2_x&plus;\mu^2_y&plus;C1}," title="l(x,y)=\frac{2\mu_x\mu_y+C1}{\mu^2_x+\mu^2_y+C1}," /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=c(x,y)=\frac{2\sigma_x\sigma_y&plus;C2}{\sigma^2_x&plus;\sigma^2_y&plus;C2}," target="_blank"><img src="https://latex.codecogs.com/gif.latex?c(x,y)=\frac{2\sigma_x\sigma_y&plus;C2}{\sigma^2_x&plus;\sigma^2_y&plus;C2}," title="c(x,y)=\frac{2\sigma_x\sigma_y+C2}{\sigma^2_x+\sigma^2_y+C2}," /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=s(x,y)=\frac{\sigma_x_y&space;&plus;&space;C3}{\sigma_x&space;&plus;&space;\sigma_y&plus;C3}," target="_blank"><img src="https://latex.codecogs.com/gif.latex?s(x,y)=\frac{\sigma_x_y&space;&plus;&space;C3}{\sigma_x&space;&plus;&space;\sigma_y&plus;C3}," title="s(x,y)=\frac{\sigma_x_y + C3}{\sigma_x + \sigma_y+C3}," /></a>

where $\mu$ is the average intensity for signals x and y and $\sigma$ is the standard deviation of signals x and y. $C_1$ and $C_2$ are constants defined as

<a href="https://www.codecogs.com/eqnedit.php?latex=C_1=(K_1L)^2," target="_blank"><img src="https://latex.codecogs.com/gif.latex?C_1=(K_1L)^2," title="C_1=(K_1L)^2," /></a>
<a href="https://www.codecogs.com/eqnedit.php?latex=C_2=(K_2L)^2," target="_blank"><img src="https://latex.codecogs.com/gif.latex?C_2=(K_2L)^2," title="C_2=(K_2L)^2," /></a>

where L is the dynamic range of the image and <a href="https://www.codecogs.com/eqnedit.php?latex=(K_1<<1)&space;and&space;(K_2<<1)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?(K_1<<1)&space;and&space;(K_2<<1)" title="(K_1<<1) and (K_2<<1)" /></a>. 




The system diagram of the proposed quality assurance system is shown in Figure \ref{SSIs} \cite{imagequality}. It is assumed that two non-negative image signals are matched (e.g., spatial spots extracted from each image). If one of the signals has optimal quality, the similarity measure can be used as a quantitative measure of the quality of the second signal. 

The system divides the task of similarity measurement into three comparisons: luminance, contrast and structure.


![SSIm](https://github.com/Dhaour9x/SSIM/blob/master/images/SSIMindex.PNG)

SSIM determines the actual difference in perception between two similar images. It cannot judge which of the two images is better: this must be deduced from knowing which is the original and which requires additional processing.



