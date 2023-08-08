# Controles de Período

### Como funcionam os controles de período?

Com o controle de período, você pode mudar as datas que gostaria de ver no relatório. Para definir um período personalizado, escolha as datas de início e término. Também é possível selecionar uma das opções em uma lista de períodos predefinidos, como Ontem, Últimos sete dias (incluindo hoje), Trimestre passado, Acumulado no ano etc.

### Período padrão

Quando você adiciona pela primeira vez um controle de período ao seu relatório, ele usa o período padrão da fonte de dados (que, por sua vez, depende do conector usado por essa fonte). Por exemplo, o conector do Google Analytics utiliza por padrão os últimos 28 dias, já o conector do Planilhas Google oferece todos os dados contidos na planilha. Para substituir esse padrão, mude a configuração do Período padrão do controle.

### Controles de período e fontes de dados

Para adicionar um controle de período a um relatório, pelo menos uma das origens de dados anexada ao relatório precisa ter uma dimensão de dados. Os controles de período afetam apenas os gráficos criados em origens de dados com uma dimensão de data.

### Escopo do controle de período

Um controle de período é usado em todos os gráficos na página. É possível limitar o escopo desse controle de uma destas maneiras:

1) Definir uma propriedade de período para um gráfico individual substitui o controle de período.

2) Agrupar um controle de período com um gráfico limita o controle desse período ao gráfico em questão. Os gráficos não agrupados não são afetados pelo controle de período.

O controle de períodos pode ser muito útil quando desejamos filtrar os dados que contém uma dimensão de data, facilitando a visualização de informações em datas específicas.

# Filtros para vizualização de dados dinâmica e interativa

Nesta aula, conhecemos e utilizamos alguns filtros do Looker Studio, os quais nos ajudam a visualizar os dados de forma dinâmica e interativa.

Primeiramente, criamos os controles de lista, sendo eles: Lista suspensa e Lista de tamanho fixo.

Para acessar o controle de Lista suspensa, fomos em Adicionar um controle, na barra de ferramentas no topo. Entre as opções, clicamos em Lista suspensa:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/16822e09-1a1e-4081-a4d5-83c7d8148f67)

Os campos utilizados nesse visual foram o seguintes:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/04506531-81d0-4903-8848-56f3c29dc64d)

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/ae5a6001-da53-4d9b-9f57-1284980ad7d8)

E assim criamos o visual de Lista suspensa:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/82783a26-3267-466f-9b2c-800b7e82feee)

Em seguida, clicamos novamente no botão Adicionar um controle, dessa vez escolhendo o controle de Lista de tamanho fixo:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/742b53df-0be4-4025-8536-82772ca9b76a)

Com os seguintes campos:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/aef7a533-a3dc-4127-868d-49ab5defeb60)

Com o filtro de Lista de tamanho fixo ficando da seguinte forma:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/d7d796db-4c4d-4e17-a515-f193be100159)

Mais à frente, adicionamos uma Caixa de entrada, seguindo os passos anteriores:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/de42f65a-fdfe-4ab2-9ef8-f64e84bb2a64)

A seguir podemos verificar seus campos:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/32b221ef-6fcc-4356-9ce1-a0fdfc5432a8)

E o seu visual:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/f68b71dc-178f-462b-aa01-71bab37cbc53)

Por fim, adicionamos o Filtro avançado:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/64885fb9-b1a5-42c3-9c8a-d2bee1d27386)

Com sua configuração a seguir:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/e560e09b-2ff7-4abc-b32c-0963671eff3b)

O seu visual ficou da seguinte maneira:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/a5defae8-f8ee-43dd-93fe-f6f0ded1d791)
