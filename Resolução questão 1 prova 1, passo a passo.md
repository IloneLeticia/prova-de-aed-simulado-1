Aqui está a solução e explicação passo a passo da Questão 1 da Primeira Prova (Pilha Flexível — Validação e Inversão de Sentenças), estruturada de forma direta e objetiva.
1. Lógica e Estrutura da Solução
Para resolver o problema, precisamos de:
 * Classe CelulaChar e PilhaFlexivelChar: Estrutura dinâmica simples com nó cabeça para armazenar caracteres (char).
 * Validação de Balanceamento:
   * Percorremos a expressão caracter por caracter.
   * Ao encontrar (, empilhamos (Inserir/Push).
   * Ao encontrar ), desempilhamos (Remover/Pop). Se a pilha estiver vazia nesse momento, a expressão é inválida.
   * Ao final da leitura, se a pilha não estiver vazia, significa que sobrou ( sem fechar (expressão inválida).
 * Inversão da Sentença:
   * Se estiver balanceada, percorremos a string novamente empilhando apenas as letras/caracteres alfabéticos.
   * Em seguida, desempilhamos todos até a pilha esvaziar, garantindo a ordem inversa (LIFO — Last In, First Out).
2. Código da Estrutura (Pilha Flexível com Nó Cabeça)
using System;

public class CelulaChar
{
    public char Elemento { get; set; }
    public CelulaChar Prox { get; set; }

    public CelulaChar(char elemento = '\0')
    {
        Elemento = elemento;
        Prox = null;
    }
}

public class PilhaFlexivelChar
{
    private CelulaChar topo;

    public PilhaFlexivelChar()
    {
        // Nó cabeça
        topo = new CelulaChar();
    }

    public void Inserir(char x)
    {
        CelulaChar tmp = new CelulaChar(x);
        tmp.Prox = topo.Prox;
        topo.Prox = tmp;
    }

    public char Remover()
    {
        if (topo.Prox == null)
            throw new Exception("Erro: Pilha Vazia!");

        CelulaChar tmp = topo.Prox;
        char elemento = tmp.Elemento;
        topo.Prox = tmp.Prox;
        tmp.Prox = null;
        return elemento;
    }

    public bool Vazia()
    {
        return topo.Prox == null;
    }
}

3. Resolução Principal (Passo a Passo da Questão)
public class Program
{
    public static void Main()
    {
        string expressao = "(A(B)C)";

        if (ValidarEInverter(expressao) == false)
        {
            Console.WriteLine("Status: Expressao Invalida");
        }
    }

    public static bool ValidarEInverter(string expr)
    {
        PilhaFlexivelChar pilhaValidacao = new PilhaFlexivelChar();

        // PASSO 1: Verificação de Balanceamento dos Parênteses
        for (int i = 0; i < expr.Length; i++)
        {
            if (expr[i] == '(')
            {
                pilhaValidacao.Inserir('(');
            }
            else if (expr[i] == ')')
            {
                if (pilhaValidacao.Vazia())
                    return false; // Tentou fechar sem nenhum '(' aberto

                pilhaValidacao.Remover();
            }
        }

        // Se sobrou '(', a expressão está desbalanceada
        if (!pilhaValidacao.Vazia())
            return false;

        // PASSO 2: Inversão dos Caracteres Alfabéticos
        PilhaFlexivelChar pilhaInversao = new PilhaFlexivelChar();

        for (int i = 0; i < expr.Length; i++)
        {
            if (char.IsLetter(expr[i]))
            {
                pilhaInversao.Inserir(expr[i]);
            }
        }

        // Exibição do Resultado
        Console.WriteLine("Status: Correta");
        Console.Write("Inverso: ");

        while (!pilhaInversao.Vazia())
        {
            Console.Write(pilhaInversao.Remover() + " ");
        }
        Console.WriteLine();

        return true;
    }
}

4. Explicação do Fluxo de Execução
 * Entrada (A(B)C):
   * Encontra ( \rightarrow Empilha (.
   * Lê A \rightarrow Ignora na validação.
   * Encontra ( \rightarrow Empilha (.
   * Lê B \rightarrow Ignora na validação.
   * Encontra ) \rightarrow Desempilha um (.
   * Lê C \rightarrow Ignora na validação.
   * Encontra ) \rightarrow Desempilha o outro (.
   * Fim da string \rightarrow Pilha de validação vazia \rightarrow Validação OK.
 * Inversão de (A(B)C):
   * Empilha A, depois B, depois C.
   * Desempilha tudo \rightarrow Imprime: C B A.
   * 
