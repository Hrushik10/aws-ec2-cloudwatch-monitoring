# Amazon SNS Notification

## Purpose

Amazon Simple Notification Service (SNS) is used to send notifications when the CloudWatch alarm changes state.

## SNS Topic

The CloudWatch alarm is connected to an SNS topic for notification delivery.

## Notification Flow

EC2 Instance
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
Email Notification

## Alarm Integration

When the ErrorCount metric reaches the configured threshold, the CloudWatch alarm enters the ALARM state and publishes a notification to the configured SNS topic.

## Testing

The alarm was tested by generating an ERROR event from the EC2 instance. The CloudWatch alarm entered the ALARM state and the SNS notification mechanism was triggered.

## Purpose in the Project

SNS provides automated notification delivery so that administrators can be informed when an application or system error is detected.