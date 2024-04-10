# MIE424 Final Project: Second Order Optimizer Comparison Experiments
By: Tracy Qian, Haris Rasul, Kailyn Yoon, Grant Lau


## About:
This is a comparative analysis of first-order and second-order methods in the context of training Convolutional-Neural-Networks for image classification. Our study benchmarks the popular stochastic gradient descent and ADAM methods against several second order methods based off Newton’s method such as the Broyden-Fletcher-Goldfarb-Shanno method (BFGS). The main objective is to investigate whether the more complex second-order methods lead to better performance metrics, such as accuracy and training speed compared to standardized first-order methods. We examine both performance and feasibility of these methods. We provide seperate implmentations in each jupyter notebook 


## Reference Papers:
1. Second Order Methods Implementations - T.-D. Guo, Y. Liu, and C.-Y. Han, “An overview of stochas- tic Quasi-Newton methods for large-scale machine learning - Journal of the Operations Research Society of China,” Springer, https://link.springer.com/article/10.1007/s40305-023-00453-9 (ac- cessed Mar. 18, 2024).

2. Conjugate Gradient Method - L. Lasdon, “The conjugate gradient method for optimal control problems,” IEEE, https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=arnumber=1098538

3. Second Order Method Integration into a Convolutional Neural Architecure - Chen , P. (2018) A comparison of second-order meth-
ods for - openreview, OpenReview.Net. Available at:
https://openreview.net/pdf?id=HJYoqzbC- (Accessed: 07 April
2024).

## Dependancies: 
1. pyTorch
2. V100 GPU - Google Colab subscription
3. Matplotlib
4. numpy
5. scikit-learn

## Methods Implemented:

First order methods implemented:
 - Stochastic Gradient Descent - BaselineFirstOrders.ipynb
 - ADAM - Kingma, D. and Ba, J. (2015) Adam: A method for stochastic op- timization. Available at: https://arxiv.org/pdf/1412.6980.pdf (Ac- cessed: 08 April 2024).

Second Order methods implemented:

- Limited Broyden-Fletcher - Goldfarb-Shanno (BFGS) algorithm : stochastic_lbfgs.ipynb

- Conjugate Gradient - Psudeo implentation for apprxomiatiobs using Newton Guassian Matrix logic inspired by: rosse, R. (2021) Chapter 4 second-order
optimization, cs.toronto.edu. Available at:
https://www.cs.toronto.edu/ rgrosse/courses/csc2541 2021/readings/L04 seco
(Accessed: 09 April 2024). - File Conjugate-Gradient.ipynb

- AdaHessian - ao, Z. et al. (2021) Adahessian: An adaptive second order optimizer for machine learning, arXiv.org. Available at: https://arxiv.org/abs/2006.00719 (Accessed: 08 April 2024). File - AdaHessian.ipynb


## Datasets

We utilized the Muffin vs Chihuahua dataset avaibale on Kaggle for binary classification for our CNN architecture:

https://www.kaggle.com/datasets/samuelcortinhas/muffin-vs-chihuahua-image-classification


## Key Files:

1. MIE424-Dataloader - load in the kaggle dataset and make dircetory with ones own drive ; this will produce the normalized image dataset required for training each model under each optimizer
2. (Excel File) Model-Data-424.xlsx - contains model data for each configuration ; you will need to run each type of model optimizer in the correct file dircetory to collect training loss, validation loss, test accuracy
3. In each file optimizer file:
(AdaHessian.ipynb, stochastic_lbfgs.ipynb, ...) upon training each model the training/validation loss and accuracy will be reported for each epoch as well total time duration trained. A model will be generated in each epoch in a self generated directory that stores model weights. You can use those model weight .npz files  to test against a train test split. The attempt to train BFGS can be found in the AdaHessian.ipynb file.


## How to Run:

- Download dataset form Kaggle
- Run dataloader to create dircetory on local device
- CNN module is initailized in each test file (AdaHessian.ipynb, Conjugate-Gradient.ipynb, etc..) 
- Table data in report gotten from report comes recording total time to train a model as well best model test accuracy
- call npz file weighst with cnn moudle within each test file on a train test split of your choice 

## Results
Table 1. Test accuracy performance on Chihuahua vs Muffin dataset:

<img width="319" alt="Screenshot 2024-04-09 at 2 00 53 PM" src="https://github.com/tracyqian0720/Second-Order-Optimizer/assets/66268214/f0e87b1f-ec1d-405b-b30d-52dac39b759f">


