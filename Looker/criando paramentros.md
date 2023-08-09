# Criando Parâmetros

Nessa aula, conhecemos os parâmetros, uma outra forma de criar campos no Google Looker Studio. Para criá-los, o procedimento é parecido ao de criar um campo.

O primeiro parâmetro que criamos foi o de Quantidade, na tabela de Produto:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/816d12c7-008e-4e1c-8c33-cad539af8438)

Após isso, criamos um novo campo chamado Total orçamento, com a seguinte fórmula:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/b6c6312a-9313-4ab4-bdd3-6782972fe060)

Após criar tanto o parâmetro quanto o campo, criamos um visual de tabela contendo os campos de “produto”, “preco” e “Total orçamento”. Além disso, adicionamos o parâmetro de Quantidade no canva:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/56da876e-17fd-4965-8222-23947a29d94f)

Após adicionarmos esses visuais, criamos outro parâmetro chamado Percent Lucro:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/f60cbe86-932c-4023-be3d-e027fc3d729c)

Em seguida, criamos um novo campo chamado Lucro análise cenário:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/403481f4-b0dc-4be8-bb2b-c38ae27303cc)

Após criar tanto o parâmetro quanto o campo, criamos um visual de tabela contendo os campos de “estado”, “Receita” e “Lucro análise cenário”. Além disso, adicionamos o parâmetro de Percent Lucro no canva:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/838c09ab-52ba-4c95-9e3f-2f785a7dc2aa)

Em seguida, criamos um outro parâmetro chamado “estado”, contendo uma lista de valores com todos os estados brasileiros:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/1d9e2848-f723-45c1-b8e9-fa877a5010a3)

Após criarmos esse parâmetro, partimos para a ativação da opção de modificação no URL do relatório. Para isso, vamos em Recurso e clicamos na opção “Gerenciar parâmetros de URL do relatório”:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/3db6ae79-5f14-485c-bcfe-5dae0a51dd76)

Na tela de gerenciamento, clicamos na caixa de seleção da coluna de “Permitir a modificação no URL do relatório” para o parâmetro de “estado”. Aqui, também é importante você pegar o código que está destacado em verde, pois vamos utilizar ele para configurar o parâmetro. No meu caso, o meu código é ds0.estado:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2b89b72b-7528-4438-baa4-6c41f673a0da)

Após permitir a modificação, fomos em Compartilhar e clicamos em “Gerar link do relatório”:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/0c3ce457-42a1-49c5-9329-ebe0bc8c21de)

Na janela aberta, desativamos a opção de “Vincular à vista atual do relatório” e clicamos em “Copiar link”:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/003f5e62-b8b1-4a8d-a40d-222e8c9da871)

Após copiarmos o link, colamos na barra de pesquisa do navegador e adicionamos o trecho ?params= no fim do link:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/dc868610-a30f-46d7-a616-66d79a63ece8)

Para podermos configurar o valor do parâmetro, entramos no da MDN para criarmos nosso código para lidar com o JSON stringfy.

No site, usamos o código a seguir. Lembre-se de verificar qual é o número da chave ds0.estado. No meu caso, o meu tem o número 0, porém no seu pode ser diferente:

```
var params = {
      "ds0.estado": "BR-GO"
    };
    var paramsAsString = JSON.stringify(params);
    var encodedParams = encodeURIComponent(paramsAsString);
console.log(encodedParams);
```

Com o código inserido, vamos clicar em Run e copiar o resultado gerado:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/26b506d5-7d78-4480-9a43-f4d165f8b1ce)

Você pode copiar o código gerado a seguir:

```
%7B%22ds0.estado%22%3A%22BR-GO%22%7D
```

Mas antes de adicionarmos o código no link, temos que trocar o campo de dimensão estado pelo parâmetro estado na tabela que criamos por último:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/9a956233-f70d-47b6-aed1-c73347756060)

Agora, podemos colar o código no link e rodar:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/36e6ca62-4fb4-4c3c-80f5-29e2479de88e)

Após rodar, podemos conferir se estão sendo filtrados de acordo com o estado que coloquei no parâmetro e, nesse caso, será GO:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/a91eab0f-cf32-4fa6-9516-5e1388c25c9f)

Chegamos ao fim das etapas realizadas nesta aula, onde realizamos a criação de parâmetros e os utilizamos no nosso relatório.

