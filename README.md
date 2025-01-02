Unstructured Data Analysis Homework 4


In this assignment we look at the questions:
Is it possible to create a classifier which can differentiate well between paintings by Monet
and Picasso. If this is possible, can we gather any understanding of how this is being per-
formed within the classifier and with this information are we able to mislead the classifier to misclassify a painting?

The data used is a set of images of paintings (predominantly from Claude Monet and Pablo Picasso) from obtained https://www.wikiart.org/ (The zip file is available here, it was too large to put in this repository but is freely available and the images used are in the [presplit_data](./presplit_data) directory. 

We begin by running exploratory data analysis on our data to gather information about the count of the number paintings from Monet & Picasso and the styles of their paintings. This is done in [presplit_data](./code/data_EDA.ipynb). Also in this notebook we split the data into a training dateset and validation dataset (80%/20%). This is performed randomly and placed in the [presplit_data](./presplit_data) directory. 

Using this data we first chose to use the CNN model given in our lectures as a baseline, this is performed in [cnn_from_lecture](./code/cnn_from_lecture.ipynb)

For our main ResNet50 model, the code implementation and testing is performed in [resnet50_model_setup](./code/resnet50_model_setup.ipynb)

For the evasion attack, (which is also in [resnet50_model_setup](./code/resnet50_model_setup.ipynb)) to run the code from the Stylized Neural Painting code from https://github.com/jiupinjia/stylized-neural-painting , we ran the commands: 

python demo_prog.py --img_path ./test_images/pablo-picasso_woman-on-the-street-1901.jpg --canvas_color 'white' --max_m_strokes 4000 --max_divide 5 --renderer oilpaintbrush --renderer_checkpoint_dir checkpoints_G_oilpaintbrush --net_G zou-fusion-net    

python demo_prog.py --img_path ./test_images/pablo-picasso_portrait-of-minguell.png --canvas_color 'white' --max_m_strokes 4000 --max_divide 5 --renderer oilpaintbrush --renderer_checkpoint_dir checkpoints_G_oilpaintbrush --net_G zou-fusion-net   

The resultant files are [pablo-picasso_woman-on-the-street-1901_final.png](./presplit_data/test/pablo-picasso_woman-on-the-street-1901_final.png) and [pablo-picasso_portrait-of-minguell_final.png](./presplit_data/test/pablo-picasso_portrait-of-minguell_final.png). These can be found in  in [presplit_data/test](./presplit_data/test)

Some preliminary work was done on looking at the common subjects of the paintings of both artists, this was performed in [finding_painting_content.ipynb](./code/finding_painting_content.ipynb). This provided some funny outputs with the 4 most common subjects of Monet's paintings as [('fountain', 370), ('jigsaw_puzzle', 266), ('lakeside', 177), ('castle', 165)].

Images for the report are in [Images for Report](./Images%20for%20report)
