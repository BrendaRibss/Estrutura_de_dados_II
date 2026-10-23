# Caderno do Estudante
# Projeto ConectaUDF: redes sociais com grafos
**Disciplina:** Algoritmos / Matemática Discreta / Ciência de Dados
**Aluna:** Brenda Ribeiro dos Santos  RGM: 43650287
## 1. O desafio
Você faz parte da equipe que analisa a rede social fictícia **ConectaUDF**. Sua missão é representar as amizades em um grafo, realizar cálculos e usar Python para interpretar a estrutura da rede.

## 2. Conceitos essenciais
- **Vértice (ou nó):** representa um usuário.
- **Aresta:** representa uma amizade entre dois usuários.
- **Grau:** quantidade de conexões diretas de um usuário.
- **Caminho:** sequência de usuários em que cada par consecutivo está conectado.
- **Densidade:** proporção entre as amizades existentes e todas as amizades possíveis.

Neste projeto, a amizade é recíproca. Portanto, usamos um **grafo não direcionado**.

## 3. Conheça os usuários
| Código | Usuário |
|---|---|
| A | Ana |
| B | Bruno |
| C | Carla |
| D | Diego |
| E | Elisa |
| F | Felipe |

As amizades são:
1. Ana — Bruno
2. Ana — Carla
3. Bruno — Carla
4. Bruno — Diego
5. Carla — Elisa
6. Diego — Elisa
7. Diego — Felipe
8. Elisa — Felipe

## 4. Passo a passo: desenhe o grafo
1. Desenhe seis círculos, um para cada usuário.
2. Escreva o nome de cada pessoa dentro do círculo.
3. Para cada amizade da lista, desenhe uma linha entre os dois usuários.
4. Não desenhe duas linhas para a mesma amizade.
5. Confira se todas as oito amizades aparecem.

**Espaço para o seu desenho:** 
<img width="426" height="377" alt="Captura de tela 2026-10-23 131114" src="https://github.com/user-attachments/assets/3b3161ff-7642-4781-8f80-a2135b4831d3" />


## 5. Passo a passo: calcule o grau
Conte quantas linhas chegam a cada círculo. Registre o resultado.

| Usuário | Amigos diretos | Grau |
|---|---|---:|
| Ana    | Bruno e Carla         | 2 |
| Bruno  | Ana, Carla e Diego    | 3 |
| Carla  | Ana, Bruno e Elisa    | 3 |
| Diego  | Bruno, ELisa e Felipe | 3 |
| Elisa  | Carla,Diego e Felipe  | 3 |
| Felipe | Diego e Elisa         | 2 |

**Pergunta 1:** quem tem mais conexões diretas?  
Resposta: Bruno, Carla, Diego e ELisa possuem o maior grau, pois cada um tem ligação direta com três amigos.

## 6. Passo a passo: calcule o número de amizades
Some todos os graus. Como cada amizade conecta dois usuários, cada aresta é contada duas vezes.

**Fórmula:**  
`Número de arestas = soma dos graus ÷ 2`

1. Soma dos graus: 16
2. Divida por 2: 16 ÷ 2 = 8
3. Quantas amizades existem no grafo? 8

## 7. Passo a passo: calcule a densidade
A densidade compara as amizades existentes com o total de amizades possíveis.

Para um grafo simples não direcionado:

`D = 2 × E / (V × (V − 1))`

Em que:
- `D` = densidade;
- `E` = número de arestas;
- `V` = número de vértices.

Substitua os valores:
`D = 2 × 8 / (6 × (6 − 1))`

Resultado decimal: 16/30  = 0,53
Resultado percentual: 53,3% %

**Interprete:** a rede tem poucas ou muitas das conexões possíveis? Representa uma quantidade média das relações de amizade que podem existir dentro deste exemplo, uma vez que cada indivíduo faz 2 ou mais conexões, mas há espaço para que mais conexões existam entre as pessoas existentes no exemplo. 

________________________________________________________________

## 8. Passo a passo: represente o grafo em Python
A lista de adjacência registra, para cada usuário, os nomes de seus amigos. Digite o código em Python (por exemplo, no Google Colab ou em outro ambiente disponível).

