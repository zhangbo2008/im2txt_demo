这个项目挺牛逼


# im2txt_demo
im2txt + pretrained models + docker = easy tryout

This repo contains a copy of im2txt (https://github.com/tensorflow/models/tree/master/im2txt), 
a suitable docker image, pretrained models (https://github.com/tensorflow/models/issues/466) and 
some trivial shell scripts for convenience.

### Limitations:
* The command "git lfs pull" might respond with errors, due to the limited GitHub data quota:  
```                                                                                                                           
batch response: This repository is over its data quota. Purchase more data packs to restore access. 
```
  In this case you can 
  - wait until next month and hope you can perform "git lfs pull" before the data limit is reached OR
  - use the following links to the pretrained models and download them manually:
     https://drive.google.com/file/d/0Bw6m_66JSYLlRFVKQ2tGcUJaWjA/view
  - Copy the file model.ckpt-2000000 to the folder im2txt_pretrained. It should have a size of 143 mb.

The tensorflow version is fixed to an old one (0.12). Feel free to update and create a pull request! Thanks in Advance for your help!

### Getting started:

#### Install docker (skip if already installed)
https://docs.docker.com/engine/installation/

#### Install git lfs (skip if already installed)
https://help.github.com/articles/installing-git-large-file-storage/

#### Clone this repo and pull large files (pretrained models):
```
git clone https://github.com/siavash9000/im2txt_demo.git
cd im2txt_demo
git lfs pull
```

#### build docker image
```
cd im2txt_demo
make build
```

##### start container
```
make run
```

##### build run_inference (must be performed only once)
```
./build_inference.sh
```
##### get caption for image
```
./process_image.sh imgs/bikes.jpg
```
