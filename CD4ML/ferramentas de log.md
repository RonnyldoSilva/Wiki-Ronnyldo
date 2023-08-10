# Ferramentas de Log

Na construção e exploração do nosso log, combinamos três ferramentas, utilizando assim uma stack chamada de EFK. O E de Elasticsearch, o F de Fluentd e o K de Kibana. Conhecer um pouco dessas ferramentas é muito importante para entender como elas nos ajudam a aplicar o CD4ML no nosso sistema de machine learning.

#### Fluentd
O Fluentd é um coletor de dados de código aberto, que permite unificar a coleta e o consumo de dados para um melhor uso e compreensão dos dados. Ele é o responsável por unir nossos logs que vem de diversas fontes e você pode se aprofundar mais pela documentação do Fluentd.

#### Elasticsearch
Já o Elasticsearch é o mecanismo distribuído de pesquisa e análise. Ele fornece pesquisa e análise quase em tempo real para todos os tipos de dados. Seja o dado texto estruturado ou não estruturado, sejam dados numéricos ou dados geoespaciais, o Elasticsearch pode armazená-los e indexá-los com eficiência, de forma a oferecer suporte a pesquisas rápidas.

Você pode ir muito além da simples recuperação de dados e agregar informações para descobrir tendências e padrões em seus dados. E, conforme seu volume de dados e consultas cresce, a natureza distribuída do Elasticsearch permite que sua implantação cresça perfeitamente junto com ele. Você pode se aprofundar mais pela documentação do Elasticsearch.

#### Kibana
Por fim, com o Kibana, você pode pesquisar e observar seus dados. Ele possibilita desde a descoberta de documentos até a análise de logs e visualização dos dados (em gráficos, medidores, mapas combinados em um painel, etc.).

Você pode se aprofundar mais pela documentação do Kibana.
