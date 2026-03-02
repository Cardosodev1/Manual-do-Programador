# Módulo 1.6: Funções (Rotinas - Parte 2)

As **Funções** são o segundo tipo de rotina que podemos utilizar. Assim como os procedimentos, elas servem para isolar blocos de código, mas com uma diferença fundamental: elas **retornam um valor** ao final de sua execução.

---

### 1. A Diferença Crucial: Função vs. Procedimento

| Rotina | Comportamento | Analogia |
| :--- | :--- | :--- |
| **Procedimento** | Executa uma tarefa e pronto. | Um recado: "Vá lá e limpe a sala". |
| **Função** | Executa uma tarefa e **traz um resultado** de volta. | Um pedido: "Vá lá e me traga o total de cadeiras". |

No programa principal, a chamada de uma função é tratada como um valor. Por isso, você pode atribuir uma função a uma variável ou usá-la dentro de um `Escreva`.

---

### 2. Sintaxe da Função
Para declarar uma função, precisamos indicar o tipo de dado que ela vai devolver (inteiro, real, caractere ou logico).

```text
funcao NomeDaFuncao(parametros): tipo_do_retorno
var
   // variáveis locais
inicio
   // instruções
   retorne valor_final // Comando obrigatório
fimfuncao
```

### 3. Funções Internas (Nativas do Sistema)
A maioria das linguagens (incluindo o Java) já possui funções prontas. No VisuAlg/Portugol, existem funções úteis para manipular textos:

| Função | Descrição | Exemplo |
| :--- | :--- | :--- |
| `compr(texto)` | Retorna o tamanho do texto. | `compr("Java")` retorna 4. |
| `copia(texto, p, n)` | Extrai uma parte do texto. | `copia("Curso", 1, 3)` retorna "Cur". |
| `maiusc(texto)` | Converte para MAIÚSCULAS. | `maiusc("oi")` retorna "OI". |
| `minusc(texto)` | Converte para minúsculas. | `minusc("OI")` retorna "oi". |
| `pos(sub, texto)` | Busca a posição de uma letra/palavra. | `pos("v", "ovo")` retorna 2. |

### 4. Exemplos Práticos

#### **Exemplo 1: Soma com Retorno (Básico)**
```text
algoritmo "SomaComFuncao"
var
   valor1, valor2, resultadoSoma: inteiro

funcao SomarValores(numeroA, numeroB: inteiro): inteiro
inicio
   retorne numeroA + numeroB
fimfuncao

inicio
   Escreva("Primeiro valor: ")
   Leia(valor1)
   Escreva("Segundo valor: ")
   Leia(valor2)
   
   // A variável recebe o que a função "retornar"
   resultadoSoma <- SomarValores(valor1, valor2)
   
   EscrevaL("A soma vale: ", resultadoSoma)
fimalgoritmo
```
Diferente do procedimento, a função `SomarValores` não escreve nada na tela. Ela apenas calcula o valor e o "joga" de volta para a linha onde foi chamada.
No programa principal, a variável `resultadoSoma` captura esse valor retornado (ex: 9) e o armazena.

#### **Exemplo 2: Verificador de Paridade (Retorno de Texto)**
```text
algoritmo "ParOuImparFuncao"
var
   numeroDigitado: inteiro
   resultadoTexto: caractere

funcao VerificarParidade(valorRecebido: inteiro): caractere
inicio
   se (valorRecebido % 2 = 0) entao
      retorne "PAR"
   senao
      retorne "ÍMPAR"
   fimse
fimfuncao

inicio
   Escreva("Digite um número: ")
   Leia(numeroDigitado)
   
   resultadoTexto <- VerificarParidade(numeroDigitado)
   
   EscrevaL("O número ", numeroDigitado, " é um valor ", resultadoTexto)
fimalgoritmo
```
A função analisa o resto da divisão. Se for zero, ela retorna a palavra "PAR", caso contrário, retorna "ÍMPAR".
O programa principal recebe essa palavra e a utiliza para montar uma frase completa no `EscrevaL`.

#### **Exemplo 3: Cálculo de Fatorial (Variável Local e Retorno)**
```text
algoritmo "FatorialComFuncao"
var
   numeroEntrada, resultadoFatorial: inteiro

funcao CalcularFatorial(valorBase: inteiro): inteiro
var
   contador, acumulador: inteiro // Variáveis locais
inicio
   acumulador <- 1
   para contador <- 1 ate valorBase passo 1 faca
      acumulador <- acumulador * contador
   fimpara
   retorne acumulador
fimfuncao

inicio
   Escreva("Calcular o fatorial de: ")
   Leia(numeroEntrada)
   resultadoFatorial <- CalcularFatorial(numeroEntrada)
   EscrevaL("O fatorial de ", numeroEntrada, "! é ", resultadoFatorial)
fimalgoritmo
```
Dentro da função, usamos `contador` e `acumulador` para realizar o cálculo. Essas variáveis só existem enquanto a função trabalha.
Ao final do loop, o `acumulador` contém o resultado (ex: 120 caso o usuário digite 5), que é enviado de volta ao programa principal através do comando `retorne`.

