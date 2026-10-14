# PROVA PRÁTICA DE ALGORITMOS E ESTRUTURAS DE DADOS

**Duração:** 1h30 (90 minutos)

**Valor total:** 25,00 pontos

**Linguagem sugerida:** C# (ou Java/C++)

---

## CONTEXTO & REGRAS GERAIS

* **Restrição Obrigatória:** Proibido o uso de coleções/estruturas nativas da linguagem (ex: `List<T>`, `Stack<T>`, `Queue<T>`).
* **Critério de Avaliação Técnica:** Para cada questão, você deve escolher a estrutura de dados mais adequada (entre Pilha, Fila e Lista — Estática ou Flexível com Nó Cabeça) focando na **eficiência de tempo de execução** (Complexidade de Tempo $\mathcal{O}$). A escolha errada da estrutura ou uma solução ineficiente acarretará desconto na pontuação.
* **Manipulação Limpa:** Não utilizar métodos de parada como `Console.ReadKey()` ao final da execução.

---

## QUESTÃO 1: Histórico de Navegação "Voltar" e "Avançar" (8,0 Pontos)

Um navegador web precisa gerenciar o histórico de abas de um usuário. O sistema deve permitir:

1. `Visitar(url)`: Acessa uma nova página.
2. `Voltar()`: Retorna para a página anterior.
3. `Avancar()`: Caso o usuário tenha voltado, permite avançar para a página que estava antes de voltar.
4. `ExibirStatus()`: Exibe a página atual, a página anterior imediata (se houver) e a próxima página (se houver).

### Requisitos:

* Escolha e implemente a(s) estrutura(s) mais eficiente(s) em tempo para que as operações de navegação ocorram em **tempo constante $\mathcal{O}(1)$**.
* Justifique em um comentário no código o porquê da(s) estrutura(s) escolhida(s).

### Exemplo de Uso:

```text
Visitar("google.com")
Visitar("pucminas.br")
Visitar("canvas.pucminas.br")
Voltar() -> Atual: pucminas.br
Avancar() -> Atual: canvas.pucminas.br

```

---

## QUESTÃO 2: Triagem e Despacho de Processos Acadêmicos (8,0 Pontos)

A secretaria de uma faculdade recebe solicitações acadêmicas continuamente ao longo do dia. O atendimento funciona rigorosamente por ordem de chegada:

1. `AdicionarSolicitacao(id, descricao)`: Cadastra um novo processo na fila de espera.
2. `AtenderProximo()`: Remove e processa a solicitação há mais tempo na espera.
3. `UrgenciaCoordenacao(id, descricao)`: Fato extraordinário em que o coordenador insere um processo que deve ser atendido antes de todos os outros que já estão aguardando.

### Requisitos:

* Escolha e implemente a estrutura de dados que garanta tempo **$\mathcal{O}(1)$ tanto para inserção normal/urgente quanto para a remoção**.
* Não é permitido reordenar ou deslocar elementos em vetor (evitar custos $\mathcal{O}(n)$).
* Justifique em um comentário no código a escolha da estrutura.

---

## QUESTÃO 3: Ranking Dinâmico de Pontuação (9,0 Pontos)

Um sistema de jogos mantém a pontuação de jogadores cadastrados contendo `string Nome` e `int Pontos`. O sistema precisa realizar as seguintes operações com frequência:

1. `InserirJogador(nome, pontos)`: Adiciona um jogador na posição correta mantendo a lista **ordenada do maior para o menor ponto**.
2. `AtualizarPontos(nome, novosPontos)`: Busca o jogador pelo nome, atualiza sua pontuação e ajusta sua posição na estrutura para manter a ordenação.
3. `ExibirRanking()`: Imprime os jogadores do 1º ao último colocado e, em seguida, do último ao 1º colocado de forma eficiente.

### Requisitos:

* Escolha a estrutura mais adequada para permitir a travessia em ambos os sentidos sem necessidade de estruturas auxiliares ou recursão.
* Justifique em um comentário a complexidade de tempo do método `InserirJogador` e `AtualizarPontos`.

---

## CRITÉRIOS DE AVALIAÇÃO

| Item | Pontuação |
| --- | --- |
| **Questão 1:** Escolha adequada da estrutura + Eficiência $\mathcal{O}(1)$ + Lógica de navegação | 8,0 pts |
| **Questão 2:** Escolha adequada + Operações em $\mathcal{O}(1)$ sem deslocamentos desnecessários | 8,0 pts |
| **Questão 3:** Escolha adequada + Manutenção da ordem + Travessia bidirecional + Análise de complexidade | 9,0 pts |
| **TOTAL** | **25,0 pts** |
