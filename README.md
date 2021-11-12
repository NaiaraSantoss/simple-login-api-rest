# simple-login-api-rest
Simples API REST login com Spring Boot
##Setup:

* Ubuntu 20.04
* Java 17
* Mysql 8
* Spring Boot
* Maven 4.0.0
* Postman

#### Passo a passo:
- Criar o repositório no spring initialazr.
- Gerar o arquivo.
- Adicionar as dependências (use as dependências do pom xml deste repositório - basta colar)
- Crie as classes necessárias.
- Execute o projeto.
- Caso apareça que não foi possível executar, observe se foi por falta da tabela table_pessoas.
- Instale o Mysql(Instruções ao final dessa página)
- Crie a tabela table_pessoas.
- Use os verbos http no Postman para adicionar, consultar e atualizar os dados.

### POST http://localhost:8080/pessoas
` {"id": 1,
"nome": "Naiara"
}`
### GET http://localhost:8080/pessoas/1

Para verificar se as alterações no postman foram realizadas com sucesso, consulte o Database no terminal.


`sudo mysql
show databases;
use table_pessoas;
show tables;
select * from pessoa`


### Instalar Mysql

`sudo apt update`

`sudo apt install mysql-server`

`sudo mysql_secure_installation`

`sudo mysql`

`CREATE USER 'admin'@'localhost' IDENTIFIED BY 'suasenha';`

`GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;` 

`CREATE USER 'suporte'@'%' IDENTIFIED BY 'suasenha';`

`GRANT ALL PRIVILEGES ON *.* TO 'suporte'@'%' WITH GRANT OPTION;`

`FLUSH PRIVILEGES;`

### Instalar Mysql Client

`sudo apt install mysql-client`


- verificar o inet com “ifconfig”
`ifconfig`
saída: 10.0.2.15

`sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf` 

Para liberar acesso de outros computadores, mude o bind-address para 0.0.0.0 e mysql-adress para 0.0.0.0

`skip-name-resolve #conflitos`dns /request de ip

`sudo service mysql restart`

`mysql -usuporte -pInfo@1234 -h10.0.2.15`

`show databases;`

`create database table_pessoas;`

- Desinstalar mysql

` sudo apt-get remove --purge mysql*

sudo apt-get purge mysql*

sudo apt-get autoremove

sudo apt-get autoclean

sudo apt-get remove dbconfig-mysql

sudo apt-get dist-upgrade`


