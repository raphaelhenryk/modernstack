# modernstack
# refresh test

This is a repo that will storage pipelines artfacts using Modern Data Stack Technologies, such as Airbyte, Air Flow, dbt, Metabase, etc.


Infraestrutura:
    - Setup do Ambiente de Dev (Hardware e Software: Linux, Python, Docker, Curl, Pip, Git, Npm, atc...)
    - Liberar permissoes do Gitpod no github
    - Subir Airbyte via Docker: 
        https://docs.airbyte.com/quickstart/deploy-airbyte/
        OBS: ao inves de dar clone, dar um fork no codigo do airbyte, cria-se entao uma branch no codigo forkeado.
        Executa-se entao o clone do airbyte da branch criada no seu proprio repositorio, e nao no repo oficial.
        git clone -b modernstack https://github.com/raphaelhenryk/airbyte.git
        cd airbyte
        docker-compose up


    - Subir Airflow via Docker
        https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html
        Cria-se um diretorio airflow
        cd airflow
        executase a partir do diretorio airflow, o seguinte comando: 
        curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.5.0/docker-compose.yaml'
        executar os comandos:
        mkdir -p ./dags ./logs ./plugins
        echo -e "AIRFLOW_UID=$(id -u)" > .env

        - Subir os serviços do Airflow: comando :
        docker compose up airflow-init

        - Subir o Airflow: comando :
        docker-compose up
        criar um arquivo .gitignore na pasta do Airflow para que nao suba a pasta logs/*
        commit

    - Subir Metabase via Docker
        criar a pasta metabase
        criar um arquivo docker-compose.yaml
        
            version: "3"
                services:
                metabase-app:
                    image: metabase/metabase
                    restart: always
                    ports:
                    - 3000:3000
                    volumes:
                    # declare your mount volume /host/dir:/container/dir
                    - /home/app/metabase-data:/metabase-data
        
        cd metabase
        docker-compose up


    - Criar Script de Execução
        Shell script com todos os comandos do terminal, para subir os serviços
        
    - Testar a Execução

Extraçao
Preparacao
Transformação
Visualização
Orquestração
    - Airflow: 
        Criar Dag
        Criar a Docker Network
        Incluir nos composes a Net Criada
        Setup Do Serviço
        Testar a conectividade entre os containers do Airflow e do Airbyte
        Criar as Conexoes com o Airbyte atraves do Script
        Testar a Execução do Pipeline
Encerramento

Tasks:
- Airbyte
- Air Flow
- Create Snowflake Account
- 