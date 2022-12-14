# Visão Computacional: reconhecimento de texto com OCR e OpenCV.






### REGEX:

- Busca de informações:
```python
import re
horas = []
config_tesseract = "--tessdata-dir tessdata"
padrao_hora = '([01]?[0-9]|2[0-3]):[0-5][0-9](:[0-5][0-9])?'

img = cv2.imread('/content/text-recognize/Atividades/Aula4_cotacao.png')
rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
resultado = pytesseract.image_to_data(rgb, config=config_tesseract, lang="eng", output_type=Output.DICT)

img_copia = rgb.copy()
for i in range(0, len(resultado['text'])):
  confianca = int(resultado['conf'][i])
  if confianca > min_conf:
    texto = resultado['text'][i]
    if re.match(padrao_hora, texto):
      x, y, img = caixa_texto(resultado, img_copia, (0,0,255))
      horas.append(texto)
    else:
      x, y, img_copia = caixa_texto(resultado, img_copia)
cv2_imshow(img_copia)
```

### Cenários Naturais:

![image](https://user-images.githubusercontent.com/37785171/207730274-886e1424-47f7-4041-b612-efd8e38530fe.png)

### Métricas de avaliação:

Semelhante aos modelos de machine learning convencionais temos as métricas que podem ser utilizadas após a montagem da matriz de confusão e nos auxiliam a entender melhor sobre como nosso modelo está performando.

Dentro da nossa matriz de confusão ainda continuamos com os mesmos campos, de verdadeiros e falsos que podem ser positivos ou negativos, gerando nossas quatro categorias:

- Verdadeiro Positivo (VP): É quando o modelo categoriza corretamente uma imagem. Por exemplo, categorizar uma imagem de um gato como um gato.

- Falso Positivo (FP): Quando o modelo categoriza uma imagem quando não deveria. Por exemplo, categorizar uma imagem de um gato como um cachorro.

- Verdadeiro Negativo (VN): Ocasião na qual o modelo não categoriza corretamente uma imagem. Por exemplo, não categorizar uma imagem de um gato como um cachorro.

- Falso Negativo (FN): É quando o modelo não categoriza uma imagem, mas deveria. Por exemplo, não categorizar uma imagem de um gato como gato.

Um destaque especial é dado para os valores de Falsos Positivos (FP) que ocorrem quando a imagem tem mais classificações do que deveria, apresentando caixas a mais em lugares onde o objeto ou o texto não se encontra, que foi o caso da aula de Falsos Positivos.

Após termos os valores de VP, FP, VN e FN podemos medir a performance do nosso modelo com algumas métricas, como a Acurácia, Precisão e Recall (ou Sensibilidade - em português).

Sendo assim, temos que cada um destes itens significam, respectivamente:

- Acurácia: avalia a proporção de acertos em relação a todas as previsões realizadas. É obtida pelo quociente da soma dos valores de verdadeiros positivos e negativos por todos os outros valores previstos (VP, VN, FP, FN).

- Precisão: avalia a proporção de verdadeiros positivos dentre as predições dadas como positivas pelo modelo. É obtida dividindo os verdadeiros positivos pela soma das previsões positivas.

- Recall / Sensibilidade: avalia a proporção de verdadeiros positivos dentre todos os valores positivos reais. É obtida dividindo os verdadeiros positivos pela soma de positivos reais.

Além disso, outras métricas, tais como Taxa de Verdadeiros Positivos (TVP) e a Taxa de Falsos Positivos (TFP) também podem ser calculadas com base nos valores obtidos da matriz de confusão. Com os valores de TVP e TFP é possível fazer o gráfico utilizado para avaliar modelos de classificação, chamado de curva ROC

### Fotos em Cenários Naturais:

Durante a aula de Cenários naturais vimos que imagens que estão em ambientes que não conseguimos controlar as luzes, saturação, contraste, angulação e demais fatores são chamadas de imagens em cenários naturais e normalmente precisam de maiores tratamentos, pois trazem consigo alguns valores de Falsos Positivos, como foi o caso mostrado na caneca durante a aula sobre cenários naturais.

Outro caso que pode ocorrer em imagens em cenários naturais não tratadas devidamente é o que chamamos de Falsos Negativos, isto é, quando ela deveria achar o objeto (no nosso caso o texto) e não o encontra. Um exemplo de combinação de Falsos Positivos e Falsos Negativos na mesma imagem, quando não está tratada da forma correta, pode ser analisado abaixo:

![image](https://user-images.githubusercontent.com/37785171/207735491-4674200f-0417-4ace-a435-82ffb6b0e66c.png)

Depois de carregarmos a imagem e fazer a conversão de cores de BGR para RGB, temos uma placa de trânsito que antes era amarela mas agora está na cor azul e com letras pretas escrito REDUZA A VELOCIDADE.

Ao fundo dessa imagem podemos observar várias vegetações, como árvores e uma tubulação logo atrás da placa e o chão tem a grama alta, cobrindo boa parte de um dos pés da placa.

```python
img = cv2.imread('/content/text-recognize/Atividades/Aula4_placa.jpg')
rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
cv2_imshow(rgb)
```

O próximo passo é aplicar o PSM 6, que assume um único bloco uniforme de texto, definir o valor mínimo de confiança e também calcular o resultado do OSD, com todos os dados que temos da imagem.

```python
config_tesseract = '--tessdata-dir tessdata --psm 6'
min_conf = 40
resultado = pytesseract.image_to_data(rgb, lang="por", output_type=Output.DICT, config=config_tesseract)
```

Em seguida, vamos usar as funções `caixa_texto` e `escreve_texto` para fazer os nossos bounding boxes nas imagens e também escrever as palavras encontradas, que passam no mínimo de confiança declarado de 40%.

```python
img_copia = rgb.copy()
for i in range(0, len(resultado['text'])):
  confianca = int(resultado['conf'][i])
  if confianca > min_conf:
    x, y, img = caixa_texto(resultado, img_copia)
    texto = resultado['text'][i]
    #cv2.putText(img_copia, texto, (x, y - 10), cv2.FONT_HERSHEY_SIMPLEX, 1.1, (0,0,255))
    img_copia = escreve_texto(texto, x, y, img_copia, fonte)
cv2_imshow(img_copia)
```

![image](https://user-images.githubusercontent.com/37785171/207735734-e82d027f-b883-461e-a967-b1a184930832.png)

O resultado final dessa célula são vários retângulos pela imagem, alguns pela vegetação abaixo da placa e muitos na vegetação acima, no nível das árvores, ou seja, tivemos o caso onde o Falso Positivo e o Falso Negativo ocorreram ao mesmo tempo. Para casos como esse, métodos mais aprofundados de pré-processamento de imagens são necessários para que o Tesseract OCR foque na placa e não nos arredores.


