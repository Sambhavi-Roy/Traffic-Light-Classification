Working under the guidance of Professor Lelitha Devi Vanajakshi (Dept of Civil Eng, IIT Madras) to develop a model for the classification of traffic lights based on color from images of the LISA dataset which consists of over 43,000 frames and 113,888 annotated traffic lights.

Traffic light detection using machine learning (ML) is a crucial component of many modern intelligent transportation systems and autonomous driving technologies. The primary aim of this project is to use different algorithms to detect the traffic lights to equip vehicles or traffic management systems with the capability to identify and interpret traffic lights accurately and swiftly.

A large number of images have been edited (by changing brightness, contrast and applying filters) in order to improve variation of data and check efficiency of the algorithms.



STEPS INVOLVED:
1. Data Collection
2. Pre-processing
3. Feature Extraction
4. Training
5. Testing



MODELS USED:
1. Decision trees
2. Logistic Regression
3. Support Vector Machine



LIBRARIES USED:
1. OpenCV
2. NumPy
3. Pandas
4. Matplotlib
5. ScikitLearn



DATA COLLECTION:
1. Data cleaning is done by removing unnecessary columns, renaming columns, filtering rows based on target classes, extracting filenames, and removing duplicates.
2. A function finds the number of unique elements present in the target column and counts them. Next each target value is mapped to a specific colour.
3. This colour mapping is done by the color_map dictionary which is an inbuilt function which maps target classes to specific colors. For example, red, yellow, red for traffic lights. This is very useful in visualisations and exploratory data analysis.



PRE-PROCESSING:

A. Extracting Semaphore from images
  1. The region of interest ( Traffic light) is cropped out from the images using a set of processes.
  2. Relevant data is obtained from the dataframe such as the image path, filename, target class and the bounding box coordinates which specifies the location of the traffic lights.
  3. Overall, this function processes the input DataFrame to extract semaphore images based on the provided bounding box coordinates, converts their color format, and returns a list of cropped semaphore images for further analysis or processing.

B. Converting Image to grayscale
  1. A dictionary is created to store all the binarized images. The image is first resized and then converted to grayscale.
  2. The object pixels become white and background pixels become black using the cv2.THRESH_OTSU function.
  3. Binarization can be useful for further processing, such as feature extraction or segmentation, as it simplifies the image to only two intensity values (usually 0 and 255)

C. Converting Image to vector
  1. Vectorization refers to the process of converting data from its original form into a vector representation. In the context of image processing or computer vision, vectorization typically involves transforming an image into a one-dimensional array or vector where the pixels are being stored.
  2. This function essentially converts each binarized image into a vector representation and combines it with the annotation DataFrame.
  3. Vectorization allows for easy extraction of features from images. Each element of the vector corresponds to a specific pixel in the image, making it straightforward to extract features such as pixel intensity values, texture, or shape information. It also reduces computational memory as vectors have lower dimensionality  



DEFINING FEATURES AND TARGETS:
1. Principal Component Analysis is a popular technique used for dimensionality reduction of Feature Matrix and data visualization.
2. PCA aims to reduce the dimensionality of a dataset while preserving as much of the variance in the data as possible. By reducing the number of features (dimensions), PCA simplifies the dataset, making it easier to analyze and visualize, while still retaining the most important information.
3. Here PCA reduces the dimensionality of the data to two principal components to visualize it in a 2D space.
4. The plot helps to visually inspect the distribution of data in the reduced space and observe any patterns or separability between classes.



TRAINING RESULTS:

Decision trees achieved an accuracy of 99%, Logistic Regression and Support Vector Machine achieved an accuracy of 100% on day training dataset

Logistic Regression achieved an accuracy of 99% on training dataset, Decision Trees and Support Vector Machine achieved an accuracy of 98% on night training dataset



TESTING RESULTS

Decision trees achieved an accuracy of 91%, Logistic Regression 92% and Support Vector Machine achieved an accuracy of 90% on day testing dataset

Logistic Regression achieved an accuracy of 93% on training dataset, Decision Trees 91% and Support Vector Machine achieved an accuracy of 94% on night testing dataset



REFERENCES:
https://www.kaggle.com/code/marco22daniel/traffic-light-classification
