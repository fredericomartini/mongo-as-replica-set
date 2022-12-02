# Create a MongoDB cluster using ReplicaSet

## How to run:

```bash
./startReplicaSetEnvironment.sh
```

## How to connect:

### MongoDB compass

Add new connection to replicaSet:

```config
mongodb://mongo1:27017,mongo2:27018,mongo3:27019/DATABASE_NAME?readPreference=secondary&replicaSet=dbrs
```

### Commands to see which node is being used while performing read/write operations:

- Primary

```bash
docker exec -it mongo1 mongostat --uri='mongodb://127.0.0.1:27017' -i
```

- Secondary 1

```bash
docker exec -it mongo2 mongostat --uri='mongodb://127.0.0.1:27018' -i
```

- Secondary 2

```bash
docker exec -it mongo3 mongostat --uri='mongodb://127.0.0.1:27019' -i
```
