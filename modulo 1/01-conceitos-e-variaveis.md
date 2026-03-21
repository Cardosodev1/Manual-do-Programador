## Módulo 1: Conceitos e Variaveis
Antes de escrever código, precisamos entender a lógica por trás das instruções. Este arquivo cobre os fundamentos de como um programa é estruturado e como ele armazena informações.

---

### 1. O que é um Algoritmo?
Um algoritmo é simplesmente uma **sequência de passos finitos e organizados** para resolver um problema ou executar uma tarefa.

* **Analogia:** Uma receita de bolo é um algoritmo. Se você seguir os passos na ordem errada ou pular uma etapa, o resultado final não será o esperado.
* **Software:** É um conjunto de algoritmos escritos para resolver problemas específicos ou tarefas complexas utilizando o computador.
* **O "Burro muito rápido":** O computador não tem "bom senso". Ele faz exatamente o que você manda, por isso as instruções precisam ser extremamente precisas.

---

### 2. O Ciclo de Vida da Informação (E-P-S)
Todo programa de computador, do mais simples ao mais complexo, segue este ciclo fundamental:

1.  **Entrada (Input):** Dados que o programa recebe (ex: o que você digita no teclado).
2.  **Processamento:** O que o computador faz com esses dados (ex: uma conta matemática).
3.  **Saída (Output):** O resultado apresentado ao usuário (ex: uma mensagem na tela).

---

### 3. Variáveis e Identificadores
Lembra da memória RAM no Módulo 0? Para processar dados, precisamos guardá-los em pedaços dessa memória. Usamos **Variáveis** para isso. Cada pedaço precisa de um nome, chamado de **Identificador**.

#### **Regras para Identificadores (Nomes de Variáveis):**
Para dar nome a uma variável, você deve seguir estas regras:

1. Deve começar sempre com uma letra (nunca com números).
2. Não pode conter espaços (use `salario_liquido` ou `salarioLiquido`).
3. Não pode conter caracteres especiais (acentos, ç, @, #), exceto o *underscore* `_`.
4. Não pode ser uma palavra reservada (nomes com significado pré-definido na sintaxe de uma linguagem de programação).

---

### 4. Tipos Primitivos de Dados
O computador reserva espaços diferentes na memória dependendo do que você vai guardar:

| Tipo | O que guarda | Exemplo |
| :--- | :--- | :--- |
| **Inteiro** | Números inteiros, positivos ou negativos. | `10`, `-5`, `0` |
| **Real** | Números com casas decimais. | `1.75`, `-10.50` |
| **Caractere** | Texto, letras ou símbolos (sempre entre "aspas"). | `"Guilherme"`, `"A"`, `"123"` |
| **Lógico** | Valores binários de verdadeiro ou falso. | `verdadeiro`, `falso` |

---

### 5. Anatomia de um Algoritmo
Todo algoritmo organizado (especialmente no padrão que usaremos para aprender, o *Portugol*) possui uma estrutura clara:

1.  **Cabeçalho:** O nome do algoritmo.
2.  **Área de Declaração:** Onde "reservamos" nossas variáveis (os espaços na memória RAM).
3.  **Corpo (Início e Fim):** Onde as instruções de ação realmente acontecem.

```text
algoritmo "NomeDoPrograma"
var
   // Aqui declaramos as variáveis (Ex: nome: caractere, numero: inteiro)
inicio
   // Aqui escrevemos os comandos (Ex: Escreva, Leia)
fimalgoritmo
```

---

### 6. Comandos Básicos
É como o programa interage com o usuário e guarda um valor dentro de uma variável.

* **Atribuição (`<-`):** Coloca um valor na variável. Ex: idade <- 25.
* **Entrada (`Leia`):** O computador pausa e espera o usuário digitar algo, guardando esse valor em uma variável.
* **Saída (`Escreva`):** Mostra algo para o usuário.
