# SQL-SERVER Monitor

This project creates a monitor stack for SQL-SERVER instances

## Stack Techs:
- Docker
- Grafana
- Telegraf
- InfluxDB


## Requirements

- Docker
- SQL-SERVER user configured for telegraf. 

## Configurations
### Telegraf

Telegraf is the data collector responsible for conecting into SQL-SERVER Instances and collect metrics, after that, it will persist that data into an InfluxDB instance.

Change the section "servers" into ./telegraf/telegraf.conf to match the connection string of the desired server instance to monitor.

### SQL-SERVER
Telegraf requires an user for querying data, you can see details in:
[https://github.com/influxdata/telegraf/tree/master/plugins/inputs/sqlserver](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/sqlserver)

### Grafana
Grafana is responsible for dashboarding data stored in InfluxDB

No steps are required here.

### InfluxDB
InfluxDB is a time-series database, it will store the data collected from the instances.

No steps required here.

# Executing the stack
After configurating the components, execute the following command:
	

    docker-compose up -d

In a few moments, it will be avaiable on localhost:3000 a grafana configurated instance, enjoy it ;)
