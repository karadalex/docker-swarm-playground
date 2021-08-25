Docker Swarm Playground
=======================

## Instructions

1. Create cluster `vagrant up`
2. Login to manager node `vagrant ssh manager1`
3. Initialise docker swarm `docker swarm init --advertise-addr 192.168.99.100`
4. Copy the output commande `docker swarm join ...` and run it at each worker
5. `vagrant ssh worker1`
6. `docker swarm join`
7. Go back to manager1 node and make sure 3 nodes appear connected in the cluster `docker node ls`

8. To install Portainer
```
vagrant ssh manager1
cd /vagrant
docker stack deploy -c portainer-agent-stack.yml portainer
```
then you can access the UI from [http://192.168.99.100:9000](http://192.168.99.100:9000)

9. To install Netdata
```
vagrant ssh manager1
cd /vagrant
docker stack deploy -c netdata.yml netdata
```
then you can access the UI from [http://192.168.99.100](http://192.168.99.100) for the overview of cluster monitoring
or visit one of [http://192.168.99.100:19999](http://192.168.99.100:19999), [http://192.168.99.101:19999](http://192.168.99.101:19999),
[http://192.168.99.102:19999](http://192.168.99.102:19999) to visit the Netdata dashboard for each node (with more details)

## Resources

1. Docker swarm tutorial [https://docs.docker.com/engine/swarm/swarm-tutorial/](https://docs.docker.com/engine/swarm/swarm-tutorial/)
2. [https://www.vagrantup.com/docs/multi-machine](https://www.vagrantup.com/docs/multi-machine)
3. Portainer [https://documentation.portainer.io/v2.0/deploy/ceinstallswarm/](https://documentation.portainer.io/v2.0/deploy/ceinstallswarm/)