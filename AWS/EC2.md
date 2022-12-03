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
