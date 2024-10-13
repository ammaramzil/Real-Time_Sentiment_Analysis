# Real-Time Sentiment Analysis
This project offers a solution for real-time analysis of data streams from Twitter, enabling the prediction of sentiments expressed in tweets. The results are displayed on an intuitive graphical interface. The technologies used include Apache Kafka Streams, Apache Spark, PySpark, NLTK, MongoDB, Streamlit, and Docker.

![Your paragraph text](https://github.com/user-attachments/assets/824f21de-a9f9-4c42-8656-402d9be2dce6)

## System Architecture

1. **Twitter Data Stream**: Tweets are collected from a CSV file named `twitter_validation.csv`, which serves as the input for the real-time processing system.

2. **Apache Kafka**: Kafka acts as the streaming platform for processing incoming tweets. The configuration includes:
   - **Broker, Topic, and Partition Setup**: Kafka is set up with the necessary brokers, topics, and partitions to efficiently manage the flow of Twitter data.
   - **Kafka Streams**: Kafka Streams are utilized to read data from the `twitter_validation.csv` file, ensuring that the latest tweets are processed in real time.

3. **Apache Spark Streaming**: Spark Streaming handles the processing of tweets from the Kafka topic. The processing pipeline consists of the following steps:
   - **Data Loading**: Data is loaded from the `twitter_training.csv` file using PySpark, which contains labeled data for training the model.
   - **Data Preprocessing**: The tweets are cleaned and prepared for analysis through tokenization, stop words removal, and lemmatization using the NLTK library to extract relevant features.
   - **Model Selection and Training**: A supervised machine learning model, specifically Logistic Regression, is trained on the preprocessed data from the labeled dataset.
   - **Model Evaluation and Saving**: After training, the model is evaluated to determine its performance. The best-performing model is saved for real-time sentiment prediction.
   - **Prediction**: The pre-trained model is applied to the incoming tweet data to predict sentiments.
   - **Result Storage**: Sentiment prediction results are stored in MongoDB for later retrieval and visualization.

4. **Integration with Web Application**: The results stored in MongoDB are visualized using Streamlit, creating an intuitive graphical interface that displays the sentiment analysis outcomes.

## Project Requirements

Here are the essential requirements for our project:

0. **Operating System**: We used **Windows 11** as the operating system for development.

1. **Docker Desktop**: This tool is needed to manage and run Docker containers on your local machine, which helps in setting up the environment for our application.

2. **Jupyter Notebook**: We use Jupyter Notebook for interactive computing in Python, allowing us to write and execute code in a user-friendly interface.

3. **Apache Spark 3.5.1**: This software is used for processing large-scale data efficiently.

4. **Python 3.11**: The main programming language used for developing our project.

5. **Kafka and Zookeeper Images**: These are necessary for building and running Apache Kafka clusters, which handle the streaming of Twitter data.

6. **Java 8 or Java 11**: Required by Kafka, Spark, and other components, Java is a programming language essential for our technology stack.

7. **MongoDB**: This database is used for storing and managing our data.

8. **Streamlit**: We use Streamlit to create interactive web applications, making it easier to visualize our results.

9. **Pandas**: This library helps with data manipulation and analysis, allowing us to work with structured data effectively.

10. **NLTK**: The Natural Language Toolkit (NLTK) is used for performing natural language processing tasks, such as analyzing text data.

11. **Regex**: Regular expressions (Regex) are used for pattern matching in text, helping us clean and process our data.

12. **NumPy**: This library is essential for numerical computing, providing support for large, multi-dimensional arrays and matrices.

13. **PySpark 3.5.1**: The Python API for Apache Spark, allowing us to use Spark functionalities within our Python code.

14. **PyMongo**: This library enables interaction with MongoDB from Python, making it easier to store and retrieve data.

15. **JSON**: JavaScript Object Notation (JSON) is used for data interchange, allowing us to easily transfer data between systems.

## How to Run the Project

Follow these steps to successfully run the project:

1. **Start Docker**: Open **Docker Desktop** and start the **Kafka** and **Zookeeper** containers. Make sure the required images are already available in Docker.

2. **Run Consumer and Producer**: Execute the **consumer** (`consumer.py`) and **producer** (`producer.py`) scripts. Ensure that data is being received correctly without any issues.

3. **Run the Data Streamer Notebook**: Open the `data_streamer_prediction.ipynb` file and run all cells. Wait for the last cell to finish executing before proceeding.

4. **Connect to MongoDB**: Launch **MongoDB Compass** and connect to your database. Make sure the database named **"tweet_db"** and the collections **"tweet_col"** and **"checkpoint"** already exist.

5. **Insert Data into MongoDB**: Open the `insert_2_mongodb.ipynb` file and execute the code inside it. Check **MongoDB Compass** to confirm that the data has been successfully received.

6. **Run the Dashboard**: Navigate to the **"Visualisation"** folder and run the **Dashboard** using the following command in your terminal: `streamlit run Dashboard.py`. This will open the web application in your browser.

## Dashboard with Streamlit:


