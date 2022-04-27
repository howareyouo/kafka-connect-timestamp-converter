# TimestampConverter for Kafka Connect
This is a rewrite of Apache Kafka® SMT `org.apache.kafka.connect.transforms.TimestampConverter`
> Docs on Confluent: https://docs.confluent.io/platform/current/connect/transforms/timestampconverter.html

It change the property `field` to `fields` , allows us handle multiple fields at once.

## Usages
Download the jar file from
[Release](https://github.com/howareyouo/kafka-connect-timestamp-converter/releases) page.
Drag it into you `plugin.path` folders (each of them).

## Example
Below configuration snippet shows how to use `TimestampConverter` to transform JSON formatted `timestamp` (represented as an `IOS-8601` string value, which comes from the Debezium JDBC source connector) into target type `Timestamp`(used by the following Confluent JDBC sink connector).

```
"transforms": "TimestampConverter",
"transforms.TimestampConverter.type": "com.github.howareyouo.kafka.connect.transforms.TimestampConverter$Value",
"transforms.TimestampConverter.format": "yyyy-MM-dd'T'HH:mm:ss'Z'"
"transforms.TimestampConverter.target.type": "Timestamp"
"transforms.TimestampConverter.fields": "created_at,updated_at,visited_at,..."

```
