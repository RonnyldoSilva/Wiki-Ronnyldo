# Wiki Airflow

## Just some notes about Airflow

- DAG:
- Operadores:
- Jinja: são templates em python que podem ser usados no airflow.

## to run the airflow:
```
cd Documents/MyAirflow
source venv/bin/activate
export AIRFLOW_HOME=~/Documents/MyAirflow
airflow standalone
```

## to access the UI:
- open your browser
- go to localhost:8080/home

## variáveis dinâmicas

A modelagem no Airflow nos permite passar informações dinâmicas para as instâncias de tarefa em tempo de execução. Vamos usar, como exemplo, a tarefa que fizemos anteriormente:
```
   tarefa_4 = BashOperator(
        task_id = 'cria_pasta',
        bash_command = 'mkdir -p "/home/millenagena/Documents/airflowalura/pasta={{ data_interval_end }}"'
      )
```

Neste exemplo, o valor entre as chaves duplas `{{ }}` é nosso código modelo a ser avaliado em tempo de execução. O conteúdo retornado pela variável data_interval_end é a data final do intervalo de dados, ou seja, a data de acionamento do DAG.

O Airflow utiliza o **Jinja**, uma estrutura de modelagem em Python, como seu mecanismo de modelagem. Vamos conhecer mais algumas variáveis que podemos utilizar em tempo de execução:

- data_interval_start: data do início do intervalo de dados;
- data_interval_end: data do fim do intervalo de dados;
- ds: data lógica de execução do DAG;
- ds_nodash: data lógica de execução do DAG sem nenhuma separação por traços.

O Airflow inclui muitas outras variáveis que podem ser usadas para modelagem. Caso queira conhecê-las, consulte a documentação: https://airflow.apache.org/docs/apache-airflow/2.3.2/templates-ref.html

## criando o primeiro dag

Para o desenvolvimento do primeiro DAG, abrimos a pasta de instalação do Airflow e criamos uma subpasta chamada **dags**. Dentro dela, criamos um script Python, chamado **meu_primeiro_dag.py**, no qual desenvolvemos o código do nosso primeiro DAG, da seguinte forma:

- Importamos as bibliotecas:

```
from airflow.models import DAG
from airflow.utils.dates import days_ago
from airflow.operators.dummy_operator import DummyOperator
from airflow.operators.empty import EmptyOperator
from airflow.operators.bash_operator import BashOperator
```

- Especificamos os parâmetros do nosso DAG, criamos três tarefas utilizando o EmptyOperator e uma utilizando o BashOperator:

```
with DAG(
  'meu_primeiro_dag',
  start_date=days_ago(1),
  schedule_interval='@daily',
) as dag:

   tarefa_1 = EmptyOperator(task_id='tarefa_1')
   tarefa_2 = EmptyOperator(task_id='tarefa_2')
   tarefa_3 = EmptyOperator(task_id='tarefa_3')

   tarefa_4 = BashOperator(
        task_id = 'cria_pasta',
        bash_command = 'mkdir -p "/home/millenagena/Documents/airflowalura/pasta"'
      )

   tarefa_1 >> [tarefa_2, tarefa_3] 
   tarefa_3 >> tarefa_4
```
