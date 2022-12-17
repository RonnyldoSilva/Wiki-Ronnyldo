# AWS RDS

1 - Selecione a instância “nginx” e crie uma imagem a partir dela;

2 - Após a imagem ficar disponível, execute uma nova instância a partir dessa imagem;

3 - Após as verificações de status finalizarem, acesse a instância para confirmar que tudo funcionou como esperado;

4 - Encerre essa última instância para evitar custos, já que não vamos mais utilizá-la;

5 - Reinicie a instância “nginx” e veja que seu IP e seu DNS vão mudar;

6 - Acesse a página de “IPs elásticos” e aloque um novo IP com todas as opções padrão;

7 - Clique no IP recém criado e o associe à instância “nginx”;

8 - Acesse http://seu-ip-elastico para conferir que o acesso à instância está ocorrendo com sucesso;

9 - Entre na instância (via ssh) e execute sudo apt update && sudo apt install posgresql para instalar o PostgreSQL na instância;

10 - Na busca do console da AWS, pesquise por RDS e acesse o painel desse serviço;

11 - Crie um novo banco de dados compatível com PostgreSQL no Nível gratuito;

12 - Veja os detalhes de conexão para copiar sua senha. Copie também o endpoint (host) do banco;

13 - Adicione à sua instância o security group “default” que permite todo tráfego dentro da VPC;

14 - Quando o banco estiver disponível, acesse novamente (via ssh) sua instância EC2 e se conecte ao banco através do comando psql -U postgres -p -h seu-endpoint-rds-aqui e após digitar “Enter”, entre com sua senha.
