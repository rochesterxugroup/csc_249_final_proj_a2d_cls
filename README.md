# csc_249_final_proj_a2d_cls
Actor-Action Multi-Label Classification

## Task description
Given an image, the goal of the task is to predict its actor-action classes. Since an image may have different actors and actions, the task is a multi-label and multi-class problem.

## Dataset
A2D dataset: it has 43 valid actor-action labels such as 'baby-climbing',
        'ball-climbing',
        'ball-crawling'. It consists of 4750 training images, 1209 validation images, and 1044 testing images.  

## Data Processing
We provided a dataloader for processing training or validation sets of A2D dataset for the actor-action classification task. It will read images and annotations in training or validation sets, do processing on images and original annotaions, then return processed images (224x224x3) and its class labels (43-D encoding). For the returned labels, it will have 44 dimension corresponding 43 different classes. If a encoded label is [1, 1, 0, ..., 0] (the first two elements are 1 and the others are 0), it means the image has the first and second classes ("adult-climbing" and "adult-crawling"). 
We provide another dataloader for processing testing set of A2D dataset, which will only return images without annotation labels. 

## Template
We provide a template for training, evaluation, and testing for submission. You can finish your code based on the template, and you are free to do any changes or even use your own code . 

### How to use? 
(1) You need to define your network in network.py

(2) use the defined network and define your loss function and optimizer in train.py.

(3) you can evaluate your model on validation set and generate results on testing set using eval_on_val.py and test_for_submission.py with loading your pre-trained model, respectively. You need to write model loading code.

## Evaluation Metrics
We use precision, recall, and F1-score to measure performance of trained models. The descriptions about the three metrics can be found in https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9.

## Submission 
We will evaluate your model on the testing set and the results should be a (NXnum_cls) array containing predictions saved as "results.pkl", where N (1044) refers to testing set size and num_cls (43) is the number of classes, and the elements are 0 or 1. You may follow the template: test.py to do testing. 

Please submit the results_netid.pkl (please change "netid" with your netid) and do not do data shuffle during testing.
