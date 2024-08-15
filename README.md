# Tổng hợp các command thường dùng.

# UFW allow
```
ufw allow 80,443,3000,996,7946,4789,2377/tcp; ufw allow 7946,4789,2377/udp;
```
# Caprover setup
```
docker run -p 80:80 -p 443:443 -p 3000:3000 -e ACCEPTED_TERMS=true -v /var/run/docker.sock:/var/run/docker.sock -v /captain:/captain caprover/caprover
```
Đây chỉ là command setup cơ bản
# Caprover remove
Try this
```
docker service rm $(docker service ls -q)
```
then
```
docker swarm leave --force
```
