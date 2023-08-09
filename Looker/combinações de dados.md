# Combinações de dados

Nessa aula, realizamos a combinação de dados. No Google Looker Studio, podemos fazer isso através da opção de Gerenciar mesclagens.

Para isso, você pode acessar a opção de Recursos na barra de ferramentas, e escolher a opção desejada:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/ba1d0ec7-1909-477a-8c79-a347246907c7)

De início, não temos nenhuma mesclagem criada. Nesse caso, podemos clicar na opção Adicionar uma combinação:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/085ce78a-71a9-492a-a5dc-d13ff0fd08a3)

A primeira combinação que realizamos foi entre a tabela de produtos e a tabela de itens_pedidos. Para realizar essa mesclagem, utilizamos a junção do tipo interna, ligando os campos de produto_id:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/5c8ddc2e-cf28-4360-8c09-262e2835eb97)

Em seguida, realizamos a combinação da tabela de itens_pedido com a de pedido, com o mesmo tipo de junção, porém desta vez ligando os campos de pedido_id:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/4718f114-ea27-475a-9567-7155962a4e3a)

As mesclagens completas ficaram da seguinte forma:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/d127a742-53ed-4ffd-bcec-b42d6f6f12db)

Após combinar os dados de fontes iguais, nos resta mesclar a outra fonte. Nesse caso à tabela de vendedores, utilizando o tipo de junção Externa à esquerda, ligando os campos de vendedor_id:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/e602aecc-7ca9-4eab-9d93-ab938e8be095)

Após selecionar o tipo de junção, temos a nova mesclagem com a tabela de vendedores:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/d3ce1a2c-f0b6-4951-a70b-6ebd1a156317)

Após realizarmos as combinações, vamos realizar a importação de uma nova fonte de dados, porém dessa vez vamos fazer isso através de uma consulta em SQL nas tabelas do banco de dados Meteora. Para isso, vamos na opção de Recursos novamente e vamos clicar em “Gerenciar fontes de dados adicionais” dessa vez:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/d4af4409-717c-44f4-8770-9801ab3402a3)

Na tela seguinte, iremos clicar em Adicionar uma fonte de dados:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/fb585f96-307d-4f2c-83e1-39e242076c2d)

Vamos selecionar a fonte do MySQL novamente:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2f224f77-b250-42e2-9112-9cd92a8be295)

Dessa vez, após preenchermos os campos do nosso banco, vamos selecionar a opção de Consulta personalizada, onde iremos adicionar a consulta em SQL:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/15e02af9-4f68-4e32-abf9-37cc52ce5031)

Abaixo, você pode copiar o comando em SQL:

```
SELECT
p.produto,
p.marca,
p.preco,
ip.quantidade,
ip.valor_total,
ip.estado,
ip.frete,
p2.data_compra,
p2.vendedor_id

FROM produto p 

INNER JOIN itens_pedido ip on p.produto_id = ip.produto_id 
INNER JOIN pedido p2 on p2.pedido_id = ip.pedido_id
```

Após adicionarmos essa outra fonte de dados, vamos combiná-la com a tabela de vendedores, criando uma nova mesclagem. Para isso, vamos utilizar a junção do tipo Externa à esquerda:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/78116193-5d81-4050-a34e-a809ada05cfd)

A combinação ficará da seguinte forma:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/391eab55-7511-4498-9407-700e2bc19f1a)

Chegamos ao fim das etapas realizadas nesta aula, onde realizamos a combinação de várias tabelas, além da importação de novas fontes de dados.
