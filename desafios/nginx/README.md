# fullcycle

## Desafio Nginx com Node.js

###### Criação das imagens:

docker-compose up -d --build 


###### Execução

Após executar o docker-compose up acessar http://localhost:8080 

Para criar a tabela no mysql, foi utiliza um recurso da imagem do mysql, de execução de scripts o warmap do servidor.
Foi criado uma pasta: mysql/script e mapeado o volume: ./mysql/script:/docker-entrypoint-initdb.d
O entrypoint da imagem executa todos os arquivos contidos no diretório mapeado. 
Na pasta mysql/script foi criado o arquivo: create-table.sql com o conteúdo: 
create table people(id int not null auto_increment, name varchar(255), primary key(id));
Os arquivos do banco de dados foi mapeado para mysql/db 

A pasta mysq/**db** foi incluída no gitignore para evitar subir para o repositório arquivos do banco de dados.