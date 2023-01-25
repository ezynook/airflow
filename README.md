## How to Deploy
```bash
git clone https://github.com/ezynook/airflow.git
cd /home
mkdir -p /home/airflow/dags
mkdir -p /home/airflow/mysqldata
mkdir -p /home/airflow/notebooks
```
```bash
docker run --name airflow -itd \
-p 8080:8080 -p 8888:8888 \
-v /home/airflow/dags:/root/airflow/dags \
-v /home/airflow/mysqldata:/var/lib/mysql \
-v /home/airflow/notebooks:/root/notebooks \
ezynook/airflow:latest
```
## How to use
```bash
http://ipaddress:8888 -> Jupyter
http://ipaddress:8080 -> Airflow
#---------------------------
Username: admin
Password: admin
```
## Trick
```bash
Develop directory: /home/airflow/notebooks
Production directory: /home/airflow/dags
MySQL Database: /home/airflow/mysqldata
```
## How to restart all services
```bash
#Execute to container
docker exec -ti airflow /bin/bash -c "bash /home/script/docker-entrypoint.sh"
```
