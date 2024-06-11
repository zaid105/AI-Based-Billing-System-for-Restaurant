# AI-Based-Billing-System-for-Restaurant

# Client and Problem Statement:
Our client is a food chain owner with numerous restaurants in Hyderabad, Qatar, and Dubai. The client faced significant issues with billing leakages. Waiters were not reporting accurate bills at the billing counter. For example, if a customer consumed two biryanis and a full chicken, the waiter might report only one biryani and half a chicken, leading to revenue loss.
# Proposed Solution:
To address this problem, we developed an AI model capable of generating bills based on the items present on the table. The model, integrated with security cameras, focuses on a particular table, recognizing and updating the bill as waiters place or remove items. If a waiter brings a full biryani, the model adds it to the bill; similarly, it updates the bill when new items are placed on the table.
# Development Process:
## 1.	Data Collection:
•	Initially, we needed a large dataset of food images. We attempted to scrape images using Selenium and Beautiful Soup but encountered difficulties. <br><br>
•	We then used the "Bing Image Downloader" library to successfully gather the required images.
 
## 2.	Data Augmentation:
•	To prevent overfitting, we augmented the collected images. This step ensures that the model generalizes well and performs accurately on new, unseen data.
## 3.	Model Creation:
•	We started with a basic model that could predict a single food item from an image. The model performed well in these initial tests.
## 4.	Object Detection with YOLOv8:
•	The main task was to detect multiple food items in a single image or video. For this, we used YOLOv8 (You Only Look Once version 8), a state-of-the-art object detection algorithm.<br><br>
•	YOLO (You Only Look Once): YOLO is known for its speed and accuracy in detecting objects in real-time. It divides the image into a grid and predicts bounding boxes and probabilities for each grid cell, allowing it to detect multiple objects simultaneously.
## 5.	Data Annotation:
•	To train the YOLOv8 model, we needed annotated data with bounding boxes around each food item and corresponding labels.<br><br>
•	We used the "MakeSense" and “RoboFlow” annotation tools, which provides an easy-to-use interface for creating bounding boxes and labeling images.
## 6.	Model Training and Testing:
•	After preparing the annotated data, we trained the YOLOv8 model. we tested it with video input, and the model performed well, accurately detecting and classifying the food items.
## 7.	Billing Integration:
•	We extracted the detected items from each video frame and stored them in a list.<br><br>
•	Using Python, we wrote a script to generate bills based on detected items.<br> <br>For example, if the model detects a biryani, it adds the price of biryani (e.g., 400) to the bill. Similarly, it updates the bill for other items like pizza, etc.
Conclusion:
This AI-based billing system effectively addresses the client's problem by automating the billing process and ensuring accuracy. The integration of advanced object detection algorithms like YOLOv8 and tools like MakeSense for data annotation played a crucial role in the project's success.

