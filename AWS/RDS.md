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

## “Credenciais sugeridas pela AWS”

Se você pediu que a senha de seu usuário administrador no RDS fosse gerada automaticamente, siga esse guia para conseguir obtê-la.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/3ad53db8-91cd-4fdd-adaa-c52729bf264a)

Aguarde a criação do seu banco ser concluída checando no campo de status. Durante a criação do banco (ou ao fim da mesma), um aviso vai aparecer informando das credenciais que foram geradas. ESSE ARQUIVO SÓ APARECE UMA VEZ, portanto guarde as informações em um local seguro, pois ela dão os maiores acessos possíveis ao seu banco. Clicamos em “View credentials details”.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/252fe13c-1c5a-4902-9099-588da1e9e10f)

Uma nova janela irá se abrir, guarde essas informações.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/3901b51a-2d40-4472-bb0e-0a632c1efd25)
