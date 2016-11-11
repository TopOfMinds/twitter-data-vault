FROM confluentinc/cp-kafka-connect:3.1.0

COPY include/etc/confluent/docker/configure /etc/confluent/docker/configure
COPY include/etc/confluent/docker/launch /etc/confluent/docker/launch
COPY "include/etc/${COMPONENT}/conf" "/etc/${COMPONENT}/conf"
COPY "include/etc/${COMPONENT}/jars" /usr/share/java/kafka/
