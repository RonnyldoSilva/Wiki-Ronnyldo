Nesta aula, aprendemos a utilizar funções de texto, com o objetivo de tratar alguns dados para a Ilus Tecnologia. Dentre elas, utilizamos as seguintes funções: 

- REGEX_MATCH()
- CONCAT()
- UPPER()
- LEFT_TEXT()
- UPPER()

Com essas funções, elaboramos a métrica para o Motivo_Saida, como podemos verificar a seguir:

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/2d592e52-a717-40b5-ba42-4e5af6d1a087)

Código:
```
CASE WHEN REGEXP_MATCH(MotivoSaida, "N/A-STILL Empregado") THEN "Empregado"
WHEN NOT REGEXP_MATCH(MotivoSaida, "Empregado") THEN CONCAT(UPPER(LEFT_TEXT(MotivoSaida, 1)), "", SUBSTR(MotivoSaida, 2, 20)) END
```
