# Análise Descritiva em Python

Obtenha a idade média dos homens. Observação: Na variável `Sexo`, 'H' representa os homens e 'M' as mulheres.
```python
dataset = pd.DataFrame({
    'Sexo': ['H', 'M', 'M', 'M', 'M', 'H', 'H', 'H', 'M', 'M'],
    'Idade': [53, 72, 54, 27, 30, 40, 58, 32, 44, 51]
})

dataset.groupby('Sexo').mean().loc['H']
```
