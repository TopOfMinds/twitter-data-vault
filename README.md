# twitter-data-vault
A streaming data vault for Twitter data based on Apache Kafka

## Installation

Install [docker](https://www.docker.com/products/docker). On Mac, the Confluent platform doesn't work on Docker for Mac, the older [Docker Toolbox](https://www.docker.com/products/docker-toolbox) must be used.

Clone this repo:

    $ git clone git@github.com:TopOfMinds/twitter-data-vault.git
    $ cd twitter-data-vault

Create an app on [twitter](https://apps.twitter.com/) and fill in application name & description & web site and accept the developer agreement. Then copy ```kafka-connect-standalone/include/etc/kafka-connect/conf/twitter-source.properties.example``` to ```twitter-source.properties``` in the same directory and fill in the consumer key & secret and the access token & token secret.

Start all the services:

    $ docker-machine create --driver virtualbox --virtualbox-memory 6000 confluent
    $ docker-machine ssh confluent
    docker@confluent:~$ sudo -i
    root@confluent:~# sysctl -w vm.max_map_count=262144
    root@confluent:~# exit
    docker@confluent:~$ exit
    $ eval $(docker-machine env confluent)
    $ docker-compose up
