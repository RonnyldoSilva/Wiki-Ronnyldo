# Grupos de segurança

Nessa seção vou explicar como fazer o passo a passo da liberação de acesso à sua máquina, você poderá precisar disso para configurar um primeiro acesso ou para trocar seu IP público caso o mesmo seja dinâmico. Isso pode acontecer em casos de desconexão do modem e queda de energia.

A primeira coisa que temos que fazer é obter o IP do computador que está fazendo o acesso. Você pode obtê-lo em sites procurando no google.

Uma vez que você obter esse ip, a primeira coisa que faremos é liberar na nossa EC2 a conexão na porta 22.

![image](https://user-images.githubusercontent.com/37785171/235221732-088b54cf-f0fb-4830-a969-f3d56c116930.png)

Vá ao menu de EC2 e selecione a máquina que você deseja conectar.

![image](https://user-images.githubusercontent.com/37785171/235221780-064c6f97-8cec-4051-9ba9-feb72f86cf3c.png)

Acesse a guia “Segurança” e ache a informação relativa a Grupo de Segurança.

![image](https://user-images.githubusercontent.com/37785171/235221806-2e84ab5a-7f01-4cbd-bbb3-b7b11427e5a4.png)

Clique no grupo de segurança e vamos à página do mesmo para editá-lo.

![image](https://user-images.githubusercontent.com/37785171/235221835-a5b7e94d-2a6d-425f-afd7-96662905f019.png)

Clique em “Editar regras de entrada” e insira o seu ip público com conexão para a porta 22 no modelo 111.222.333.444/32. Caso preferir, para permitir qualquer conexão, é possível fazer a liberação para o ip 0.0.0.0/0, porém qualquer um de qualquer local do mundo pode acessar sua máquina. Para entrar na mesma será necessária a chave SSH, mas ainda sim é um risco.
