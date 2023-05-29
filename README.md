# Buisness Detection

In this GitHub repository, you can find all the necessary code of our implementation of a Business classification problem, where given an image, our model is able to classify it to one of the different propsed classes.

In the dataset we can find 28 different business categories, which can be for instance: Bakery, Book Store, Motel and many others. As well as 24,255 images in total. In order to be able to obtain the images used for this task, you can click http://isis-data.science.uva.nl/jvgemert/images.tar.gz to directly download them.

Examples of images:

![image](https://github.com/DCC-UAB/dlnn-project_ia-group_1/assets/126601914/f036ad7f-0202-4ebf-92bf-53be95648300)
![image](https://github.com/DCC-UAB/dlnn-project_ia-group_1/assets/126601914/c3c2739f-32e9-4d9e-b003-2f6c2755dfd0)

## Structure of the repo
#### Data folder:

The Data folder contains the output of the Preprocessing/Train_and_Test.py python file, which generates the Train.txt and Test.txt files. Each line in these files represents the name of a .jpg image and the corresponding business that appears in the image, encoded with a number.

The folder also includes the OCR output from the Preprocessing/OCR_eassyocr.py script. There are two OCR files available: one for the train set and another for the test set. Each line in these OCR files corresponds to an image in the dataset and contains the output generated by the EasyOCR tool.

It's important to note that the number of lines in the OCR files matches the number of lines in the Train and Test txt files, ensuring that the OCR output is aligned with the respective images in the dataset.

#### Models

Contains the model used in these project

#### Preprocessing

Folder that contains all the files needed to generate the contents of the Data folder.
## Getting Started

### Prerequesites:
In order to test the code you will need to install all the libraries in the .yml file. To make it easy you can create a new conda enviroment using the following comand
```
conda env create --file environment.yml
```
Apart from the .yml file we also are using the fasttext model to make the word embedding. We have installed fasttext from their github directly using:
```
git clone https://github.com/facebookresearch/fastText.git
cd fastText
sudo pip install .
```
### Executing the program


In the preprocessing folder the code to separate train and test sets and give the label the images correspond to is provdied. Additionaly we have added the OCR_easyocr.py file, where we compute the Optic Character Recognition (OCR) for each image. Given the image, it extracts the text inside it as well as some positional information of the characters, which improves the model significantly as some images may contain relevant information of what business they belong to.

Example of easy_OCR output where each line corresponds to an image, if there is a 0 means that in the image there is no text.

![image](https://github.com/DCC-UAB/dlnn-project_ia-group_1/assets/126601914/8b5dd7ab-92b4-44f9-a24c-b1f260b4be73)

****comentar lo del alexnet****


When the data is preprocessed, in the OUR_utils folder, you can find the file utils.py, where the train and test loader are made, as well as the selection of the criterion and optimizer used. All the different other parameters like learning rate or the number of classes are set in the main.py file.

Then in the train.py, you can find the training of the model, with its scheduler and ...

In the test.py, the accuracy of the model in the test set is obtained, and a file with the weights of our model is saved, to later be able to visualize some results.

In the main.py, the configuration is set as well as the train and test are being performed.

In the Visualizations.ipynb, we load the weights obtained for our model, and compute some visualizations of the test images, with the true and predicted classes.

Finally, we have decided to try the model on complete new images extracted and the results are shown in the file jajfnjfalb.py





