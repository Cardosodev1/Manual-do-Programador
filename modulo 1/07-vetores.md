## Módulo 1.7: Vetores (Variáveis Compostas Homogêneas Unidimensionais)

Até agora, trabalhamos com **variáveis simples**, que conseguem guardar apenas um valor por vez. Os **Vetores** permitem criar uma estrutura na memória que armazena diversos valores do mesmo tipo em uma única variável, organizada por índices.

---

### 1. O que é um Vetor?
Imagine um armário com várias gavetas numeradas. O armário inteiro tem um nome (a variável), mas cada gaveta tem um endereço específico (o índice).

* **Composta:** Possui vários espaços de memória.
* **Homogênea:** Todos os espaços guardam o mesmo tipo de dado (ex: todos são inteiros).
* **Unidimensional:** Precisa de apenas um índice para localizar um valor.

**Sintaxe de Declaração:**
```text
var
   nomeVetor: vetor[inicio..fim] de tipo_de_dado
```
Exemplo: `notas: vetor[1..4] de real` (Cria um vetor com 4 espaços para números decimais).

---

### 2. Acesso e Atribuição
Para colocar ou ler um valor em um vetor, usamos o nome da variável seguido do índice entre colchetes `[ ]`.
* **Atribuição:** `V[1] <- 10` (Coloca o valor 10 na primeira posição).
* **Uso com Variáveis:** `Escreva(V[i])` (Mostra o valor que estiver na posição indicada pela variável i).

---

### 3. Vetores e Estruturas de Repetição
A forma mais eficiente de trabalhar com vetores é utilizando o laço `para`, pois o contador do loop pode servir como o índice do vetor.

```text
para i <- 1 ate 10 passo 1 faca
   Leia(V[i])
fimpara
```

---

### 4. Exemplos Práticos

#### **Exemplo 1: Listagem de Turma (Múltiplos Vetores)**
```text
algoritmo "ListagemTurma"
var
   nomes: vetor[1..4] de caractere
   media: vetor[1..4] de real
   contador: inteiro
inicio
   para contador <- 1 ate 4 passo 1 faca
      Escreva("Nome do aluno ", contador, ": ")
      Leia(nomes[contador])
      Escreva("Média de ", nomes[contador], ": ")
      Leia(media[contador])
   fimpara
   
   LimpaTela
   EscrevaL("LISTAGEM FINAL")
   para contador <- 1 ate 4 passo 1 faca
      EscrevaL(nomes[contador]:15, media[contador]:4:1)
   fimpara
fimalgoritmo
```
O programa utiliza o loop `para` para preencher dois vetores simultaneamente. Na posição `1`, ele guarda o nome e a média do primeiro aluno, na posição `2` o do segundo, e assim por diante.
Ao final, ele percorre os vetores novamente para exibir uma lista organizada. O uso de `:15` e `:4:1` serve para alinhar o texto e formatar as casas decimais.

#### **Exemplo 2: Ordenação de Vetor (Algoritmo de Troca)**
```text
algoritmo "OrdenaVetor"
var
   vetorNumeros: vetor[1..4] de inteiro
   i, j, auxiliar: inteiro
inicio
   // Preenchimento do vetor
   para i <- 1 ate 4 passo 1 faca
      Escreva("Digite um valor: ")
      Leia(vetorNumeros[i])
   fimpara
   
   // Lógica de Ordenação
   para i <- 1 ate 3 passo 1 faca
      para j <- i + 1 ate 4 passo 1 faca
         se (vetorNumeros[i] > vetorNumeros[j]) entao
            auxiliar <- vetorNumeros[i]
            vetorNumeros[i] <- vetorNumeros[j]
            vetorNumeros[j] <- auxiliar
         fimse
      fimpara
   fimpara
   
   // Exibição do vetor ordenado
   para i <- 1 ate 4 passo 1 faca
      Escreva("{", vetorNumeros[i], "}")
   fimpara
fimalgoritmo
```
O algoritmo utiliza dois laços aninhados. O primeiro (`i`) seleciona uma posição, e o segundo (`j`) percorre todas as posições à frente dela.
Se o valor na posição `i` for maior que o valor na posição `j`, eles trocam de lugar usando uma variável `auxiliar`.
Ao final de todas as comparações, o menor valor "flutua" para o início do vetor.
