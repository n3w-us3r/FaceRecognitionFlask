# Face Recognition Software

#  Installations

The following steps are tested for ubuntu 20.04 with a python version of 3.8

```
sudo apt update
sudo apt upgrade
sudo snap install cmake
```
Clone the project to any directory and open the terminal in that directory.
We will have to create some directories that will be essential for our storing images and features
```
mkdir data
mkdir features
```

I generally like to create a virtual environment for each of my projects so the next step is optional.

```
virtualenv -p /usr/bin/python3.8 venv
source venv/bin/activate
```
Now we will install all the pip packages required for running this applications. 
```
pip install -r reqirement.txt 
```
Then you can download the pre-trained model weights from [here](https://drive.google.com/file/d/1MegWliwXx2J-xHYX6iETl7hXUtLRk2sC/view?usp=sharing).
## Check your setup
After extracting the files, your directory should look like this.
```
.
├── app.py
├── config.py
├── data
├── features
├── logs
│   ├── func
│   ├── model
│   └── scalars
├── notebooks
│   ├── DatagGeneration.ipynb
│   ├── Real-time-prediction.ipynb
│   └── SiameseNetwork-TripletLoss.ipynb
├── README.md
├── reqirement.txt
├── siameseNetwork.py
├── static
│   ├── css
│   └── images
├── templates
│   ├── index.html
│   └── results.html
├── utils.py
```

## Running the browser-based tool

If you have the same set of files and folders in the directory then you can run the following command
```
python app.py
```
The flask app will start and you will be able to collect training data for any new person and generate features for that person and check the real-time recognition. You can add as many people as you want to. The images collected from this tool will be added to the data folder and the corresponding features generated will be stored in the features folder.

_**Note :** If you delete any person's images from the data folder, you need to delete the .pkl file inside the features folder as well. Also, the pickle file will be generated only when you hit submit images in the browser tool._


## References

1. O. M. Parkhi, A. Vedaldi, A. Zisserman, Deep Face Recognition, British Machine Vision Conference, 2015.
1. Q. Cao, L. Shen, W. Xie, O. M. Parkhi, A. Zisserman, VGGFace2: A dataset for recognising face across pose and age, International Conference on Automatic Face and Gesture Recognition, 2018.
3. F. Schroff, D. Kalenichenko, J. Philbin, FaceNet: A Unified Embedding for Face Recognition and Clustering, CVPR, 2015.
4. G. Koch, R. Zemel, R. Salakhutdinov, Siamese Neural Networks for One-shot Image Recognition, ICML deep learning workshop. Vol. 2. 2015.
5. [https://github.com/rcmalli/keras-vggface](https://github.com/rcmalli/keras-vggface)
6. [https://stanford.edu/~shervine/blog/keras-how-to-generate-data-on-the-fly](https://stanford.edu/~shervine/blog/keras-how-to-generate-data-on-the-fly)
7. [https://medium.com/datadriveninvestor/speed-up-your-image-training-on-google-colab-dc95ea1491cf](https://medium.com/datadriveninvestor/speed-up-your-image-training-on-google-colab-dc95ea1491cf)
