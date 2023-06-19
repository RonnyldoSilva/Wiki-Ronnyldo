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

## Custos na AWS e proteção de remoção

Quando nós falamos sobre nuvem, é sempre bom relembrar que nesse ambiente pagamos por aquilo que nós utilizamos. O RDS tem seu preço calculado baseado na quantidade de horas nas quais ele permanece ligado, por isso sempre lembre desligá-lo.

Mas preste bem atenção! Ao selecionar para desligar o mesmo, o RDS só permanece desligado por apenas 7 dias, logo após isso ele é ligado novamente. Portanto, sempre pondere se vale ou não a pena excluí-lo e refazer outro quando necessário.

Para mais informações em relação à precificação desse serviço, você pode clicar [aqui](https://aws.amazon.com/pt/rds/pricing/).

Durante a nossa aula, habilitamos a opção no banco em que é feita a proteção contra a remoção acidental desse banco. Para desabilitá-la, vamos primeiro na tela inicial onde nossos bancos são listados e selecionamos o banco do qual iremos remover essa proteção:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/bee2887c-e56c-406f-9872-43d16ce5e5bb)

Após selecionar, iremos clicar no botão “Modify” entre as opções na parte superior.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/aca38208-4f8b-403b-b205-bf0dea535721)

Nesta tela que se abriu, é possível modificar diversas características do nosso banco, entre elas o nome, senha do usuário master e tipo. Iremos descer e procurar a última opção, descrita com o nome “Enable deletion protection”.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/6373fb91-2794-4f33-8bf6-bf2ac0474260)

Desmarque a opção e clique no botão laranja de “Continue”, com isso será possível apagar o banco.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/4ad8f64c-8765-40d4-bf43-ad034714e224)

Esse tipo de alteração pode ser aplicada no que a AWS chama de janela de manutenção, a vantagem disso é que para sistemas de produção, durante essa janela o seu banco perde brevemente o acesso para atualizações importantes, e você aproveita esse momento para aplicar também suas modificações. Como não é o nosso caso, selecione a segunda opção “Apply immediately” e depois clique no botão laranja “Modify DB instance”. Algumas modificações podem levar algum tempo, mas essa será imediata.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/0f0c1b0b-9473-4c86-8dcb-e4c525976e59)

Selecione o banco que acabamos de editar, vá na opção “Actions” e depois vá em “Delete”, você será questionado se quer gerar uma última snapshot do banco. Como não há dados importantes, desmarque a opção, você deve marcar após a segunda opção que, ao deletar um banco, toda e qualquer informação e backup do mesmo é apagada em conjunto com ele.

Digite “delete me” para confirmar e clique no botão laranja “Delete”.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2d0a5972-10c6-4f94-a781-18db662c19a9)

Seu banco terá o estado mudado.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/33a21cdd-dfcd-41c0-92d2-57f61d2602e4)
