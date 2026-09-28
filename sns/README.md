# AWS EC2 CloudWatch Monitoring & Automated Alerting

## 📌 Project Overview

This project implements centralized monitoring and automated error alerting for an AWS EC2 instance using Amazon CloudWatch.

The solution collects system logs from an EC2 instance, sends them to CloudWatch Logs, detects ERROR messages using a metric filter, generates an ErrorCount metric, and triggers a CloudWatch alarm when the defined threshold is reached.

## 🏗️ Architecture

EC2 Instance
       ↓
CloudWatch Agent
       ↓
CloudWatch Logs
       ↓
Metric Filter
       ↓
ErrorCount Metric
       ↓
CloudWatch Alarm
       ↓
Amazon SNS
       ↓
Notification

## 🛠️ AWS Services & Tools

- Amazon EC2
- Amazon CloudWatch
- CloudWatch Agent
- CloudWatch Logs
- CloudWatch Metric Filters
- CloudWatch Alarms
- Amazon SNS
- Linux / Ubuntu
- SSH

## ⚙️ Implementation

### 1. EC2 Instance

Created and connected to an Ubuntu EC2 instance using SSH.

### 2. CloudWatch Agent

Installed and configured the Amazon CloudWatch Agent to collect `/var/log/syslog`.

### 3. CloudWatch Logs

Configured the agent to send system logs to:

`/aws/ec2/RWD-Machine-Logs`

### 4. Metric Filter

Created a metric filter to detect log messages containing:

`ERROR`

The filter generates an `ErrorCount` metric.

### 5. CloudWatch Alarm

Created the alarm:

`RWD-EC2-Alertss`

Alarm condition:

`ErrorCount >= 1`

The alarm changes to the ALARM state when an ERROR event is detected.

### 6. Testing

Generated test error messages from the EC2 instance and verified that the messages appeared in CloudWatch Logs.

The ErrorCount metric increased and the CloudWatch alarm successfully entered the ALARM state.

## 🔄 Monitoring Workflow

1. EC2 generates system/application logs.
2. CloudWatch Agent collects the logs.
3. CloudWatch Logs stores the events.
4. Metric Filter searches for ERROR events.
5. ErrorCount metric records detected errors.
6. CloudWatch Alarm evaluates the metric.
7. SNS can send an alert when the threshold is exceeded.

## 🎯 Project Objectives

- Monitor EC2 system logs centrally.
- Automatically detect error events.
- Convert log events into measurable metrics.
- Trigger alarms based on defined thresholds.
- Enable automated notification through SNS.
- Demonstrate AWS monitoring and observability concepts.

## 📚 Skills Demonstrated

- AWS CloudWatch
- EC2 Monitoring
- Linux
- CloudWatch Agent
- Log Management
- Metric Filters
- CloudWatch Alarms
- SNS
- AWS Troubleshooting
- DevOps Monitoring & Observability

## 👨‍💻 Project Author

Hrushik Reddy