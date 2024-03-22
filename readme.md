# Logging System

This is the repo for the logging system. PoC as of today

Starting everything should be fairly easy, after setting the required environment variables in a .env file (examples
shown in .env.sample) run the following command
```
docker-compose up
```
The process should go through a set up stage, where it generates certificates and other things, and afterwards
everything should start, if this is the first time ever starting the service and there are no volumes or previous data
available remember to run
```
docker cp elasticstack_docker-es01-1:/usr/share/elasticsearch/config/certs/ca/ca.crt YOUR/PATH/HERE/
```
Otherwise retrieve the cert from the secret manager with your API keys or through the UI (if possible).
You will need the ca.crt file for every single request \
\
Testing that everything is up and running should be easy, just run
```
curl --cacert /tmp/ca.crt -u USERNAME:PASSWORD https://ELASTIC_URL:ELASTIC_PORT
```
### TO-DO: How to connect apps to the service