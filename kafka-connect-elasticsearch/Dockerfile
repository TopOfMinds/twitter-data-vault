FROM confluentinc/cp-kafka-connect:3.1.0

COPY include/etc/confluent/docker/configure /etc/confluent/docker/configure
COPY include/etc/confluent/docker/launch /etc/confluent/docker/launch
COPY "include/etc/${COMPONENT}/conf" "/etc/${COMPONENT}/conf"
# COPY "include/etc/${COMPONENT}/jars" /usr/share/java/kafka/

# Hack: remove kafka-connect-hdfs as it contains httpcore-4.2.4.jar that
# shadows httpcore-4.4.3.jar that is needed for elasticsearch
# RUN rm -rf /usr/share/java/kafka-connect-hdfs/
