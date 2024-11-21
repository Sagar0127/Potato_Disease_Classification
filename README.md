# Potato_Disease_Classification
Farmers every year face economic loss and crop waste due to various diseases in potato plants. We will use image classification using CNN and built a web app using which a farmer can take a picture and app will tell you if the plant has a disease or not.<br>
There are two common diseases :
- Early Blight - caused by fungus
- Late Blight - caused by certain microorganism

## Technology stack for this project will be :
Model Building: tensorflow, CNN, tf dataset<br>
Backend Server and ML Ops: tf serving, FastAPI<br>
Model Optimization: Tensorflow lite<br>
Frontend: React JS

## Implementation
→ Data Collection<br>
→ Model Building<br>
→ ML Ops (using TF Serving and backend using Fast API)<br>
→ Web App (React JS)

#### 1. Data Collection
This data contains three datasets that contains photos of potato leaves. The dataset contains Healthy potato leaves, Early Blight and Late Blight.
The dataset is taken from [kaggle](https://www.kaggle.com/datasets/arjuntejaswi/plant-village)
- Load data into tf.dataset

#### 2. Data Preprocessing
- Visualizing the data
- Splitting the data in training and testing data
- Data Augmentation

#### 3. Model Building
- Building and training a CNN Model
- Plotting training history on graph
- Making predictions/inferences on sample images
- Exporting model to a file on disk

#### 4. Fast API/ tfserving backend
Building a FastAPI web server and test it using postman application, then doing the same thing using tf serving + FastAPI

#### 5. Building a website
Using a prebuilt code for building a website which is made using HTML, CSS, javascript and the framework used here is ReactJS, we will integrate it to our CNN Model.

## Running the API
### Using FastAPI
1. Get inside ```api``` folder
```
cd api
```
2. Run the FastAPI Server using uvicorn
```
uvicorn main:app --reload --host 0.0.0.0
```
3. Your API is now running at ``` 0.0.0.0:8000 ```
### Using FastAPI & TF Serve
1. Get inside ```api``` folder<br>
```
cd api
```
2. Copy the ```models.config.example``` as ```models.config``` and update the paths in file.
3. Run the TF Serve (Update config file path below)
```
docker run -t --rm -p 8501:8501 -v C:/Code/potato-disease-classification:/potato-disease-classification tensorflow/serving --rest_api_port=8501 --model_config_file=/potato-disease-classification/models.config
```
4. Run the FastAPI Server using uvicorn For this you can directly run it from your main.py or main-tf-serving.py using pycharm run option (as shown in the video tutorial) OR you can run it from command prompt as shown below,
```
uvicorn main-tf-serving:app --reload --host 0.0.0.0
```
5. Your API is now running at ```0.0.0.0:8000```
### Running the Frontend
1. Get inside ```api``` folder
```
cd frontend
```
2. Copy the ```.env.example``` as ```.env``` and update ```REACT_APP_API_URL``` to API URL if needed.
3. Run the frontend
```
npm run start
```
## Setup for ReactJS
1. Install Nodejs (Setup instructions)
2. Install NPM (Setup instructions)
3. Install dependencies
```
cd frontend
npm install --from-lock-json
npm audit fix
```
4. Copy ```.env.example``` as ```.env```.
5. Change API url in ```.env```.

