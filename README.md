# TimestampConverter for Kafka Connect
This is a rewrite of Apache Kafka® SMT `org.apache.kafka.connect.transforms.TimestampConverter`(https://docs.confluent.io/platform/current/connect/transforms/timestampconverter.html).

It change the property `field` to `fields` , allows us handle multiple fields once.

## Example
This configuration snippet shows how to use `TimestampConverter` to transform a Unix epoch (represented as an `int64` value) into a formatted date string.

```
"transforms": "TimestampConverter",
"transforms.TimestampConverter.type": "org.apache.kafka.connect.transforms.TimestampConverter$Value",
"transforms.TimestampConverter.format": "yyyy-MM-dd'T'HH:mm:ss'Z'"
"transforms.TimestampConverter.target.type": "Timestamp"
"transforms.TimestampConverter.fields": "created_at,updated_at,visited_at"

```
