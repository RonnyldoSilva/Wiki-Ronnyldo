# Roadmap de Estruturas de Dados para Entrevistas no Google

---

### Etapa 1: Fundamentos Essenciais (Revisão e Consolidação)

Antes de mergulhar em estruturas mais complexas, certifique-se de que seus fundamentos estão sólidos.

* **Complexidade de Tempo e Espaço (Big O Notation):**
    * Entenda como calcular a complexidade de algoritmos (melhor, médio, pior caso).
    * Domine os principais Big O's: $O(1)$, $O(\log n)$, $O(n)$, $O(n \log n)$, $O(n^2)$, $O(2^n)$, $O(n!)$.
    * **Recursos:** Khan Academy, GeeksforGeeks, livros como "Cracking the Coding Interview".
* **Arrays e Strings:**
    * Operações básicas: acesso, inserção, remoção.
    * Manipulação de strings: substrings, concatenação, inversão, palíndromos.
    * Problemas comuns: two-pointers, sliding window.
* **Listas Encadeadas (Linked Lists):**
    * Tipos: simples, duplas, circulares.
    * Operações: inserção, remoção, busca, inversão.
    * Problemas: detectar ciclos, encontrar o k-ésimo elemento do final.
* **Pilhas (Stacks) e Filas (Queues):**
    * Conceitos: LIFO (Stack), FIFO (Queue).
    * Implementações: usando arrays ou linked lists.
    * Aplicações: balanceamento de parênteses, BFS (Breadth-First Search) para filas.

---

### Etapa 2: Estruturas de Dados Avançadas e Árvores

Aqui começam as estruturas mais frequentemente cobradas em entrevistas de alto nível.

* **Hash Maps / Hash Tables (Dicionários/Mapas):**
    * Funcionamento interno: hashing, resolução de colisões.
    * Vantagens e desvantagens.
    * Aplicações: contagem de frequências, cache, verificação de duplicatas.
* **Árvores (Trees):**
    * **Árvores Binárias (Binary Trees):** Conceitos básicos, travessias (pré-ordem, in-ordem, pós-ordem).
    * **Árvores Binárias de Busca (Binary Search Trees - BSTs):** Inserção, remoção, busca. Equilíbrio de BSTs (conceito de árvores auto-balanceadas como AVL, Red-Black Trees - não precisa saber implementar, mas entenda o conceito).
    * **Heaps (Max-Heap, Min-Heap):**
        * Implementação baseada em array.
        * Operações: `insert`, `extract-min`/`extract-max`, `heapify`.
        * Aplicações: filas de prioridade, Heap Sort.
* **Grafos (Graphs):**
    * Representações: lista de adjacências, matriz de adjacências.
    * Tipos: direcionado, não direcionado, ponderado, cíclico, acíclico.
    * **Algoritmos de Travessia:** BFS (Breadth-First Search) e DFS (Depth-First Search).
    * Aplicações: encontrar caminhos, componentes conectados.

---

### Etapa 3: Algoritmos e Otimização

As estruturas de dados raramente vêm sozinhas; elas são a base para algoritmos eficientes.

* **Algoritmos de Ordenação (Sorting Algorithms):**
    * Entender os principais: Merge Sort, Quick Sort, Heap Sort.
    * Saber as complexidades de tempo e espaço e quando usar cada um.
    * Bubble Sort, Selection Sort, Insertion Sort (entender, mas não focar em otimização).
* **Busca Binária (Binary Search):**
    * Aplicável em arrays ordenados.
    * Variações: encontrar o primeiro/último ocorrência, teto/piso.
* **Programação Dinâmica (Dynamic Programming - DP):**
    * Reconhecer problemas que podem ser resolvidos com DP.
    * Memoização e Tabulação.
    * Problemas clássicos: mochila, sequência mais longa comum, fibonacci.
* **Algoritmos Gulosos (Greedy Algorithms):**
    * Reconhecer problemas onde a escolha localmente ótima leva a uma solução globalmente ótima.

---

### Etapa 4: Resolução de Problemas Práticos e Plataformas Online

Este é o coração da sua preparação. O conhecimento teórico só se solidifica com a prática.

* **Plataformas de Coding:**
    * **LeetCode:** Indispensável. Comece com problemas "Easy" e avance para "Medium". Priorize os tópicos que você está estudando.
    * **HackerRank:** Boa para começar com problemas mais simples e desafios de estruturas de dados.
    * **InterviewBit:** Foco em problemas de entrevista.
* **Estratégia de Resolução de Problemas:**
    1.  **Entenda o Problema:** Leia cuidadosamente, faça perguntas, entenda as entradas e saídas.
    2.  **Exemplos:** Crie exemplos pequenos e trace o passo a passo manualmente.
    3.  **Abordagem Brute-Force:** Pense na solução mais simples, mesmo que ineficiente.
    4.  **Otimização:** Como você pode melhorar a complexidade de tempo/espaço? É aqui que as estruturas de dados entram.
    5.  **Codifique:** Escreva seu código.
    6.  **Teste:** Teste com seus exemplos e casos de borda.
    7.  **Análise:** Analise a complexidade final do seu algoritmo.
* **Padrões de Problemas Comuns:**
    * Two Pointers
    * Sliding Window
    * Backtracking
    * Union-Find (Disjoint Set Union)
    * Prefix Sum

---

### Recursos Adicionais e Dicas Importantes

* **Livro "Cracking the Coding Interview" (Gayle Laakmann McDowell):** Um clássico. Embora não seja apenas sobre estruturas de dados, ele tem uma excelente seção sobre o tema e muitos problemas práticos.
* **Cursos Online:**
    * Udemy, Coursera: Procure cursos específicos sobre estruturas de dados e algoritmos.
    * MIT OpenCourseware: O curso "Introduction to Algorithms" (6.006) é excelente.
* **Artigos e Blogs:** GeeksforGeeks, HackerEarth, Medium.
* **Escolha uma Linguagem:** Python, Java ou C++ são as mais comuns em entrevistas. Python é frequentemente preferido pela sua sintaxe concisa, que permite focar mais na lógica do algoritmo. Certifique-se de estar confortável com as estruturas de dados nativas da sua linguagem (listas, dicionários/maps, sets, etc.).
* **Pratique a Comunicação:** Durante a entrevista, não é só sobre resolver o problema. Explique seu raciocínio, discuta as trade-offs das suas escolhas e pense em voz alta.

---

### Cronograma Sugerido (Flexível)

* **Semanas 1-2:** Fundamentos (Big O, Arrays, Strings, Linked Lists, Stacks, Queues). Muitos problemas "Easy" no LeetCode.
* **Semanas 3-4:** Hash Maps, Binary Trees (BSTs, travessias). Comece com problemas "Medium" relacionados.
* **Semanas 5-6:** Heaps, Grafos (BFS, DFS). Mais problemas "Medium".
* **Semanas 7-8:** Algoritmos de Ordenação, Busca Binária, Programação Dinâmica, Greedy. Problemas "Medium" e alguns "Hard" de DP.
* **Semanas 9 em diante:** Revisão geral, prática intensiva em LeetCode (focando em problemas do Google ou similares), simulações de entrevista.

---
