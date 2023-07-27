# Data Analytics: Machine Learning no Marketing Digital

O tipo de operação Groupby já é muito conhecido para quem trabalha com SQL, podendo ser bem útil para fazer análise exploratória e criar variáveis no Python.

O conceito do groupby é muito simples, mas bem poderoso, uma vez que te permite criar grupos de categorias e aplicar uma função. No Python, o groupby é eficiente tanto em performance, quanto na quantidade de código que você precisa para executar a operação.

Abaixo segue algumas operações que você pode aplicar nas suas categorias uma vez que o agrupamento foi feito.

Funções de agregação:
- mean
- median
- min
- max
- sum
- describe
- count

Além disso, ao invés de chamar a função de agregação diretamente, você pode chamar o método agg() e passar a função que gostaria como parâmetro.

Operações mais complexas:
- agg()
- agg(‘mean’)
- agg(["mean", "median"])
- agg(custom_function())
