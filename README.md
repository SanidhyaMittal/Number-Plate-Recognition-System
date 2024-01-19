# Number-Plate-Recognition-System

## Workflow:

1. Video Capture and Frame Extraction:

  * Continuously capture frames from the video stream.
  * Publish each frame to a Kafka topic for further processing.

2. Number Plate Detection:

  * Consume frames from the Kafka topic.
  * Apply the number plate detection model to identify and extract regions containing number plates.
  * Publish the detected number plates along with relevant metadata to another Kafka topic.

3. Number Plate Recognition:

  * Consume the detected number plates from the Kafka topic.
  * Apply the OCR model to recognize characters on the number plates.
  * Publish the recognized characters along with additional metadata to another Kafka topic.

4. Data Storage:

  * Consume the recognized characters from the Kafka topic.
  * Store the results, including frame timestamps, detected number plates, recognized characters, and any other relevant information, in the PostgreSQL database.

5. Analytics and Reporting (dbt):

  * Use dbt to define transformations on the stored data in PostgreSQL.
  * Create dbt models to facilitate analytics, reporting, and any other downstream data processing requirements.
