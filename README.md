# final-year-project
This project "Image In-Painting using Generative Adversarial Networks" has been conducted under the supervision of Prof. Sanjiban Sekhar Roy, Associate Professor, School of Computer Science and Engg,VIT.
Rajat Bhatia has carried out this project alongside with the support of Dr. Roy

README

General Model Configurations:

Option	Description
MODE	1: train, 2: test, 3: eval
MODEL	1: edge model, 2: inpaint model, 3: edge-inpaint model, 4: joint model
MASK	1: random block, 2: half, 3: external, 4: external + random block, 5: external + random block + half
EDGE	1: canny, 2: external
NMS	0: no non-max-suppression, 1: non-max-suppression on the external edges
SEED	random number generator seed
GPU	list of gpu ids, comma separated list e.g. [0,1]
DEBUG	0: no debug, 1: debugging mode
VERBOSE	0: no verbose, 1: output detailed statistics in the output console

Loading Train, Test and Validation Sets Configurations:

Option	Description
TRAIN_FLIST	text file containing training set files list
VAL_FLIST	text file containing validation set files list
TEST_FLIST	text file containing test set files list
TRAIN_EDGE_FLIST	text file containing training set external edges files list (only with EDGE=2)
VAL_EDGE_FLIST	text file containing validation set external edges files list (only with EDGE=2)
TEST_EDGE_FLIST	text file containing test set external edges files list (only with EDGE=2)
TRAIN_MASK_FLIST	text file containing training set masks files list (only with MASK=3, 4, 5)
VAL_MASK_FLIST	text file containing validation set masks files list (only with MASK=3, 4, 5)
TEST_MASK_FLIST	text file containing test set masks files list (only with MASK=3, 4, 5)

Training Mode Configurations:

Option	Default	Description
LR	0.0001	learning rate
D2G_LR	0.1	discriminator/generator learning rate ratio
BETA1	0.0	adam optimizer beta1
BETA2	0.9	adam optimizer beta2
BATCH_SIZE	8	input batch size
INPUT_SIZE	256	input image size for training. (0 for original size)
SIGMA	2	"standard deviation of the Gaussian filter used in Canny edge detector
(0: random, -1: no edge)"
MAX_ITERS	2E+06	maximum number of iterations to train the model
EDGE_THRESHOLD	0.5	edge detection threshold (0-1)
L1_LOSS_WEIGHT	1	l1 loss weight
FM_LOSS_WEIGHT	10	feature-matching loss weight
STYLE_LOSS_WEIGHT	1	style loss weight
CONTENT_LOSS_WEIGHT	1	perceptual loss weight
INPAINT_ADV_LOSS_WEIGHT	0.01	adversarial loss weight
GAN_LOSS	nsgan	nsgan: non-saturating gan, lsgan: least squares GAN, hinge: hinge loss GAN
GAN_POOL_SIZE	0	fake images pool size
SAVE_INTERVAL	1000	how many iterations to wait before saving model (0: never)
EVAL_INTERVAL	0	how many iterations to wait before evaluating the model (0: never)
LOG_INTERVAL	10	how many iterations to wait before logging training loss (0: never)
SAMPLE_INTERVAL	1000	how many iterations to wait before saving sample (0: never)
SAMPLE_SIZE	12	number of images to sample on each samling interval

I have taken help from github.com/knazeri/edge-connect for my project.
