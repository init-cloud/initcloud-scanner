<div align="center">    
 
# Initcloud Scanner

  
</div>
 
## Description   
Initcloud Scanner is Terraform Scanner & Visualizer for AWS, NCP.


## How to run
1. Install docker & docker-compose on your linux environment.  
    [install docker](https://docs.docker.com/engine/install/ubuntu/)  
    [install docker-compose](https://docs.docker.com/compose/install/linux/)
2. Cloning Initcloud Scanner
```bash
git clone https://github.com/init-cloud/initcloud-scanner.git
cd ./initcloud-scanner
```  
3. Set your Environment Variables. 
```bash
touch .env
```
```bash
# .env

# Dashboard
BOARD_PORT=5555 # YOUR BOARD PORT
REACT_APP_BASE_URL=http://initcloud_scanner:9090/api/v1

# Scanner
SCANNER_PORT=9090 # YOUR SCANNER PORT

# Parser
PARSER_PORT=9001 # YOUR PARSER PORT

# DB
SPRING_DATASOURCE_URL=jdbc:mariadb://initcloud_db:3306/initcloud
MARIADB_DATABASE=initcloud
MARIADB_USER=__YOUR_DATABASE_USER__
MARIADB_PASSWORD=__YOUR_DATABASE_PASSWORD__
MARIADB_ROOT=__YOUR_DATABASE_ROOT__
MARIADB_ROOT_PASSWORD=__YOUR_DATABASE_ROOT_PASSWORD__
DB_PORT=9002 #__YOUR_DATABASE_PORT__ 

```   
4. Run Docker-compose (API)
```bash
# pwd : ./initcloud-scanner
docker compose up -d
```

5. Run Docker (Dashboard)
```bash
docker inspect initcloud_scanner # For IPAddress
docker run -it -d --name initcloud_board -e TZ=Asia/Seoul -e REACT_APP_BASE_URL=${YOUR_INITCLOUD_SCANNER_IP} -p 5555:80 floodnut/initcloud_board
```
