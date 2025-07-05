
# Entendendo Attention e Dropout no BERT e Vision Transformer (ViT)

## 🔹 1. Attention (Atenção)

### 👉 O que é?
O mecanismo de **atenção** é o núcleo dos modelos Transformer. Ele permite que o modelo foque em partes relevantes da entrada ao processar um elemento, como uma palavra (no BERT) ou um patch de imagem (no ViT).

### 📌 Como funciona?
Cada token ou patch é transformado em três vetores:

- **Q (Query)**
- **K (Key)**
- **V (Value)**

A atenção é calculada com a fórmula:

\[
\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
\]

Isso permite ao modelo aprender **quais partes da entrada são mais relevantes para cada posição**.

### 🔍 Exemplos:

- **BERT**: ao analisar a palavra "banco", pode focar na palavra "dinheiro" para entender que se refere a uma instituição financeira.
- **ViT**: ao processar um patch da imagem, pode focar em outros patches com padrões semelhantes.

---

## 🔹 2. Dropout

### 👉 O que é?
**Dropout** é uma técnica de **regularização** que ajuda a prevenir o **overfitting**.

### 📌 Como funciona?
Durante o **treinamento**, o Dropout **zera aleatoriamente uma porcentagem dos neurônios** em uma camada.

Isso obriga o modelo a aprender padrões mais robustos, ao invés de depender de caminhos específicos na rede.

### 📍 No contexto do BERT e ViT:

- Dropout é aplicado **após a atenção** e em outras partes da arquitetura (como o feed-forward).
- Dropout é **desligado durante a inferência** (avaliação ou produção).

---

## 🧠 Estrutura Comparativa: BERT vs Vision Transformer

| Componente         | BERT                            | Vision Transformer (ViT)          |
|--------------------|----------------------------------|-----------------------------------|
| Entrada            | Tokens de texto                 | Patches de imagem                 |
| Embeddings         | Word + Positional Embeddings    | Patch + Positional Embeddings     |
| Atenção            | Self-Attention                  | Self-Attention                    |
| Dropout            | Após atenção e FFN              | Após atenção e FFN                |

---

## ✅ Resumo

| Termo       | Função principal                                                   |
|-------------|---------------------------------------------------------------------|
| Attention   | Permitir o modelo focar nas partes mais relevantes da entrada      |
| Dropout     | Reduzir overfitting apagando neurônios aleatoriamente no treino    |

---

## 📊 Visualização da Atenção (Exemplo Simples)

### 🔠 Texto (BERT)

Frase: **"O gato está no telhado"**

Suponha que ao analisar "telhado", o modelo preste mais atenção em "está" e "gato":

```
Palavra:   O   gato  está   no  telhado
Atenção:   ░   ████  ███    ░      ██
```

### 🖼️ Imagem (ViT)

Uma imagem é dividida em **patches** e cada patch pode focar em outros relevantes:

```
Patch 1 ▓▒░
Patch 2 ███  <--- Foco principal
Patch 3 ░░▒
...
```

