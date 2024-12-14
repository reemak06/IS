INTRODUCTION

Android malware has continued to grow in volume and complexity posing significant threats to the security of mobile devices and the services they enable. This has prompted increas- ing interest in employing machine learning to improve Android malware detection. In this paper, we present a novel classi- fier fusion approach based on a multilevel architecture that enables effective combination of machine learning algorithms for improved accuracy. The framework (called DroidFusion), gener- ates a model by training base classifiers at a lower level and then applies a set of ranking-based algorithms on their predictive accu- racies at the higher level in order to derive a final classifier. The induced multilevel DroidFusion model can then be utilized as an improved accuracy predictor for Android malware detection. We present experimental results on four separate datasets to demon- strate the effectiveness of our proposed approach. Furthermore, we demonstrate that the DroidFusion method can also effec- tively enable the fusion of ensemble learning algorithms for improved accuracy. Finally, we show that the prediction accuracy of DroidFusion, despite only utilizing a computational approach in the higher level, can outperform stacked generalization, a well- known classifier fusion method that employs a meta-classifier approach in its higher level.

DATASET DETAILS

The Drebin Dataset is a widely used dataset for Android malware detection research, containing around 5,000 Android apps, labeled as either malicious or benign 215 features . Collected from various sources, the dataset spans multiple malware families, offering a comprehensive foundation for malware analysis.
This dataset includes various features indicative of an app’s behavior and potential threat level:

Permissions: Requested by each app (e.g., READ_SMS, INTERNET), which suggest the level of data access and possible user privacy risks.

API Calls: Specific calls that reveal app functions, potentially identifying malicious behavior like unauthorized data access or communication.

Intents: Actions and events that an app can handle (e.g., starting activities), providing clues about its purpose.

Hardware Components: Hardware requested by the app (e.g., CAMERA, LOCATION), which malicious apps may use to spy or gather data.

Network Addresses: URLs or IPs the app connects to, often relevant for identifying Command and Control (C&C) communication in malware.

The dataset is organized into separate text files for each feature category, such as permissions and API calls, with labels indicating each app’s classification. For analysis, these features can be combined and transformed into a machine learning-friendly format, allowing researchers to classify apps as malicious or benign based on behavior patterns.
![image](https://github.com/user-attachments/assets/be3481b3-9582-4b56-9093-4c2bc16474c5)

METHODOLOGY

Data Collection: Collect the Drebin dataset, which includes both malicious/malware and benign Android apps, along with their associated features like permissions, API calls, and network addresses.  
 
 Data Preprocessing: Clean and preprocess the data by converting categorical features, such as permissions and API calls, into binary representations (0 or 1) for each app.  

 Feature Selection: Identify and select the most relevant features, such as permissions and API calls, that contribute to distinguishing between malicious and benign apps.  
 
 Model Selection: Choose appropriate machine learning algorithms (e.g., Random Forest, SVM, Decision Trees) for classification based on their ability to handle high-dimensional data.  
 
 Model Training: Train the machine learning model on the prepared dataset, using a training set to learn the relationships between app features and their labels.  

Model Evaluation: Evaluate the model’s performance using test data, applying metrics like accuracy, precision, recall, and F1-score to measure its classification effectiveness.  

 Model Optimization: Fine-tune the model by adjusting hyperparameters and performing cross-validation to improve its performance and avoid overfitting.
![Uploading image.png…]()


