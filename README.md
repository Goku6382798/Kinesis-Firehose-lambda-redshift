# Kinesis + Firehose + Lambda + Redshift | Real-Time Streaming Pipeline

This project demonstrates a **real-time data ingestion and analytics pipeline** using AWS services.  
Events are produced into **Amazon Kinesis**, processed by **AWS Lambda**, delivered through **Kinesis Firehose**, and stored in **Amazon Redshift** for analytics.  

---

## 📊 Architecture

![Architecture](Kinesis-Firehose-lambda-redshift/architecture/Screenshot%20from%202025-08-30%2014-52-09.png)

---

## 📂 Project Structure

Kinesis-Firehose-lambda-redshift

│

├── architecture

│ ├── real_time_lambda.pdf # Detailed documentation

│ └── Screenshot...png # Architecture diagram

│

├── data

│ └── events.csv # Sample events data

│

├── kinesis-events-producer.py # Python producer to send events to Kinesis

├── lambda.py # AWS Lambda function for event processing

└── redshift-create-table.sql # SQL script to create Redshift target table


---

## ⚙️ Tech Stack
- **Amazon Kinesis Data Streams** – Real-time event ingestion  
- **Amazon Kinesis Firehose** – Streaming delivery to Redshift  
- **AWS Lambda** – Real-time data transformation  
- **Amazon Redshift** – Data warehouse for analytics  
- **Python** – Event producer & Lambda code  

---

## 🚀 How to Run

1. **Set up Redshift**
   - Create a Redshift cluster.
   - Run `redshift-create-table.sql` to prepare the target table.

2. **Create Kinesis Stream**
   - Set up a Kinesis Data Stream for event ingestion.

3. **Deploy Lambda Function**
   - Upload `lambda.py` as the Lambda function code.
   - Configure the Lambda to trigger from the Kinesis stream.

4. **Configure Kinesis Firehose**
   - Create a Firehose delivery stream pointing to Redshift.
   - Set Lambda as a data transformation step if required.

5. **Run the Event Producer**
   - Use the Python producer to simulate streaming events:
     ```bash
     python3 kinesis-events-producer.py
     ```

6. **Query Data in Redshift**
   - Validate that events are landing in the Redshift table:
     ```sql
     SELECT * FROM events LIMIT 10;
     ```

---

## ✨ Highlights
- End-to-end **real-time streaming pipeline**  
- **Event-driven architecture** using AWS Kinesis & Lambda  
- **Seamless integration** with Redshift for analytics  
- Includes **sample events dataset** and **producer script** for testing  
