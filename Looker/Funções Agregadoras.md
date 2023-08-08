# Funções Agregadoras

Nesta aula, aprendemos a utilizar funções agregadoras, com o objetivo de resumir informações essenciais para a Ilus Tecnologia. Dentre elas, utilizamos as seguintes funções: AVG(), MIN(), MAX() e COUNT(). Além disso, utilizamos o CASE WHEN para realizar a filtragem de alguns valores. Por fim, criamos as métricas de Absenteísmo e Turnover Geral.

Para utilizar todas essas funções, primeiro, precisamos criar um novo campo.Para isso, vamos na janela de Dados na lateral direita, na parte inferior, e clicamos em Adicionar um novo campo:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2a2b897c-713f-4aa1-b9f0-c670242809ef)

Em seguida, a aba para criação do campo irá aparecer na parte inferior da tela, contendo os campos de Nome do campo, Código do campo e de Fórmula.

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/61702866-f7b0-4af5-bfed-eeb6feabe57a)

Para explorarmos essas funções, criaremos algumas métricas.

Para a função AVG(), vamos criar a Média Salarial:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/7f324dc3-9edf-4ecf-951f-fea14a62b254)

Código:
```
AVG(Salario)
```

Para a função MIN(), criamos a Menor salário:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/53370b00-1bb4-41e1-a1b4-8973d7502d48)

Código:
```
MIN(Salario)
```

Para a função MAX(), criamos a Maior salário:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/32d43992-913d-4753-9186-7e0e44baf05d)

Código:
```
MAX(Salario)
```

E para o COUNT(), criamos duas métricas. Primeiro, criamos a Colaboradores ativos:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/f744a60b-d45c-4437-8ead-914b982e9bef)

Código:
```
COUNT(CASE WHEN StatusColaborador = "Ativo" THEN "Ativos" END)
```

Para a de Desligamentos:, temos o seguinte:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/63895e1a-0a14-480e-9c38-c823843d488f)

Código:
```
COUNT(CASE WHEN StatusColaborador = "Justa Causa" THEN "Desligados"
WHEN StatusColaborador = "Saída voluntária" THEN "Desligados" END)
```

Para a métrica de Absenteísmo, criamos o seguinte código:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/14967d9b-24ef-465a-b3d4-dbf2860a5fe2)

Código:
```
((COUNT(IdColaborador) * SUM(Faltas)) / (COUNT(IdColaborador) * 20)) / 1000
```

E, por fim, criamos a de Turnover Geral:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2e9fecdb-e630-4c4b-8de9-802a62a912f5)

Código:
```
((Admissões + Desligamentos) / 2) / Colaboradores ativos * 10
```
