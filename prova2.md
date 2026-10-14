# PROVA PRÁTICA DE ALGORITMOS E ESTRUTURAS DE DADOS

**Duração:** 1h30 (90 minutos)

**Valor total:** 25,00 pontos

**Linguagem sugerida:** C# (ou Java/C++ conforme a disciplina)

---

## CONTEXTO & REGRAS GERAIS

* **Restrição Obrigatória:** Proibido o uso de coleções/estruturas nativas da linguagem (ex: `List<T>`, `Stack<T>`, `Queue<T>`).
* **Ponteiros/Nó Cabeça:** Todas as estruturas dinâmicas/flexíveis **devem obrigatoriamente utilizar nó cabeça**.
* **Manipulação Limpa:** Não utilizar métodos de parada como `Console.ReadKey()` ao final da execução.

---

## QUESTÃO 1: Pilha Flexível — Validação e Inversão de Sentenças (8,0 Pontos)

Implemente uma **Pilha Flexível (dinâmica)** com nó cabeça que armazena caracteres (`char`). Em seguida, implemente um programa que leia uma sequência de caracteres contendo letras e símbolos de parênteses `(` e `)`.

O programa deve realizar duas operações usando a pilha:

1. **Verificação de Balanceamento (4,0 pts):** Validar se todos os parênteses `(` abertos foram devidamente fechados `)`.
2. **Inversão dos Caracteres Validados (4,0 pts):** Se a expressão estiver correta/balanceada, utilize a mesma estrutura de pilha para imprimir os caracteres alfabéticos da sentença na ordem inversa à que foram digitados. Se a expressão estiver desbalanceada, imprima apenas `Expressao Invalida`.

### Exemplo de Entrada e Saída:

* **Entrada 1:** `(A(B)C)`
* **Saída 1:**
```text
Status: Correta
Inverso: C B A

```




* **Entrada 2:** `(A(B)`
* **Saída 2:**
```text
Status: Expressao Invalida

```





---

## QUESTÃO 2: Fila Linear / Estática — Fila de Prioridade Atendimentos (8,0 Pontos)

Crie uma classe `Paciente` contendo os atributos:

* `string nome`
* `int idade`

Implemente uma **Fila Linear Circular (estática via vetor)** com capacidade máxima de 50 elementos para gerenciar o atendimento de uma clínica.

Implemente os métodos e funcionalidades no menu:

1. **Inserir (2,0 pts):** Adiciona um paciente no final da fila.
2. **Atender (2,0 pts):** Remove e imprime o paciente do início da fila.
3. **MoverIdososParaFrente (4,0 pts):** Método especial da fila que percorre os elementos e remaneja todos os pacientes com **idade >= 60 anos** para que fiquem no início da fila (mantendo a ordem relativa entre os idosos), sem perder os demais pacientes que ficarão logo atrás.

### Exemplo do Menu / Execução:

* **Entrada de Operações:**
```text
1 -> Ana (25 anos)
1 -> Carlos (70 anos)
1 -> Bruno (30 anos)
1 -> Maria (65 anos)
3 -> (Executa MoverIdososParaFrente)

```


* **Ordem da Fila após Opção 3:** `Carlos (70)` -> `Maria (65)` -> `Ana (25)` -> `Bruno (30)`

---

## QUESTÃO 3: Lista Dupla Flexível — Mídia e Controle de Navegação (9,0 Pontos)

Crie uma classe `Musica` com os atributos:

* `string titulo`
* `string artista`

Implemente uma **Lista Duplamente Encadeada (Flexível)** com nó cabeça. Além dos métodos tradicionais de inserção e remoção, adicione os seguintes métodos requeridos:

1. **`void InserirFim(Musica m)` (1,5 pts):** Insere uma nova música no final da lista.
2. **`Musica RemoverPorTitulo(string titulo)` (2,5 pts):** Busca e remove a primeira ocorrência do título informado, reencadeando os ponteiros anterior e próximo corretamente. Retorna o objeto removido ou `null` caso não exista.
3. **`void TocarPlaylistSequencial()` (2,5 pts):** Imprime todas as músicas da lista do início ao fim.
4. **`void TocarPlaylistInversa()` (2,5 pts):** Imprime todas as músicas do fim para o início navegando exclusivamente pelos ponteiros `ant` (anterior).

### Exemplo de Saída Esperada ao Listar:

```text
--- Playlist (Ordem Normal) ---
1. Titulo: Song A | Artista: Artist X
2. Titulo: Song B | Artista: Artist Y

--- Playlist (Ordem Inversa) ---
1. Titulo: Song B | Artista: Artist Y
2. Titulo: Song A | Artista: Artist X

```

---

## CRITÉRIOS DE AVALIAÇÃO

| Item | Pontuação |
| --- | --- |
| **Questão 1:** Lógica de Pilha Flexível + Validação + Inversão | 8,0 pts |
| **Questão 2:** Fila Circular Estática + Reorganização por Idade | 8,0 pts |
| **Questão 3:** Lista Dupla Flexível + Encadeamento Duplo + Métodos Específicos | 9,0 pts |
| **TOTAL** | **25,0 pts** |


