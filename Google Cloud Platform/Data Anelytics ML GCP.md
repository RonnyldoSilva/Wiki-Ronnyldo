# Data Analytics: Machine Learning com Google Cloud Platform

Código mencionando no último vídeo do curso anterior.

```
import json

# Transformando as chaves dos dicionários em novas colunas
for coluna in dicionarios:
  visitas = visitas.join(
    pd.DataFrame([json.loads(json.dumps(linha))
      for linha in visitas[coluna]]) , rsuffix=('_' + coluna) )
visitas.drop( dicionarios, axis=1, inplace=True)

# Corrigindo o formato das colunas com valores quantitativos
totals = df.totals[0].keys()
totals = list(totals)
for coluna in totals:
  visitas[coluna] = pd.to_numeric(visitas[coluna])

# Limpando os dados
visitas.drop('adwordsClickInfo', axis=1, inplace=True)
# Remove as colunas cujo domínio só tem um elemento
coluna_na = []
for coluna in visitas.columns:
  print(str(coluna) + ': ' + str(len(visitas[coluna].unique())))
  if len( visitas[coluna].unique()) == 1:
    coluna_na.append(coluna)
visitas.drop( coluna_na, axis=1, inplace=True)
```

