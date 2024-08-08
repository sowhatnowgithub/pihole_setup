Pihole setup 

![Pihole](https://github.com/user-attachments/assets/bcc251de-9b3a-4dbf-aab5-44a0bee8be9b)


goto pihole docker git page via official Pihole website

or 

the following code is good

docker-compose file

```
# More info at https://github.com/pi-hole/docker-pi-hole/ and https://docs.pi-hole.net/
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:latest
    # For DHCP it is recommended to remove these ports and instead add: network_mode: "host"
    ports:
      - "53:53/tcp"
      - "53:53/udp"
      - "67:67/udp" # Only required if you are using Pi-hole as your DHCP server
      - "80:80/tcp"
    environment:
      TZ: 'America/Chicago'
      # WEBPASSWORD: 'set a secure password here or it will be random'
    # Volumes store your data between container upgrades
    volumes:
      - './etc-pihole:/etc/pihole'
      - './etc-dnsmasq.d:/etc/dnsmasq.d'
    #   https://github.com/pi-hole/docker-pi-hole#note-on-capabilities
    cap_add:
      - NET_ADMIN # Required if you are using Pi-hole as your DHCP server, else not needed
    restart: unless-stopped
```

copy the docker-compose

in cmd line 

```
mkdir pihole
cd pihole
touch docker-compose.yml
```
and then open the file , and copy contents into it
and in WEBPASSWORD='. ' remove and in singlequotes write down the password
and later type
```
docker-compose up -d
```
if docker error , check internet or type 

```
sudo apt install docker-compose -y
```
then download takes place 

then press
```
ifconfig 
```
Find ur ip address 

then go to firefox
type (inplace of ip enter ur ip address)
```
ip:80/admin
```
this will open pihole web view , enter password

happy learning :)
