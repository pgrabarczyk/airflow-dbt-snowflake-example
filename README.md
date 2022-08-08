# airflow-dbt-snowflake-example
Example usage of Apache Airflow and dbt and snowflake

# Prerequisites
1. Docker
2. Dcoker-compose
3. 4GB (ideally 8GB) RAM

> "...You should at least allocate 4GB memory for the Docker Engine (ideally 8GB). ..."

Check it by:
```bash
docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'
```

# Before first run (already done in this repo)
```bash
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.3.3/docker-compose.yaml'

mkdir -p ./dags ./logs ./plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env

docker-compose up airflow-init

# Write down my own DAG
```

# Run
```bash
docker-compose up
```

# Clean up

```bash
docker-compose down --volumes --remove-orphans --rmi all
# docker rm $(docker ps -a -q)
```

# Links
https://airflow.apache.org/docs/apache-airflow/stable/start/docker.html