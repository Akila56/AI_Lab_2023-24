# Ex.No: 10 Learning – Diabetes Prediction
### DATE:24-10-2024                                                                   
### REGISTER NUMBER : 212222060012
### AIM: 
To write a program to train the classifier for Diabetes Prediction.
###  Algorithm:
Start the program.<br>
Import required Python libraries, including NumPy, Pandas, Google Colab, Gradio, and various scikit-learn modules.<br>
Mount Google Drive using Google Colab's 'drive.mount()' method to access the data file located in Google Drive.<br>
Install the Gradio library using 'pip install gradio'.<br>
Load the diabetes dataset from a CSV file ('diabetes.csv') using Pandas.<br>
Separate the target variable ('Outcome') from the input features and Scale the input features using the StandardScaler from scikit-learn.<br>
Create a multi-layer perceptron (MLP) classifier model using scikit-learn's 'MLPClassifier'.<br>
Train the model using the training data (x_train and y_train).<br>
Define a function named 'diabetes' that takes input parameters for various features and Use the trained machine learning model to predict the outcome based on the input features.<br>
Create a Gradio interface using 'gr.Interface' and Specify the function to be used to make predictions based on user inputs.<br>
Launch the Gradio web application, enabling sharing, to allow users to input their data and get predictions regarding diabetes risk.<br>
Stop the program.<br>
### Program:
from google.colab import drive<br>
drive.mount('/content/gdrive')<br>
#import packages<br>
import numpy as np<br>
import pandas as pd<br>
pip install gradio<br>
pip install typing-extensions --upgrade<br>
!python --version<br>
 pip install --upgrade typing<br>
import gradio as gr<br>
import pandas as pd<br>
cd /content/gdrive/MyDrive/demo/gradio_project-main<br>
#get the data<br>
data = pd.read_csv('diabetes.csv')<br>
data.head()<br>
print(data.columns)<br>
x = data.drop(['Outcome'], axis=1)<br>
y = data['Outcome']<br>
print(x[:5])<br>
#split data<br>
from sklearn.model_selection import train_test_split<br>

x_train, x_test, y_train, y_test= train_test_split(x,y)<br>
#scale data<br>
from sklearn.preprocessing import StandardScaler<br>
scaler = StandardScaler()<br>
x_train_scaled = scaler.fit_transform(x_train)<br>
x_test_scaled = scaler.fit_transform(x_test)<br>
#instatiate model<br>
from sklearn.neural_network import MLPClassifier<br>
model = MLPClassifier(max_iter=1000, alpha=1)<br>
model.fit(x_train, y_train)<br>
print("Model Accuracy on training set:", model.score(x_train, y_train))<br>
print("Model Accuracy on Test Set:", model.score(x_test, y_test))<br>
print(data.columns)<br>
#create a function for gradio<br>
def diabetes(Pregnancies, Glucose, Blood_Pressure, SkinThickness, Insulin, BMI,Diabetes_Pedigree, Age):<br>
    x = np.array([Pregnancies,Glucose,Blood_Pressure,SkinThickness,Insulin,BMI,Diabetes_Pedigree,Age])<br>
    prediction = model.predict(x.reshape(1, -1))<br>
    if(prediction==0):<br>
      return "NO"<br>
    else:<br>
      return "YES"<br>
outputs = gr.Textbox()<br>
app = gr.Interface(fn=diabetes, inputs=['number','number','number','number','number','number','number','number'], outputs=outputs,description="Detection of Diabeties")<br>
app.launch(share=True)<br>

### Output:
![image](https://github.com/user-attachments/assets/f418b140-f6cd-4718-8811-da876021fb98)
![image](https://github.com/user-attachments/assets/a9b7659d-57f0-412e-a1d7-3d32912745df)
![image](https://github.com/user-attachments/assets/d42ef3a5-edef-4543-86ea-2833ba8ed398)
![image](https://github.com/user-attachments/assets/00b07bd4-d54e-4526-b305-94f4f8c9b4a4)
![image](https://github.com/user-attachments/assets/b4568349-5a9d-4280-96b5-0e933d36ffca)

### Result:
Thus the system was trained successfully and the prediction was carried out.
