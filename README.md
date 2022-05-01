## Dependencies

The code is written in Python (v3.7) and Pytorch (v1.3). We suggest the following environment:

* A Linux machine (Ubuntu) with GPU
* [Python (v3.7)](https://www.anaconda.com/download/)
* [Pytorch (v1.3)](https://pytorch.org/)
* [Pyrouge](https://pypi.org/project/pyrouge/)
* [pytorch-pretrained-bert](https://github.com/huggingface/transformers)

HINT: Notice that [pytorch-pretrained-bert](https://github.com/huggingface/transformers) may change their name and content during time. It is currently named as transformers.

To install [Python (v3.7)](https://www.anaconda.com/download/), run the command:
```
$ wget https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh
$ bash Anaconda3-2019.10-Linux-x86_64.sh
$ source ~/.bashrc
```

To install [PyTorch (v1.3)](https://pytorch.org/) and its dependencies, run the below command.
```
$ conda install pytorch torchvision cudatoolkit=10.1 -c pytorch
```

To install [pytorch-pretrained-bert](https://github.com/huggingface/transformers) and its dependencies, run the below command.
```
$ pip install spacy ftfy==4.4.3
$ python -m spacy download en
$ pip install pytorch-pretrained-bert
``` 

To install [Pyrouge](https://pypi.org/project/pyrouge/), run the command below. Pyrouge is a Python wrapper for the ROUGE toolkit, an automatic metric used for summary evaluation.  
```
$ pip install pyrouge
```

## I Want to Generate Summaries..

1. Clone this repo. Download this ZIP  file ([`others.zip`](http://i2u.world/kqsong/model/aaai2020_kaiqiang_2/others.zip)) containing trained model. Move the ZIP file to the working folder and uncompress.
    ```
    $ git clone git@github.com:KaiQiangSong/control-over-copying.git
    $ mv others.zip control-over-copying
    $ cd control-over-copying
    $ unzip others.zip
    $ rm others.zip
    $ mkdir log
    ```

2. Generating Summaries with our summarization model trained on selected dataset including: gigaword (default), newsroom.
    ```
    $ python run.py --do_test --inputFile data/test.txt
    ```
    Or if you want runing models other than that trained on gigaword:
    ```
    $ python run.py --do_test --dataset newsroom --inputFile data/test.txt
    ```
   
## I Want to Train the Model.
1. Training the Model with train files and validation files.
    ```
    $ python run.py --do_train --train_prefix data/train --valid_prefix data/valid
    ```

