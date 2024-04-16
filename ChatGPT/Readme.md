# ChatGPT

![image](https://github.com/RonnyldoSilva/Wiki-Ronnyldo/assets/37785171/905d4808-692a-4851-b2c9-caa2567d89ac)

Site Oficial: https://openai.com/blog/chatgpt

A OpenAI ainda oferece um plano pago, que garante acesso ao ChatGPT em horários de fluxo intenso, respostas mais rápidas, acesso prioritário a melhorias e novas funcionalidades implementadas. No entanto, o uso gratuito é suficiente para que o usuário utilize os recursos do chat como suporte no seu dia a dia. Para isso, basta clicar no botão “Try ChatGPT”, na página oficial, que vai redirecionar o seu navegador ao link direto da ferramenta. Na sequência, será necessário cadastrar o seu e-mail e senha, o que imediatamente libera o seu acesso ao prompt de mensagens do chat.

`Importante destacar: embora a interface do ChatGPT utilize o inglês como língua padrão, o usuário pode inserir textos em português sem que ocorram problemas na interação.`

O artigo [“What is ChatGPT doing… and why does it work?”](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/) também menciona o conceito de modelos, probabilidades, Machine Learning e treinamento de redes neurais, semântica e linguagem computacional, além de entrar em detalhes sobre a engenharia por trás do sistema do ChatGPT.

### AIs e o impacto no mercado de trabalho

No artigo [“Will AIs Take All Our Jobs and End Human History—or Not? Well, It’s Complicated…”](https://writings.stephenwolfram.com/2023/03/will-ais-take-all-our-jobs-and-end-human-history-or-not-well-its-complicated/) (em inglês), Stephen Wolfram argumenta que essa é uma questão complexa e que depende de vários fatores, incluindo a natureza do trabalho, a capacidade da AI de substituir humanos em determinadas tarefas e o papel que as pessoas desempenham no desenvolvimento e uso da tecnologia. Vale a pena a leitura do artigo para entender melhor esse debate.

## Refactor inefficient code

Better code is less prone to bugs and is easier to maintain, and the Azure OpenAI models can help guide developers on how to refactor their code.

Consider the following function.

```
def calculateTotalPrice(item, quantity):
    if item == 'apple':
        return quantity * 0.5
    elif item == 'banana':
        return quantity * 0.75
    elif item == 'orange':
        return quantity * 0.6
    else:
        return 0
```

This code calculates the total price of a particular item based on its name and quantity. However, the code isn't modular and can be difficult to maintain. When provided to the model with the request to refactor it, here's the response:

```
item_prices = {  
    'apple': 0.5,  
    'banana': 0.75,  
    'orange': 0.6  
}  

def calculate_total_price(item, quantity):  
    price = item_prices.get(item, 0)  
    return quantity * price
```

Along with the code, the model provides an explanation of the refactoring.

```
In this refactored code, we've created an object called itemPrices that maps item names to their 
prices. We've also simplified the calculateTotalPrice function by using the itemPrices object to look 
up the price of the item, rather than using a series of if/else statements. This makes the code more 
modular and easier to maintain, and also reduces the risk of introducing bugs in the future.
```
