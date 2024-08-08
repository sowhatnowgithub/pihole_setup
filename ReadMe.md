pihole setup,
goto pihole docker git page via official Pihole website
copy the docker-compose
in cmd mkdir , cd to that dir ,
type 
```
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
sudo apt install docker-compose - y
```
then download takes place 
then press
```
ifconfig 
```
in eth0 find ip , 
then go to firefox
type 
```
ip:80/admin
```
this will open pihole web view , enter password
