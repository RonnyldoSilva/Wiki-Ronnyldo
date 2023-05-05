# PostgreSQL

### Instalando PSQL

Para realizar este processo, a primeira coisa que fizemos foi conectar em nossa EC2 recém criada via SSH pelo Putty como na aula passada. Uma vez conectados a primeira coisa que fizemos foi atualizar os pacotes que podem ser instalados na máquina:

```
sudo apt-get update
```

Logo após fizemos a instalação do banco de dados e o setup do usuário com os seguintes comandos:

```
sudo apt install postgresql postgresql-contrib
sudo -u postgres psql
```

Com o PSQL instalado, iremos criar um usuário administrador através do qual iremos interagir com o banco. Como uma boa prática, o ideal é que existam diferentes usuários para diferentes tabelas, além de separá-los entre leitura/escrita. Para fins didáticos, permaneceremos apenas com um.

```
CREATE USER admin WITH PASSWORD 'admin';
ALTER USER admin WITH SUPERUSER;
```
