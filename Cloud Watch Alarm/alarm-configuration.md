# CloudWatch Alarm

## Alarm Name

RWD-EC2-Alertss

## Metric

RWD/EC2 → ErrorCount

## Alarm Condition

ErrorCount >= 1

## Evaluation Period

The alarm evaluates the ErrorCount metric over the configured evaluation period.

## Alarm Action

The alarm is configured to trigger when the ERROR count reaches the defined threshold.

## Testing

An ERROR event was generated from the EC2 instance and successfully appeared in CloudWatch Logs. The ErrorCount metric was generated and the CloudWatch alarm successfully entered the ALARM state.

## Purpose

The alarm provides automated monitoring of EC2 log errors and helps identify problems without manually checking the logs continuously.