Earn App
Unfortunately cannot use container, so go to root vps and exec:
wget -qO- https://brightdata.com/static/earnapp/install.sh > /tmp/earnapp.sh && sudo bash /tmp/earnapp.sh

Bitping
Special procedure for Bitping : you will need to enter manually credential to initialize (TODO : easiest way ?), in $HOME/CashFactory type : sudo docker run -it -v $HOME/CashFactory/data/bitping/:/root/.bitping bitping/bitping-node:latest

PacketStream
sudo docker stop watchtower; sudo docker rm watchtower; sudo docker rmi containrrr/watchtower; \
sudo docker stop psclient; sudo docker rm psclient; sudo docker rmi packetstream/psclient; \
sudo docker run -d --restart=always -e CID=6WwE \
--name psclient packetstream/psclient:latest && sudo docker run -d --restart=always \
--name watchtower -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower \
--cleanup --include-stopped --include-restarting --revive-stopped --interval 60 psclient