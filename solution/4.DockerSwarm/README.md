

# Clone the ansible project
```
git clone https://github.com/devopsjourney1/ansible-swarm-playbook
```
*Note I had to change eth0 to eth1 in this, since ip address didn't match. 


# Verify docker swarm is setup.
```
sudo docker node ls
```

```
sudo docker stack ls
sudo docker ps
sudo docker-compose down
```
# Migrate your app
* Copy over 3.Docker folder to a new app folder

```
docker build -t devopsjourney1/myflaskimg:1 .
```
* modify docker-compose file to use image instead of build
```
docker stack deploy --compose-file docker-compose.yml myapp
```

```
docker stack ls
docker stack services myapp
docker service logs -f myapp_web
docker service ps myapp_web
docker service update --force myapp_web
docker service rm disml3ux1mye
docker stack deploy --compose-file docker-compose.yml myapp
curl node1:5000
docker service scale myapp_web=3
```

* change image to devopsjourney1/myflaskimg:1


docker service rm pky4n44z0790
docker stack deploy --compose-file docker-compose.yml myapp
docker service scale myapp_web=5
docker service ls
docker service ps myapp_web


docker stack rm myapp
docker network create --driver overlay --attachable --subnet 192.168.35.0/24 myoverlay
docker network ls

docker stack deploy --compose-file docker-compose.yml myapp
docker service inspect --format '{{json .Endpoint.VirtualIPs}}' myapp_web | jq '.'

docker container run --rm --network myapp_myoverlay tutum/dnsutils ping 10.0.12.6