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

-----------------------------------------------------------------------------------------------------------------------------

Exercício feito usando C, que armazena os dados de casa aluno
#include <stdio.h> #include <stdbool.h>

//Exercício feito usando C, que armazena os dados de casa aluno


struct Aluno { char Nome[30]; int Idade; char Sexo; float Notas[3]; bool Aprovado; };

int main() {

float MediaAprov;
int QtdAlunos;

// Vetor para armazenar até 100 alunos
struct Aluno Alunos[100];

int aprovMasculino = 0;
int aprovFeminino = 0;
float SomaTurma = 0;

// Solicita a média mínima para que o aluno receba a aprovação

printf("Informe a media de aprovacao: ");
scanf("%f", &MediaAprov);

// Solicita a quantidade de alunos
printf("Informe a quantidade de alunos: ");
scanf("%i", &QtdAlunos);

// Cadastro dos alunos
for (int i = 0; i < QtdAlunos; i++) {

    printf("\nAluno %d\n", i + 1);

    printf("Nome: ");
    scanf("%s", Alunos[i].Nome);

    printf("Idade: ");
    scanf("%d", &Alunos[i].Idade);

    printf("Sexo (M/F): ");
    scanf(" %c", &Alunos[i].Sexo);

    // Cadastro das três notas
    for (int j = 0; j < 3; j++) {
        printf("Nota %d: ", j + 1);
        scanf("%f", &Alunos[i].Notas[j]);
    }

    // Calcula a média do aluno
    float media = (Alunos[i].Notas[0] +
                   Alunos[i].Notas[1] +
                   Alunos[i].Notas[2]) / 3;

    // Soma as médias para calcular a média da turma
    SomaTurma += media;

    // Verifica se o aluno foi aprovado
    if (media >= MediaAprov) {

        Alunos[i].Aprovado = true;

        // Conta alunos e alunas aprovados
        if (Alunos[i].Sexo == 'M') {
            aprovMasculino++;
        } else if (Alunos[i].Sexo == 'F') {
            aprovFeminino++;
        }

    } else {
        Alunos[i].Aprovado = false;
    }
}

// Calcula a média da turma
float MediaTurma = SomaTurma / QtdAlunos;

printf("\nMedia da turma: %.2f\n", MediaTurma);

printf("\nQuantidade de alunos aprovados: %d\n", aprovMasculino);
printf("Quantidade de alunas aprovadas: %d\n", aprovFeminino);

// Mostra os alunos aprovados
printf("\n--- ALUNOS APROVADOS ---\n");

for (int i = 0; i < QtdAlunos; i++) {
    if (Alunos[i].Aprovado) {
        printf("%s\n", Alunos[i].Nome);
    }
}

// Mostra os alunos reprovados
printf("\n--- ALUNOS REPROVADOS ---\n");

for (int i = 0; i < QtdAlunos; i++) {
    if (!Alunos[i].Aprovado) {
        printf("%s\n", Alunos[i].Nome);
    }
}

return 0;
}
