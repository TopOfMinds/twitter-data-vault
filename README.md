# twitter-data-vault
A streaming data vault for Twitter data based on Apache Kafka

## Installation

Install [docker](https://www.docker.com/products/docker). On Mac, the Confluent platform doesn't work on Docker for Mac, the older [Docker Toolbox](https://www.docker.com/products/docker-toolbox) must be used.

Clone this repo:

    $ git clone git@github.com:TopOfMinds/twitter-data-vault.git
    $ cd twitter-data-vault

Create an app on [twitter](https://apps.twitter.com/) and fill in application name & description & web site and accept the developer agreement. Then copy ```twitter-data-vault-setup/include/twitter-source.example.json``` to ```twitter-source.json``` in the same directory and fill in the consumer key & secret and the access token & token secret.

Start all the services:

    $ docker-machine create --driver virtualbox --virtualbox-memory 6000 confluent
    $ docker-machine ssh confluent
    docker@confluent:~$ sudo -i
    root@confluent:~# sysctl -w vm.max_map_count=262144
    root@confluent:~# exit
    docker@confluent:~$ exit
    $ eval $(docker-machine env confluent)
    $ docker-compose up

Figure out the ip address for the docker virtual machine:

    $ docker-machine ip confluent

e.g. ```192.168.99.100``` and point a browser to [Kibana](https://www.elastic.co/guide/en/kibana/current/index.html) e.g. http://192.168.99.100:5601/. The elasticsearch index is called ```twitter```and can be analyzed using Kibana.
