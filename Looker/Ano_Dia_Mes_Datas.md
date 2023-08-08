# Trabalhando com datas e horas

Nesta aula, aprendemos a utilizar funções de data, com o objetivo de analisar informações relacionadas aos períodos de tempo para a Ilus Tecnologia. Dentre elas, utilizamos as seguintes funções: CURRENT_DATE(), DATE_DIFF(), DAY(), MONTH(), QUARTER() e YEAR().

Primeiramente, criamos a Data Atual, através da função CURRENT_DATE():

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/09aae289-89ce-410f-923a-239861bcf7dc)

Código:
```
CURRENT_DATE("America/Sao_Paulo")
```

Com a data atual criada, elaboramos o cálculo da idade do colaborador, utilizando a função DATE_DIFF(), com apoio da função FLOOR() para arredondar o resultado:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/4d630bfc-49b8-4ef5-b46e-ea4e81a556fd)

Código:
```
FLOOR(DATE_DIFF(Data Atual, DataNascimento) / 365)
```

Em seguida, adicionamos o campo de dia:

Código:
```
DAY(DataContratacao)
```

O campo de mês:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/3ed79b4d-22f1-4662-8aa8-b703e1e57a99)

Código:
```
MONTH(DataContratacao)
```

O campo de ano:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/1ea817ce-da24-432b-a771-45324b1347cc)

Código:
```
YEAR(DataContratacao)
```

E, por fim, o de trimestre:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/063cc18d-2fe0-4223-bb08-c9c632f6bb04)

Código:
```
QUARTER(DataContratacao)
```
