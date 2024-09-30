---

# *Software for DWLR to Detect Anomaly Data*

## *Overview*
This project involves the development of a software application designed to detect anomalies in water level data collected from *Digital Water Level Recorders (DWLRs). The system monitors 14,000 DWLRs, generating high-frequency data which is analyzed using **LSTM (Long Short-Term Memory)* models. The application automatically identifies anomalies like missing data, abnormal readings, and sensor malfunctions (e.g., low battery) and sends real-time alerts to responsible officers and vendors for prompt action.

## *Project Structure*
- *Frontend (Web & Mobile)*: 
  - Built using *React* for web-based data monitoring and *Flutter* for mobile apps.
  - Both interfaces provide role-based access control for different user levels (officers, vendors).
  
- *Backend*: 
  - *Node.js* server manages API requests and handles business logic.
  - *MongoDB* stores water level data and anomaly detection results.
  
- *Anomaly Detection Model*:
  - Implemented using *TensorFlow* to train the LSTM model on historical data.
  - The model is deployed via *AWS SageMaker* for real-time anomaly detection.

- *Data Communication Protocols*:
  - Utilizes *LoRaWAN* and *NB-IoT* for reliable data transmission from remote DWLRs to the central system.
  
- *Cloud Infrastructure*:
  - Built on *AWS* services like *Lambda* (serverless computing) and *S3* (data storage) for scalability and cost-efficiency.

Model Description
LSTM (Long Short-Term Memory): The core of the anomaly detection system is an LSTM-based model implemented using TensorFlow. This model is ideal for detecting time-series anomalies in water level data.

Adaptive Thresholds: The anomaly detection system leverages individual threshold values for each DWLR, dynamically adjusted based on historical data and local climate conditions to improve detection accuracy.

Anomaly Types: The model flags issues such as missing data, abnormal water level readings, and low battery levels, providing real-time alerts and diagnostics.

## *Technology Stack*
- *Frontend*: React (Web), Flutter (Mobile)
- *Backend*: Node.js, Express.js
- *Database*: MongoDB
- *Machine Learning*: TensorFlow (LSTM Model)
- *Cloud Services*: AWS Lambda, AWS S3, AWS SageMaker
- *Data Communication Protocols*: LoRaWAN, NB-IoT
- *Monitoring & Notifications*: AWS CloudWatch, AWS SNS for real-time alerts

## *Key Features*
- *Real-time Anomaly Detection*: Detects missing data, abnormal water levels, and sensor faults using LSTM models.
- *Automated Alerts*: Sends real-time notifications via SMS, email, or mobile push notifications to officers and vendors when anomalies are detected.
- *Individual Sensor Thresholds*: Each DWLR has unique threshold values that are dynamically adjusted based on historical data and climate conditions.
- *Role-based Access Control (RBAC)*: Secure access for different users (officers, vendors) with specific roles and permissions.
- *Scalable Infrastructure*: Built on AWS for seamless scaling to support over 14,000 DWLRs by 2026.
- *Redundancy & Uptime*: Multiple data communication protocols (LoRaWAN, NB-IoT) ensure high availability and reliability.
- *Security*: Encryption, role-based access control, and regular system audits to ensure data security.

## *Deployment*
The project is deployed on *AWS Cloud* infrastructure:
- *Backend: Deployed using AWS **Lambda* for serverless computing, handling API requests efficiently.
- *Frontend: Hosted using AWS **S3* (for web) and *App Store/Google Play* for mobile app distribution.
- *Machine Learning Model: Hosted on **AWS SageMaker*, allowing continuous model updates and real-time anomaly detection.
- *Database: MongoDB hosted on **Atlas*, providing cloud-based scalable storage.

Deployment Process:
1. Push changes to *GitHub, triggering **CI/CD pipelines* using *GitHub Actions*.
2. *Backend* updates automatically deployed on AWS Lambda.
3. Frontend updates are deployed to AWS S3 and mobile app stores.
4. *AWS SageMaker* updates the LSTM model for real-time anomaly detection as new data is ingested.

---
