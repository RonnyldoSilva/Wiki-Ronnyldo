# Amazon EC2: alta disponibilidade

## Security groups

1 - Logado em sua conta no console AWS, acesse o serviço EC2;

2 - Na sessão “Instâncias”, clique no botão “Executar instâncias” para criar uma nova instância EC2;

3 - Defina um nome para sua instância e selecione a imagem padrão (Amazon Linux);

4 - Deixe todas as opções padrão até chegar em “Par de chaves (login)”;

5 - Crie um novo par de chaves. Mantenha as opções padrão e faça o download da sua chave;

6 - Altere as permissões de sua chave com chmod 400 sua-chave.pem;

7 - Finalize clicando em “Executar instância”;

8 - Com a instância sendo executada, acesse os detalhes da instância e vá até “Conectar”. Siga as instruções para se conectar à instância;

9 - Vá até “Security group” e edite as regras de entrada do security group criado para nossa instância, permitindo acesso somente de “Meu IP”;

10 - Crie um novo Security group para liberar acesso web (portas 80 e 443);

11 - Vá até “Instâncias” e adicione esse Security group à instância criada anteriormente.

## Create an instancy with NGINX image.

1 - Encerre a instância criada no capítulo anterior;

2 - Crie uma nova instância e na sessão de imagem, clique em “Procurar mais AMIs” para selecionar uma imagem diferente;

3 - Em “AMIs do AWS Marketplace” procure por “nginx” e selecione a imagem gratuita chamada “NGINX Open Source packaged by Bitnami”;

4 - Continue a criação da instância normalmente, atrelando a ela os grupos de segurança já criados;

5 - Dê um nome (algo como “nginx”) para a instância recém criada;

6 - Nos detalhes da instância, clique para acessar o endereço de DNS público dessa instância. Na aba aberta, substitua “https” por “http”. A página de boas-vindas da imagem deve ser exibida com sucesso;

7 - Se conecte, via ssh, à instância usando o usuário “bitnami”.

## Imagem vs Modelo

Qual a diferença entre Imagem e Modelo que podemos criar a partir de uma instância existente?

- Imagem é relacionado ao software enquanto Modelo é ao hardware.

- Ao criarmos uma instância a partir de uma imagem, podemos selecionar todo o hardware (tipo de instância, rede, etc) e algum software já vem pré-instalado. No exemplo da aula foi o Nginx. Já com o Modelo, nós podemos selecionar qualquer imagem e o hardware já estará pré-configurado. Inclusive nós criaremos um modelo mais adiante no curso para que a AWS possa criar instâncias automaticamente para nós.

- `Criação` da image. Para criarmos uma imagem a partir de uma instância, o que devemos fazer? Parar a instância e criar a imagem. Parar a instância sempre é a recomendação. Desta forma, garantimos a integridade dos dados.
