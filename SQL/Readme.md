🚀 Resumão de SQL Básico 🚀

Pra quem, como eu, sempre esquece da sintaxe das linguagens pouco usadas.

1. SELECT: Usado para selecionar dados de um banco de dados.
-----------------------------
  SELECT * FROM clientes;
-----------------------------

2. WHERE: Filtro de registros com base em uma condição.
--------------------------------------------------
  SELECT * FROM clientes WHERE idade > 30;
--------------------------------------------------

3. IN: Filtra registros que correspondem a qualquer valor em uma lista.
----------------------------------------------------------------------------
  SELECT * FROM clientes WHERE cidade IN ('São Paulo', 'Rio de Janeiro');
----------------------------------------------------------------------------

4. OR/NOT: Combina condições, permitindo maior flexibilidade nas consultas.
----------------------------------------------------------------------------
  SELECT * FROM clientes WHERE cidade = 'São Paulo' OR cidade = 'Rio de Janeiro';
  SELECT * FROM clientes WHERE NOT cidade = 'São Paulo';
----------------------------------------------------------------------------

5. Wildcards (Coringas): Usados com LIKE para buscar padrões específicos.
----------------------------------------------------------------------------
  SELECT * FROM clientes WHERE nome LIKE 'J%'; -- Nomes que começam com J
  SELECT * FROM clientes WHERE nome LIKE '%a'; -- Nomes que terminam com a
----------------------------------------------------------------------------

6. ORDER BY: Ordena os resultados da consulta por uma ou mais colunas.
------------------------------------------------------
  SELECT * FROM clientes ORDER BY nome ASC;
  SELECT * FROM clientes ORDER BY idade DESC;
------------------------------------------------------

7. Operações Matemáticas: Realiza cálculos básicos dentro da consulta.
----------------------------------------------------------------------------
  SELECT nome, salario * 1.1 AS salario_reajustado FROM funcionarios;
 ----------------------------------------------------------------------------

8. Funções Agregadoras: Realizam cálculos em um conjunto de valores e retornam um único valor.
----------------------------------------------------------------------------
  SELECT COUNT(*) FROM clientes; -- Conta o número de clientes
  SELECT AVG(idade) FROM clientes; -- Calcula a idade média
  SELECT SUM(salario) FROM funcionarios; -- Soma de todos os salários
  SELECT MAX(salario) FROM funcionarios; -- Salário máximo
  SELECT MIN(salario) FROM funcionarios; -- Salário mínimo
----------------------------------------------------------------------------

9. GROUP BY: Agrupa os resultados por uma ou mais colunas.
----------------------------------------------------------------------------
  SELECT cidade, COUNT(*) FROM clientes GROUP BY cidade;
  SELECT departamento, AVG(salario) FROM funcionarios GROUP BY departamento;
----------------------------------------------------------------------------
