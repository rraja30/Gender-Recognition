# Gender-Recognition
Analysis of facial images using the dlib python library to implements accurate gender recognition and prediction using the implementation of numerous machine learning models. This research explores the effectiveness of machine learning models in gender recognition based on facial features. The study initially focused on the analysis of six facial features extracted from images in the dataset. Then non-facial features were incorporated, leading to improved model performance. The paper emphasizes the importance of supplementing facial features with relevant non-facial characteristics for enhanced gender recognition accuracy. Through a comprehensive comparative analysis of various models, including Linear Discriminant Analysis, Quadratic Discriminant Analysis, Support Vector Machine, Decision Tree, k-Nearest Neighbors, and Logistic Regression, the study provides insights into the strengths and limitations of different feature sets, contributing to the broader understanding of gender recognition in images

## Files
`AddFeatsAnalysis.ipynb` - Analysis of all ML algorithims with nine extracted features

`AttributesCoorelationMatrix.ipynb` - Analysis of the coorelation of all given features in the dataset

`LimFeatsAnalysis.ipynb` - Analysis of all ML algorithims with six extracted features

`PCA_40Feats.ipynb` - Principal Component Analysis enacted on all 40 attributes in given dataset

`MATH4210FinalReport_RajaGeigerAni.pdf` - Comprehensive Research Report

## Data Setup
The data used in this research, is from the [CelebA Dataset](https://www.kaggle.com/datasets/jessicali9530/celeba-dataset?resource=download-directory). The face images have a broad range of pose variations and background complexities, which guarantees a thorough representation of real-world scenarios. CelebFaces contains 202,599 face images, 10,177 unique identities, and comprehensive annotations with 5 landmark locations and 40 binary attribute annotations per image. The data set is also accompanied with a .csv file with information pertaining to a binary representation of the 40 features per image for all images in the data set. Follow the data splitting procedure used to unsure equal testing and training sets. (The provided data set has more female images than male images, thus a paritition must be implemented to ensure accurate results) 
## Dlib Library Configuration
Following the following [instructions](https://www.geeksforgeeks.org/how-to-install-dlib-library-for-python-in-windows-10/) to download the dlib library which will allow the extraction of features from images. 
## Feature Selection
From the 40 binary attribute annotations, we used the 'Male' column as our predictor for our data set. While we had this labeled information, the scope of our project aims to extract features from the images to conduct our analysis. Thus we only used the 'Male' attribute to label our data for supervised learning. Further more, it is important to note the values in the .csv file of attributes are represented only as binary values, to conduct a more in depth analysis, our feature extraction sought to represent features as numerical values or decimals. Thus when we conducted our own feature extraction, we incorporated floating point variables to represent the features of each image rather than as binary values.

We then sought to expand analysis further by identifying facial landmarks that play a role in determining the gender of facial images. We wanted to choose the best features to predict gender. Thus, we mapped a correlation matrix based on our given, labeled, attributes to understand which features could serve as the best predictors. Because we specifically wanted to analyze facial attributes, features related to hair color, if wearing accessories, if the image was blurry, attractiveness (subjective) or otherwise cosmetic aspects, were categorized to be added as additional features for further analysis later on. The six facial features chosen for analysis include eyebrow width, eyebrow length, eye length, lip size, face height, and round face. After the initial implementation was conducted on those six features, an additional three features pertaining to more cosmetic aspects we added for additional analysis (lipstick, makeup, and necktie presence represented as binary values).

## Feature Extraction
Geometric-based feature extraction involves the identification and extraction of different facial components or feature points that primarily represent the geometric structure of the face. This approach often relies on fixed points within the face image to derive essential information for gender classification. To extract these facial components, we incorporated a Python package called Dlib. It is a versatile open-source software library primarily written in C++ but with interfaces for Python as well. Dlib is designed to provide tools and algorithms for a variety of machine learning and computer vision tasks. It incorporates a face detector, a trained face key point detector, and a facial recognition model. The nine features include eyebrow length, eyebrow height, lip size, eye length, round face, face height, represented as floating point decimals, and lipstick, makeup, and necktie presence, represented as binary values.

## Machine Learning Algorithim Implementation
A variety of methods were chosen for analysis to provide a comprehensive understanding of the effectiveness of classification, dimensionality reduction, and clustering methods. 

## Conclusion
In conclusion, a variety of classification, clustering, and dimensionality reduction techniques were used in our thorough investigation of gender detection in face images, which produced insightful findings and useful performance indicators. We used PCA for dimensionality reduction, K-means for clustering, SVM, KNN, Decision Tree, Logistic Regression, QDA, and LDA for classification. 

Achieving high accuracy in gender detection proved challenging due to factors such as class imbalance, non-distinctiveness of numeric values in facial features, noisy data, and limitations in the Dlib package. These limitations in the Dlib package stem from face images having too dark or light of a background, or face being turned, causing the data point to be values of 0. The lack of reproducibility in certain scenarios and the inability of Dlib to identify faces in challenging conditions led to misclassifications, adding complexity to the task.

Our study emphasizes the significance of taking into account various methodologies when addressing gender detection in face images, despite these obstacles. In order to improve overall performance, future work should concentrate on reducing the limitations that have been found, investigating different feature selection techniques, fine-tuning model parameters, and possibly combining the advantages of various approaches.
