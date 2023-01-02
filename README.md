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

    - Subir Airflow via Docker
    - Subir Metabase via Docker
    - Criar Script de Execução
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