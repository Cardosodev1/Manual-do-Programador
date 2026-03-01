# Módulo 1.3: Estruturas Condicionais (Seleção)
Até agora, nossos algoritmos seguiam uma linha reta do início ao fim. As **Estruturas Condicionais** permitem que o programa tome caminhos diferentes baseados em condições, dando "inteligência" ao código.

---

### 1. O Conceito de Seleção
Uma estrutura condicional avalia uma expressão lógica (Verdadeiro ou Falso) para decidir qual bloco de instruções executar.

* **Se a condição for verdadeira:** O bloco de código é executado.
* **Se a condição for falsa:** O programa pula esse bloco ou segue por um caminho alternativo.

---

### 2. Tipos de Condicionais

Nesta seção, exploramos as quatro formas principais de organizar a tomada de decisão em um algoritmo.

#### **A. Condicional Simples**
É a forma mais básica. O programa executa uma ação **apenas se** a condição for atendida. Se não for, ele simplesmente continua o fluxo normal.

```text
  se (condição) entao
     // instrução executada se verdadeiro
  fimse
```

#### **B. Condicional Composta**
Oferece um caminho alternativo caso a condição seja falsa. O programa faz a "Ação A" ou faz a "Ação B".

```text
se (condição) entao
  // caminho verdadeiro
senao
  // caminho falso
fimse
```

#### **C. Condicionais Aninhadas**
Quando uma decisão depende de outra, colocamos uma estrutura dentro da outra. Isso é útil para verificar múltiplas faixas de valores (ex: notas de um aluno).

```text
se (condição1) entao
  // ...
senao
  se (condição2) entao
    // ...
  senao
    // ...
  fimse
fimse
```

#### **D. Estrutura de Escolha (Seleção Múltipla)**
Ideal para quando uma variável pode assumir vários valores fixos (como um menu). É muito mais legível que vários "se/senao" seguidos.

```text
escolha (variável)
  caso valor1
    // ...
  caso valor2
    // ...
  outrocaso
    // caso nenhum valor acima bata
fimescolha
```

---

### 5. Exemplos Práticos

#### **Exemplo 1: Par ou Ímpar (Condicional Composta)**
```text
algoritmo "ParOuImpar"
var
   n: inteiro
inicio
   Escreva("Digite um número: ")
   Leia(n)
   se (n % 2 = 0) entao
      Escreva("O número é PAR.")
   senao
      Escreva("O número é ÍMPAR.")
   fimse
fimalgoritmo
```
O programa lê o número e calcula o resto da divisão por 2 (usando o operador `%`). Se o resto for igual a zero, a condição é **verdadeira** e ele executa o bloco `entao` imprimindo "PAR".
Caso contrário, ele pula para o `senao` e informa que o número é "ÍMPAR".

#### **Exemplo 2: Classificação de IMC (Condicionais Aninhadas)**
```text
algoritmo "CalculoIMC"
var
   m, a, imc: real
inicio
   Leia(m, a)
   imc <- m / (a ^ 2)
   se (imc < 18.5) entao
      Escreva("Abaixo do peso")
   senao
      se (imc >= 18.5) e (imc < 25) entao
         Escreva("Peso ideal")
      senao
         Escreva("Sobrepeso")
      fimse
   fimse
fimalgoritmo
```
O algoritmo calcula o IMC e inicia uma verificação em camadas. Primeiro testa se é "Abaixo do peso". Se não for, ele entra no `senao` onde existe **outro teste** para verificar se é "Peso ideal".
Se este também falhar, sobra apenas a opção "Sobrepeso".

#### **Exemplo 3: Menu de Opções (Escolha-Caso)**
```text
algoritmo "Menu"
var
   opcao: inteiro
inicio
   Escreva("1 - Olá | 2 - Tchau | 3 - Sair")
   Leia(opcao)
   escolha opcao
      caso 1
         Escreva("Olá, tudo bem?")
      caso 2
         Escreva("Até a próxima!")
      caso 3
         Escreva("Saindo...")
      outrocaso
         Escreva("Opção inválida!")
   fimescolha
fimalgoritmo
```
Em vez de testar a variável `opcao` várias vezes, a estrutura `escolha` salta diretamente para o `caso` que bate com o valor digitado. 
O `outrocaso` funciona como uma rede de segurança: se o usuário digitar 4, 5 ou qualquer valor não listado, ele avisa que a opção é inválida.

---

**Dica de Ouro**

Para as condições funcionarem, você sempre usará os **Operadores Relacionais** (`>`, `<`, `=`, `<>`, `>=`, `<=`) e poderá combiná-los com **Operadores Lógicos** (`e`, `ou`, `nao`).
