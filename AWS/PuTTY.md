# Preparando o ambiente: Instalando o PuTTY

Para essa primeira aula precisaremos de dois softwares, o PuTTY, para conectar com o nosso servidor.

Para instalarmos o PuTTY, vamos obter o instalador a partir do seu site, vamos pegar a versão instalável pois será necessário a aplicação do PuTTY para trabalharmos chaves SSH.

![image](https://user-images.githubusercontent.com/37785171/235198271-80929db7-37bd-4943-9910-c0a80e2bbc18.png)

Escolha o melhor lugar para instalação.

![image](https://user-images.githubusercontent.com/37785171/235198323-141b4d0d-f52c-4529-986e-100b7545e492.png)

Selecione instalar e aguarde a finalização.

![image](https://user-images.githubusercontent.com/37785171/235198348-a8f43020-aaaf-4efa-b8d7-ceb42b2a9cd3.png)

Se quiser, abra o PuTTY para checar se tudo ocorreu bem, assim ele deve ser apresentado.

![image](https://user-images.githubusercontent.com/37785171/235198378-e213397d-7eeb-4538-a4c4-e4fac0133e51.png)

Em breve iremos utilizá-lo para fazer as conexões.

## Um exemplo de configuração

Para a conexão em nossa máquina recém criada, fizemos a conversão da nossa chave .pem para uma chave privada, que usaremos para conectar em nosso servidor. Para realizar este processo, utilizamos um dos softwares que são instalados juntamente ao Putty, o PuttyGen.

![image](https://user-images.githubusercontent.com/37785171/235217417-2c912e07-2b67-4089-af93-928622376a06.png)

Com o PuttyGen aberto, clicamos na barra superior de “Conversions” e logo após em “Import key”. Uma nova tela se abrirá para que possamos localizar o arquivo de extensão “.pem”. Com o arquivo já carregado, iremos salvar a nossa chave privada clicando em “Save private key”!

![image](https://user-images.githubusercontent.com/37785171/235217494-f6617652-f264-49d6-9609-9ca6246b21ca.png)

Um pop up aparecerá caso você não tenha configurado uma senha para sua chave privada (caso tenha o feito, ela terá de ser inserida em toda conexão). Clique em “Yes” não queira usar.

Lembrando que esse arquivo permite a conexão à sua EC2, ou servidor. Caso esse servidor esteja aberto para a internet e alguém obtiver esse arquivo, ele terá livre acesso.

Uma vez feita essa conversão, configuramos o PuTTY para o primeiro acesso.

![image](https://user-images.githubusercontent.com/37785171/235217678-ca2592ed-3952-48f4-8401-1a549cd38111.png)

Além das configurações de porta e host, configuramos também o SSH, inserindo a chave que acabamos de converter dentro dos menus “Connection” -> “SSH” -> “Auth” e clicando no botão de browse.

![image](https://user-images.githubusercontent.com/37785171/235217782-e522706c-fba9-4553-b7db-ea23e0aaf04c.png)

Uma vez conectados, utilizamos o comando `htop` na linha de comando que nos mostrou as configurações da máquina, além do quanto processamento está sendo utilizado. Uma vez feita a análise, utilizamos Ctrl + C para fechá-lo.

A instância ao final desta aula pode ser encerrada com o comando:
```shell
sudo shutdown
```
