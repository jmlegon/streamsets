# streamsets

In order to run this tutorial, you need first to provision a SQL Server database. 
For that, you can rely on Docker:

1) Extract the SQL Server 2019 or 2017 images from MS Azure Container Registry

sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
  Or ...
sudo docker pull mcr.microsoft.com/mssql/server:2017-latest


2) launch the container
sudo docker run -d --name sql_server_demo -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Juanito1!' -p 1433:1433 microsoft/mssql-server-linux

3) start the agent

sudo docker exec -it sql_server_demo "/opt/mssql/bin/mssql-conf" set sqlagent.enabled true

3) restart SQL Server

sudo docker run -d --name sql_server_demo -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=******' -p 1433:1433 microsoft/mssql-server-linux --restart=unless-stopped


4) import the Pipeline into your own Streamsets org : (CRUD-Operations-Microservice-MSSQL.zip)

5) import the following collection in Postman (streamsets-microservice-template.postman_collection.json)
