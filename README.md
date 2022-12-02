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

# Scanner
SCANNER_PORT=__YOUR__SCANNER_PORT__

# Parser
PARSER_PORT=__YOUR__PARSER_PORT__

# DB
SPRING_DATASOURCE_URL=jdbc:mariadb://INITCLOUD_DB:3306/__YOUR_DATABASE__
MARIADB_DATABASE=__YOUR_DATABASE__
MARIADB_USER=__YOUR_DATABASE_USER__
MARIADB_PASSWORD=__YOUR_DATABASE_PASSWORD__
MARIADB_ROOT=__YOUR_DATABASE_ROOT__
MARIADB_ROOT_PASSWORD=__YOUR_DATABASE_ROOT_PASSWORD__
DB_PORT=__YOUR_DATABASE_PORT__
DB_INNER_PORT=3306

```   
4. Run with Docker-compose
```bash
# pwd : ./initcloud-scanner
docker compose up -d
```