cd /mnt/c/Users/rlyst/Netology/11-microservices-04-scaling

docker compose up -d

docker compose down

docker compose up --build --remove-orphans

docker exec -it vm1 redis-cli -p 7001

CLUSTER INFO

CLUSTER NODES

docker exec -it vm1 redis-cli --cluster create \
172.20.0.11:7001 172.20.0.12:7003 172.20.0.13:7005 \
172.20.0.13:7006 172.20.0.11:7002 172.20.0.12:7004 \
--cluster-replicas 1

docker exec -it vm1 redis-cli -p 7001 cluster info