```python
rede = {
    "Ana": ["Bruno", "Carla"],
    "Bruno": ["Ana", "Carla", "Diego"],
    "Carla": ["Ana", "Bruno", "Elisa"],
    "Diego": ["Bruno", "Elisa", "Felipe"],
    "Elisa": ["Carla", "Diego", "Felipe"],
    "Felipe": ["Diego", "Elisa"]
}

# Quantidade de usuarios
n = len(rede)

# Calcule o grau de cada usuario
for usuario, amigos in rede.items():
    print(usuario, "tem", len(amigos), "conexoes")

# A soma dos graus conta cada amizade duas vezes
soma_graus = sum(len(amigos) for amigos in rede.values())
arestas = soma_graus // 2

print("Total de usuarios:", n)
print("Total de amizades:", arestas)

# Densidade do grafo
densidade = (2 * arestas) / (n * (n - 1))
print(f"Densidade: {densidade:.2%}")
```

### Entenda o código
1. `rede` guarda os usuários e suas listas de amigos.
2. `len(rede)` conta os usuários.
3. `len(amigos)` calcula o grau de cada usuário.
4. `sum(...)` soma os graus.
5. `// 2` divide a soma por dois para contar cada amizade uma única vez.
6. A fórmula final calcula a densidade.

## 9. Passo a passo: encontre um caminho
Encontre um caminho de Ana até Felipe. Cada passagem por uma linha corresponde a uma aresta.

Exemplo de registro:
`Ana → Bruno → Diego → Felipe`

- Quantas arestas há no caminho? 3
- Você encontrou outro caminho com a mesma quantidade de arestas? Qual? Ana → Carlos → Elisa → Felipe

________________________________________________________________

## 10. Desafio em grupo
Amplie a rede social:
<img width="486" height="428" alt="Captura de tela 2026-10-23 133641" src="https://github.com/user-attachments/assets/c2973f57-d333-4ba5-accf-ceb766276110" />

1. Adicione pelo menos quatro usuários fictícios.
2. Crie no mínimo cinco novas amizades.
3. Atualize a lista de adjacência no Python.
rede = {
    "Ana": ["Bruno", "Carla", "Gabriela"],
    "Bruno": ["Ana", "Carla", "Diego", "Heitor"],
    "Carla": ["Ana", "Bruno", "Elisa", "Isabela"],
    "Diego": ["Bruno", "Elisa", "Felipe"],
    "Elisa": ["Carla", "Diego", "Felipe"],
    "Felipe": ["Diego", "Elisa", "Joao"],
    "Gabriela": ["Ana", "Heitor"],
    "Heitor": ["Bruno", "Gabriela"],
    "Isabela": ["Carla", "Joao"],
    "Joao": ["Felipe", "Isabela"]
}

4. Recalcule os graus, o total de arestas e a densidade.

| Usuário | Amigos diretos | Grau |
| Ana    |	Bruno, Carla e Gabriela	    |3
| Bruno  |	Ana, Carla, Diego e Heitor	|4
| Carla  |	Ana, Bruno, Elisa e Isabela	|4
| Diego  |	Bruno, Elisa e Felipe	    |3
| Elisa  |	Carla, Diego e Felipe	    |3
| Felipe |	Diego, Elisa e João	        |3
|Gabriela|	Ana e Heitor	            |2
| Heitor |	Bruno e Gabriela	        |2
| Isabela| 	Carla e João	            |2
| João   |	Felipe e Isabela	        |2

- Total de usuários: 10
- Total de amizades: 14
- Soma dos graus: 28
- Densidade decimal: 0,3111
- Densidade percentual: 31,11%
  
5. Compare a densidade antes e depois da ampliação: A densidade diminuiu pois o número de conexões possíveis aumentou de 15 para 45, pois isso houve uma diminuição proporcional na porcentagem de novas possibilidades de conexões.
6. Identifique os usuários com mais conexões: Bruno e Carla, os dois com 4 conexões.
7. Explique como a rede poderia recomendar uma nova amizade: A rede poderia recomedar para todos perfis que tem amizade com alguém que é seguido por uma das pessoas do ciclo de amizade descrito no grafo, para que por meio de conexões a parte eles conseguissem conhecer outras pessoas. Como é feito no instagra, por exemplo.

## 11. Entrega
Entregue:
- desenho do grafo;
- tabela com os graus;
- cálculos de arestas e densidade;
- código Python executável;
- respostas às perguntas e breve conclusão.

## 12. Pergunta de reflexão
Duas pessoas ainda não são amigas, mas têm três amigos em comum. Como essa informação poderia ser usada para sugerir uma nova conexão? Quais cuidados de privacidade devem ser considerados ao analisar redes sociais?

A rede social poderia sugerir amizade entre essas duas pessoas, já que elas têm três amigos em comum. Mas é importante respeitar a privacidade de cada um, protegendo seus dados e deixando cada pessoa escolher quem pode ver suas informações.
