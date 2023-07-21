# Fingerprint_Matching
In this Project we build fingerprint matching system that leverages a Siamese network to achieve accurate and efficient Fingerprint identification. The system consists of three main stages: image preprocessing, feature extraction, and matching.
# Methodology
## Fingerprint Image Processing:
Fingerprint images were standardized to eliminate the problems of inconsistent clarity,
grayscale, and the number of channels between different fingerprint images. The steps were
as follows: Fingerprint images were standardized to eliminate the problems of inconsistent
clarity, grayscale, and the number of channels between different fingerprint images. The
steps were as follows:
1. Gray Scaling: Fingerprint images were converted from color to grayscale. This
conversion simplifies the image representation and reduces computational complexity, as it
focuses solely on the intensity values of pixels, which contain important fingerprint ridge
information.
2. Histogram Equalization: Histogram equalization was performed to enhance the
contrast and normalize the grayscale values of the fingerprint images. This step addressed
the issue of inconsistent clarity and variations in grayscale due to different imaging conditions or finger pressure during image acquisition.
To perform histogram equalization, the following steps were followed:

• Compute the histogram of the grayscale image, which represents the distribution of
pixel intensities.

• Calculate the cumulative distribution function (CDF) of the histogram.
• Normalize the CDF to the range of pixel intensities (usually 0 to 255) to obtain the
mapping function.

• Apply the mapping function to each pixel in the grayscale image to obtain the equalized image.

3. Low-pass filtering smoothing: The image noise generated during fingerprint collection was removed and the fingerprint images were smoothed. Fast Fourier transform
(FFT) was applied to the images. After the high-frequency part was eliminated, low-pass
filtered images were acquired through inverse Fourier transform.

#### Fingerprint Enhancement:
Additional image enhancement techniques
can be applied to further improve the quality of fingerprint images. These techniques may
include noise reduction, ridge thinning, ridge orientation estimation, and ridge frequency
estimation. Noise reduction techniques, such as Gaussian filtering or median filtering,
help remove unwanted noise while preserving important ridge information. Ridge thinning
algorithms aim to reduce the width of ridges to enhance their clarity and distinguishability.
Ridge orientation estimation techniques help determine the local ridge direction.

### Siamese Network  Architecture:

We trained the Siamese network with 63 different fingerprints using fingerprint
images of size 98 × 98. The fingerprint images of the same finger in the training set were
stored in the same folder. For the main network, VGG16 pre-trained weights were used for
subsequent network training. The training set comprised 66 different kinds of fingerprint
images belonging to different fingers, collected using an AS60x fingerprint collector. On
average, 10 images were sampled for each fingerprint in the training set. All images in the
training set underwent the fingerprint preprocessing steps described earlier. To increase the
adaptability of the training set, each fingerprint image was rotated five times, resulting in
a total of six images. Through this data augmentation technique, the number of images for
each fingerprint increased to an average of 60. Regarding the training of the comparative
network, two images of the same fingerprint kind were selected from the training set, and
the network output was calibrated to 1. Similarly, an image of a different fingerprint kind
was selected, and the output was calibrated to 0. This process was repeated with different
images from the training set. By training the network in this manner, when two fingerprint
images of the same finger were input, the network output was biased towards 1. Conversely,
when two fingerprint images of different fingers were input, the network output was biased
towards 0. 


![model](https://github.com/Nitheshkamath/Fingerprint_Matching/assets/112107488/1613b2c9-f969-45a1-842f-c2c579868888)







