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
```


