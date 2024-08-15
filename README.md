# Tổng hợp các command thường dùng.

OS đã setup thành công:
- Ubuntu: 20.04, 22.04, 24.04
- Debian: 10 (buster), 11 (bullseye)
- CentOS: 7

### UFW allow
```
ufw allow 80,443,3000,996,7946,4789,2377/tcp; ufw allow 7946,4789,2377/udp;
```

### Caprover setup
```
docker run -p 80:80 -p 443:443 -p 3000:3000 -e ACCEPTED_TERMS=true -v /var/run/docker.sock:/var/run/docker.sock -v /captain:/captain caprover/caprover
```
Đây chỉ là command setup cơ bản

### Caprover restart
```
docker service update captain-captain --force
```

### Caprover remove
Try this
```
docker service rm $(docker service ls -q)
```
then
```
docker swarm leave --force
```

### Check logs caprover

Lệnh cơ bản
```
docker service logs captain-captain --since 60m
```

Chekc my application's logs
```
docker service logs srv-captain--my-app --since 60m --follow
```
