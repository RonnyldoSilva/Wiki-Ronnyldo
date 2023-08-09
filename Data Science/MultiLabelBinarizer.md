# MultiLabelBinarizer

O MultiLabelBinarizer é utilizado para casos onde temos várias labels dentro da mesma “ocorrência”. Em caso mais simples onde temos uma coluna com uma categoria por linha, uma forma bem simples de fazer esse tratamento é com o método “get_dummies” do Pandas.

```
pd.get_dummies(df[‘sx’])
```

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/fd0e1d39-7c6d-4b11-9b2d-b8d8c28502ca)

No exemplo acima, para cada valor único da coluna “sx”, será criado uma coluna que é marcada com “1” quando há ocorrência do valor da coluna, e “0” quando não há.

