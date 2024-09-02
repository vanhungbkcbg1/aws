# You can search and filter the log data coming into CloudWatch Logs by creating one or more metric filters. Metric filters define the terms and patterns to look for in log data as it is sent to CloudWatch Logs. CloudWatch Logs uses these metric filters to turn log data into numerical CloudWatch metrics that you can graph or set an alarm on

[how to create metric filter](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/CountingLogEventsExample.html)

# Push log to cloudwatch
 to push log to cloudwatch you can use aws cli to push, here is a example
 ````
 aws logs put-log-events \
  --log-group-name MyApp/access.log --log-stream-name TestStream1 \
  --log-events \
    timestamp=1394793518000,message="Test event 1" \
    timestamp=1394793518000,message="Test event 2" \
    timestamp=1394793528000,message="This message also contains an Error"
 ````