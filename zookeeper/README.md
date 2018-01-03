# Zookeeper Notes

## Running locally 

```bash
docker-compose up
```

## Comands

### Checking status of zookeeper

```bash
winpty docker-compose exec zoo1 bin/zkServer.sh status
```

### Listing namespace

```bash
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 ls //
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 create //helloworld ""
#sequential
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 create -s //helloworld ""
#sequential & ephemeral
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 create -s -e //helloworld ""
#ephemeral
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 create -e //helloworld ""


winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 delete -s //helloworld
```

### Stat listing

```bash
winpty docker-compose exec zoo1 bin/zkCli.sh -server localhost:2181,zoo2:2181,zoo3:2181 stat //zookeeper
```
