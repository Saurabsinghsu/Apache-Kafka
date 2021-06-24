## CLI References
* List Topics
  * bin/kafka-topics.sh --list --bootstrap-server localhost:9092
* Create Topic
  * bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --topic your_topic_name
* Create topic if not exist
  * bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --topic your_topic_name --if-not-exists
* Describe a topic 
  * bin/kafka-topics.sh --describe --bootstrap-server localhost:9092 --topic your_topic_name
* Delete a topic
  * bin/kafka-topics.sh --delete --bootstrap-server localhost:9092 --topic your_topic_name
* Create a topic with multiple partitions
  * bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --topic your_topic_name --partitions 2
* Alter a topic
  * bin/kafka-topics.sh --alter --bootstrap-server localhost:9092 --topic your_topic_name --partitions 2
* Send messages
  * bin/kafka-console-producer.sh --bootstrap-server localhost:9092 --topic demo 
  * After this command put some messages, and press Ctrl+C to halt the process
* Consume Messges
  * bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic demo --from-beginning
* Consume Messges by specifying a partition
  * bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic your_topic_name --from-beginning --partition 0
* Producer Sending Messges using Keys
  * bin/kafka-console-producer.sh --bootstrap-server localhost:9092 --topic your_topic_name --property parse.key=true --property key.separator=":"
  * Now after this you can send messages to respective topic, separated by ":" Eg. key1:SomeMessage Once done, press Ctrl+C
* Getting keys while consuming messages
  * bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic your_topic_name --from-beginning --partition 0 --property print.key=true --property key.separator="-"
* Adding Offset while consuming
  * bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic your_topic_name --partition 0 --property print.key=true --property key.separator="-" --offset 20
