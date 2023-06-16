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

## Criação do banco propriamente dito (mesmo a interface estando em português as opções ficavam em inglês)

Para criar o banco, iremos à ferramenta RDS e clicar em Create Database.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/fa7aa3f9-8f16-4b28-a20d-3ad151ac7309)

Faremos a configuração tradicional do banco (Standard) para ver um pouco mais sobre as configurações que iremos escolher. Será usado PostgreSQL versão 11.6.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/306a3f95-8236-4dce-b37f-5e41bca2a2f9)

Escolha a versão como FREE TIER, pois toda conta na AWS tem uma cota de ferramentas grátis por um tempo. Além disso, ela irá te redirecionar para criar um banco com um custo menor.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/6e0b4fdf-b502-449f-aa46-ee698cae32bc)

Preencha também o nome do seu banco e o usuário Master, aquele que terá acesso root na conta (permitido fazer tudo). Preencha sua senha ou deixe que a AWS escolha por você.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/9ebade17-5133-4b33-b4a1-1be522b1701f)

O tipo de máquina escolhido será a t2.micro por não precisarmos de processamento para esse exercício. Escolha 20GB de armazenamento e desative a opção de auto-scale.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/c1b76ce1-bb7c-40dd-b265-7de843381803)

A conectividade pode ser deixada em “default” e não deixaremos o RDS público, faremos um tunnel para acessá-lo via AWS.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/d2a8879e-5f4b-4524-8b7d-ff044cb77f6a)

Coloque para criar uma database “postgres” e desabilite o backup pois para esse exercício não será necessário.

Além disso iremos desabilitar o backup, mas não faça isso em sistemas normais. Está sendo desabilitado para evitar custos!

