## Módulo 5: Procedimentos (Rotinas - Parte 1)

As **Rotinas** são blocos de código que realizam tarefas específicas e podem ser chamados a qualquer momento pelo programa principal. O primeiro tipo de rotina que aprenderemos é o **Procedimento**.

---

### 1. O que é um Procedimento?
Um procedimento é um conjunto de instruções agrupadas sob um nome. Imagine que você tem uma tarefa que se repete várias vezes (como desenhar um cabeçalho ou limpar a tela). Em vez de escrever todos os comandos toda vez, você cria um procedimento e apenas o "chama" pelo nome.

* **Vantagem:** Evita a repetição de código e torna o programa principal muito mais limpo.
* **Sintaxe:**
    ```text
    procedimento NomeDoProcedimento(parametros)
    var
       // variáveis locais (opcional)
    inicio
       // instruções
    fimprocedimento
    ```

---

### 2. Escopo de Variáveis (Global vs. Local)
O local onde você declara uma variável define onde ela pode ser "enxergada" pelo computador.

| Tipo | Onde é declarada | Onde funciona |
| :--- | :--- | :--- |
| **Global** | No início do algoritmo principal. | Em todo o programa, inclusive dentro dos procedimentos. |
| **Local** | Dentro de um procedimento específico. | Apenas dentro daquele procedimento. Ela "morre" quando o procedimento termina. |

---

### 3. Passagem de Parâmetros
Parâmetros são valores que enviamos para dentro do procedimento para que ele possa trabalhar com eles. Existem duas formas de passar esses dados:

#### **A. Passagem por Valor**
O programa envia uma **cópia** do valor da variável original. 
* **Efeito:** Qualquer alteração feita no parâmetro dentro do procedimento **não afeta** a variável original que está fora dele.

#### **B. Passagem por Referência**
O programa envia o **endereço** (referência) da variável original. No Portugol, usamos a palavra `var` na declaração do parâmetro.
* **Efeito:** Qualquer alteração feita no parâmetro dentro do procedimento **afeta diretamente** a variável original. É como se eles estivessem "conectados".

---

### 4. Exemplos Práticos

#### **Exemplo 1: Detector de Pesado (Procedimento Simples)**
```text
algoritmo "DetectorDePeso"
var
   nomePessoa, pessoaMaisPesada: caractere
   pesoAtual, maiorPeso: real
   contador: inteiro
   
procedimento ExibirTopo()
inicio
   LimpaTela
   EscrevaL("----------------------------------")
   EscrevaL(" D E T E C T O R  DE  P E S A D O ")
   EscrevaL(" Maior Peso até agora: ", maiorPeso, "Kg")
   EscrevaL("----------------------------------")
fimprocedimento

inicio
   maiorPeso <- 0
   para contador <- 1 ate 5 passo 1 faca
      ExibirTopo() // Chamada do procedimento
      Escreva("Digite o nome: ")
      Leia(nomePessoa)
      Escreva("Digite o peso de ", nomePessoa, ": ")
      Leia(pesoAtual)
      se (pesoAtual > maiorPeso) entao
         maiorPeso <- pesoAtual
         pessoaMaisPesada <- nomePessoa
      fimse
   fimpara
   ExibirTopo()
   EscrevaL("A pessoa mais pesada foi ", pessoaMaisPesada, " com ", maiorPeso, "Kg")
fimalgoritmo
```
O procedimento `ExibirTopo` limpa a tela e desenha o cabeçalho usando a variável global `maiorPeso`.
Toda vez que o loop para roda, ele chama essa rotina para atualizar o visual do programa sem que precisemos reescrever as linhas decorativas.

#### **Exemplo 2: Verificador de Paridade (Passagem por Valor)**
```text
algoritmo "VerificadorParidade"
var
   numeroEntrada: inteiro

procedimento VerificarParidade(numeroVerificado: inteiro)
inicio
   // Verifica se o valor recebido é par ou ímpar
   se (numeroVerificado % 2 = 0) entao
      EscrevaL("O valor ", numeroVerificado, " é PAR.")
   senao
      EscrevaL("O valor ", numeroVerificado, " é ÍMPAR.")
   fimse

   // Tentativa de alterar o valor localmente
   numeroVerificado <- 0
   EscrevaL("Valor dentro do procedimento após alteração: ", numeroVerificado)
fimprocedimento

inicio
   Escreva("Digite um número para análise: ")
   Leia(numeroEntrada)

   // Realiza a chamada passando o valor por cópia
   VerificarParidade(numeroEntrada)

   // Comprova que o valor original não mudou
   EscrevaL("O valor original na variável principal continua sendo: ", numeroEntrada)
fimalgoritmo
```
O programa solicita um número e o envia para o procedimento, mas como não utilizamos a palavra `var` na declaração do parâmetro, o computador cria apenas uma cópia do valor original na memória.
O procedimento realiza o teste lógico normalmente e até tenta zerar a variável internamente, porém, como ele está manipulando apenas uma cópia, a variável `numeroEntrada` no programa principal
permanece intacta e segura.

#### **Exemplo 3: Soma com Alteração (Passagem por Referência)**
```text
algoritmo "ExemploReferencia"
var
   valorX, valorY: inteiro

procedimento CalcularSoma(var numA, numB: inteiro)
inicio
   numA <- numA + 1
   numB <- numB + 2
   EscrevaL("Soma interna vale: ", numA + numB)
fimprocedimento

inicio
   valorX <- 4
   valorY <- 8
   CalcularSoma(valorX, valorY)
   EscrevaL("Valor de X: ", valorX) // Mostrará 5
   EscrevaL("Valor de Y: ", valorY) // Mostrará 10
fimalgoritmo
```
Como os parâmetros `numA` e `numB` foram passados com `var`, eles são referências diretas a `valorX` e `valorY`.
Ao somar valores dentro do procedimento, o programa altera as variáveis originais que estão no escopo global.

#### **Exemplo 4: Gerador de Fibonacci (Uso de Variável Local)**
```text
algoritmo "FibonacciComProcedimento"
var
   termo1, termo2, contador: inteiro // Variáveis GLOBAIS

procedimento ProximoFibonacci(var valorA, valorB: inteiro)
var
   proximoTermo: inteiro // VARIÁVEL LOCAL: só existe dentro deste procedimento
inicio
   proximoTermo <- valorA + valorB
   Escreva(proximoTermo, " ")
   
   // Atualiza as referências para os próximos cálculos
   valorA <- valorB
   valorB <- proximoTermo
fimprocedimento

inicio
   termo1 <- 0
   termo2 <- 1
   Escreva(termo1, " ", termo2, " ")

   // O loop gera os próximos 8 termos (do 3º ao 10º)
   para contador <- 3 ate 10 passo 1 faca
      ProximoFibonacci(termo1, termo2)
   fimpara
fimalgoritmo
```
O programa utiliza variáveis globais para controlar a sequência, mas dentro da rotina existe uma variável chamada `proximoTermo` que possui escopo local.
Isso significa que ela nasce quando o procedimento é chamado para realizar o cálculo da soma e "morre" assim que a tarefa termina, liberando espaço na memória RAM
e impedindo que o programa principal acesse esse dado temporário indevidamente. Ao mesmo tempo, a passagem por referência garante que os novos valores dos termos sejam
devolvidos para as variáveis globais para o próximo ciclo.
