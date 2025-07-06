# Vision Transformer (ViT) — Como funciona e Casos de Uso

## 🧠 Como o ViT funciona — Visão geral rápida

| Etapa | O que acontece | Por quê isso importa |
|-------|----------------|----------------------|
| **1. Fatiar a imagem em “patches”** | A imagem \(H \times W\) é dividida em blocos fixos (ex. 16 × 16 px). Cada patch é achatado em um vetor. | Permite tratar a imagem como uma “sequência” — o mesmo formato que o Transformer usa para palavras. |
| **2. Projeção linear** | Cada vetor‑patch passa por uma camada linear (peso compartilhado) que o leva a um espaço de dimensão \(D\) (ex. 768). | Equivale ao *embedding* de palavras em NLP. |
| **3. Adição dos embeddings de posição** | Um vetor fixo ou aprendido é somado a cada patch‑token. | Transforma a sequência em algo “ordenado” — o modelo sabe qual patch veio de onde. |
| **4. Token especial `[CLS]`** | Um token extra é inserido à frente da sequência. Ele vai concentrar a “visão geral” da imagem. | Depois do encoder, o vetor `[CLS]` vira a representação global para classificação ou outras tarefas. |
| **5. Encoder Transformer** | Camadas empilhadas de **Multi‑Head Self‑Attention + MLP** com *LayerNorm* e *Dropout*. | Assim como no BERT, cada token presta atenção em todos os outros, mas aqui os “palavras” são patches de imagem. |
| **6. Cabeça de saída** | ‑ **Classificação**: MLP sobre `[CLS]`.  <br>‑ **Detecção / Segmentação**: heads extras (ex. DETR, Mask2Former). | O mesmo backbone ViT serve para várias tarefas — muda só a cabeça. |

> **Intuição‑chave:** Ao contrário dos CNNs, o ViT não usa convoluções locais: ele aprende relações **globais** logo no começo. Isso o torna muito flexível, mas exige dados (ou pré‑treino) para generalizar bem.

---

## ⚖️ Pontos fortes vs fracos

| Pontos fortes | Pontos fracos |
|---------------|---------------|
| Capta dependências **longas** desde a 1ª camada. | Self‑attention quadrática → alto custo computacional. |
| **Transfer learning** simples: basta trocar a cabeça. | Precisa de **muito dado** (ou pré‑treino em JFT/Imagenet‑21k). |
| Arquitetura unificada com NLP → fácil para multimodal. | Menos interpretável que filtros de CNN. |

---

## 🚀 Casos de uso onde ViT brilha

| Categoria | Exemplos práticos |
|-----------|------------------|
| **Classificação de imagem** | Inspeção de defeitos, raio‑x, espécies animais, etc. |
| **Detecção / Segmentação** | Usado em DETR, Mask2Former, Segmenter. |
| **Visão + Texto (Multimodal)** | CLIP, BLIP, etc. — busca de imagens por texto. |
| **Vídeo** | TimeSformer, ViViT — detecção de ações. |
| **Self-supervised Learning** | MAE, DINO, SimMIM — ideal para domínios com pouco rótulo. |
| **Geração / Difusão** | Stable Diffusion, U‑ViT. |
| **Ciência / Pesquisa** | Microscopia, imagens médicas, astronomia, etc. |

---

## ❌ Quando **não** usar

- Poucos dados + pouca GPU → CNNs pré‑treinadas performam melhor.
- Aplicações em tempo real com RAM limitada.
- Tarefas onde o detalhe local é mais importante que o contexto global.

---

## ✅ Boas práticas de uso

1. Use pesos **pré‑treinados** (`timm`, `huggingface`).
2. Aumente resolução (ex: 224px → 384px) no fine‑tuning.
3. Regularização com `DropPath`, `WeightDecay`.
4. Use **data augmentation pesado**: RandAugment, CutMix, Mixup.
5. Se faltar memória, opte por **variantes leves**: ViT‑tiny, Swin, DeiT.

---

## TL;DR

Vision Transformers dividem imagens em **patches**, processam como sequência via **self-attention** e entendem contextos **globais** rapidamente. São ótimos para classificação, detecção, segmentação e multimodalidade — desde que haja dados e hardware. Para cenários leves ou muito locais, CNNs ainda reinam.
