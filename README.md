# FBGAN-and-MVGG16
## FBGAN in Tensorflow
The structure of FBGAN
![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/Network%20Structure/FBGAN.png)

### Prerequisites
* Python 2.7
* Tensorflow-gpu 1.4.0
* Scipy
* Pillow
* Numpy

### ForwardGAN

The network D:

![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/Network%20Structure/D.png)

The network G:

![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/Network%20Structure/G.png)

#### Usage of ForwardGAN
To train a model with dataset train:

    $ cd ForwardGAN
    $ python main.py --dataset train --input_height=64 --output_height=64 --train

To test with an existing model:
    
    $ python main.py --dataset train --input_height=64 --output_height=64

Or, you can use your own dataset to train ForwardGAN. You need to put your dataset under the 'data' folder and run:

    $ python main.py --dataset DATASET_NAME --train
    $ python main.py --dataset DATASET_NAME
    $ # example
    $ python main.py --dataset=lung --input_fname_pattern="*.png" --train

If your dataset is located in a different root directory:

    $ python main.py --dataset DATASET_NAME --data_dir DATASET_ROOT_DIR --train
    $ python main.py --dataset DATASET_NAME --data_dir DATASET_ROOT_DIR
    $ # example
    $ python main.py --dataset=lung --data_dir ../datasets/ --input_fname_pattern="*.png" --train

#### Results of ForwardGAN
The output images of ForwardGAN will be saved under'../output/test/'. Here are some examples:

Benign samples:
![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/results/ForwardGAN0.png)

Malignant samples:
![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/results/ForwardGAN1.png)

### BackwardGAN

![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/Network%20Structure/BackwardGAN.png)

#### Usage of BackwardGAN

To train a model:

    $ python main.py --train=True

You can also use your dataset to train BackwardGAN. You need put the noise images under '../data/noise images/', and put clear images under '../data/clear images/'. Then train the model by:

    $ python main.py --train=True
    
To test an existing model, please put the test images under '../data/test/' and run:

    $ python main.py --train=False
    
#### Results of BackwardGAN
The output images of ForwardGAN will be saved under'../output/'. Here are some examples:

Benign samples:
![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/results/BackwardGAN0.png)

Malignant samples:
![Image text](https://github.com/BelleZhao/FBGAN-and-MVGG16/blob/master/results/BackwardGAN1.png)

