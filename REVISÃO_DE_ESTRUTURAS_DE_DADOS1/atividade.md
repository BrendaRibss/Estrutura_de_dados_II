Estrutura de Dados 1 

1. Vetores (Arrays):
- Um vetor é uma estrutura que armazena vários elementos do mesmo tipo em posições consecutivas.

Exemplo:

Índice:   0 1 2 3 4
Valor:   10 20 30 40 50 
A primeira posição geralmente é 0.
Acesso por índice é O(1).
Inserção/remoção no meio pode ser O(n), porque os elementos precisam ser deslocados.
Operações
A[2] → acessa o elemento na posição 2
A[0] → primeiro elemento
A[n-1] → último elemento

Vantagem: acesso rápido.
Desvantagem: tamanho geralmente fixo e inserções no meio são custosas.

2. Matrizes
- Uma matriz é um vetor de duas ou mais dimensões.

Exemplo 3×3:

[ 1  2  3 ]
[ 4  5  6 ]
[ 7  8  9 ]

Podemos acessar usando:

M[linha][coluna]

Por exemplo:

M[1][2] = 6
Matriz em memória

Normalmente, uma matriz é armazenada de forma linear na memória.

Ordem por linha (row-major):

1 2 3 4 5 6 7 8 9

3. Pilha (Stack)
- A pilha segue o princípio:
  - LIFO — Last In, First Out
    Último a entrar → primeiro a sair.

Imagine uma pilha de pratos:

     ┌───┐
     │ 3 │ ← sai primeiro
     ├───┤
     │ 2 │
     ├───┤
     │ 1 │
     └───┘
Principais operações

Push: coloca elemento.

push(4)

Pop: remove o elemento do topo.

pop()

Top/Peek: consulta o topo sem remover.

top()

Geralmente:

Operação	Complexidade
Push	O(1)
Pop	O(1)
Top	O(1)
Aplicações
Desfazer ações (Ctrl + Z)
Histórico de páginas
Chamadas de funções
Avaliação de expressões
Parênteses em expressões

4. Fila (Queue)
- A fila segue:
  - FIFO — First In, First Out
    Primeiro a entrar → primeiro a sair.

Como uma fila de pessoas:

ENTRADA → [ João ][ Maria ][ Pedro ] → SAÍDA
                                      ↑
                                   primeiro
Operações

Enqueue: adiciona no final.

enqueue(10)

Dequeue: remove do início.

dequeue()

Front: consulta o primeiro elemento.

front()

Geralmente:

Operação	Complexidade
Enqueue	O(1)
Dequeue	O(1)
Front	O(1)
Aplicações
Impressora
Atendimento
Processos de um sistema operacional
Filas de requisições

5. Bubble Sort 
- O Bubble Sort compara elementos vizinhos e troca quando estão na ordem errada.

Exemplo:

[5, 2, 4, 1]

Compara:

5 > 2 → troca

[2, 5, 4, 1]

Depois:

5 > 4 → troca

[2, 4, 5, 1]

Depois:

5 > 1 → troca

[2, 4, 1, 5]

O maior elemento vai "borbulhando" para o final.

Complexidade
Caso	Complexidade
Melhor	O(n)*
Médio	O(n²)
Pior	O(n²)

* Quando implementado com uma verificação para parar caso nenhuma troca tenha ocorrido.

Memória: O(1)

É simples, mas geralmente ineficiente para grandes quantidades de dados.

6. Selection Sort
- Procura o menor elemento e coloca na posição correta.

Exemplo:

[5, 3, 4, 1]

Procura o menor:

1

Troca com o primeiro:

[1, 3, 4, 5]

Depois procura o menor do restante.

Complexidade:

O(n²)

7. Insertion Sort
- Funciona como organizar cartas na mão.

Exemplo:

[5, 3, 4, 1]

Pega o 3 e coloca na posição correta:

[3, 5, 4, 1]

Depois 4:

[3, 4, 5, 1]

Depois 1:

[1, 3, 4, 5]

Complexidade:

Caso	Complexidade
Melhor	O(n)
Médio	O(n²)
Pior	O(n²)

É interessante quando os dados já estão quase ordenados.

13. Merge Sort

Divide o vetor em partes menores, ordena essas partes e depois junta tudo.

[8, 3, 5, 1]

       ↓

[8, 3] [5, 1]

       ↓

[8] [3] [5] [1]

       ↓

[3, 8] [1, 5]

       ↓

[1, 3, 5, 8]

Complexidade:

O(n log n)

É baseado na ideia de dividir para conquistar.

8. Quick Sort
- Escolhe um elemento chamado pivô e separa os elementos em relação a ele.

Exemplo:

[7, 2, 9, 4, 5]

Pivô:

5

Separa:

menores       maiores
[2, 4]   5    [7, 9]

Depois aplica o mesmo processo nas partes.

Complexidade média:

O(n log n)

Pior caso:

O(n²)
