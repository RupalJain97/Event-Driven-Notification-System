# Event-Driven-Notification-System

## Overview

The Event-Driven Notification System is a scalable and efficient system designed to handle real-time notifications using Apache Kafka. It enables multi-channel notifications such as email, SMS, and push notifications while ensuring high reliability and low latency. The system is built with Java, Spring Boot, and Kafka, leveraging advanced event-driven architecture principles to process and distribute notifications effectively.

## Features

1. Real-Time Event Streaming:
* Handles real-time ingestion of events via Kafka producers.
* Supports high-throughput event streams with minimal latency.
2. Multi-Channel Notification Support:
* Sends notifications via email, SMS, and push channels.
* Customizable notification formats based on user preferences.
3. Retry Mechanism for Failed Events:
* Implements a retry mechanism using Kafka’s dead-letter queues for handling failed events.
* Ensures 99.9% reliability in notification delivery.
4. Event Filtering and Processing:
* Filters and processes events dynamically using Kafka Streams.
* Supports conditional notification triggers based on event metadata.
5. Scalability and Fault Tolerance:
* Built on Apache Kafka’s distributed architecture to scale with increasing event volumes.
* Ensures fault tolerance through topic replication and consumer group balancing.

## Technologies Used

* Programming Language: Java
* Framework: Spring Boot
* Streaming Platform: Apache Kafka
* Database: PostgreSQL (optional for logging notifications)
* APIs: Twilio for SMS, JavaMail for email notifications
* Monitoring: Prometheus and Grafana for Kafka metrics
* Deployment: Docker

## Architecture

* Producers:
1. Event producers publish events (e.g., user actions, system updates) to Kafka topics.
* Consumers:
1. Kafka consumers process events from notification_events and route them to the appropriate notification channel (email, SMS, push).
* Dead-Letter Queue:
1. Failed events are pushed to a retry topic for reprocessing.
2. Consumers handle retry logic with exponential backoff.
* Multi-Channel Notification:
1. Channels (email, SMS, push) are determined dynamically based on event metadata.
2. Each channel has its own service for processing and delivery.
* Monitoring and Metrics:
1. Kafka performance is tracked with Prometheus and visualized in Grafana.
2. Consumer lag and event throughput metrics are monitored.
