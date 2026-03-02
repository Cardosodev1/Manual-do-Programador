## Módulo 1.8: Matrizes (Variáveis Compostas Homogêneas Multidimensionais)

As **Matrizes** são variáveis compostas que possuem duas ou mais dimensões. Se um vetor é como uma linha de gavetas, uma matriz é como um armário inteiro com várias linhas e colunas de gavetas.

---

### 1. O que é uma Matriz?
É uma estrutura de dados que armazena diversos valores do mesmo tipo, acessados por dois índices: um para a **linha** e outro para a **coluna**.

* **Dimensão:** Uma matriz 3x2 possui 3 linhas e 2 colunas, totalizando 6 espaços de memória.
* **Uso Comum:** Jogos (posicionamento em mapas), planilhas, computação gráfica e cálculos matemáticos complexos.

**Sintaxe de Declaração:**
```text
var
   nomeMatriz: vetor[lin_inicio..lin_fim, col_inicio..col_fim] de tipo_de_dado
```
Exemplo: `M: vetor[1..3, 1..2] de inteiro` (Cria uma matriz de 3 linhas e 2 colunas).

---

### 2. Acesso e Atribuição
Para manipular um valor, você deve indicar sempre os dois índices entre colchetes, separados por vírgula.

* **Atribuição:** `M[1, 2] <- 4 (Coloca o valor 4 na linha 1, coluna 2).
* **Leitura:** `Leia(M[l, c])` (Lê um valor e o guarda na posição indicada pelas variáveis `l` e `c`).

---

### 3. Estrutura de Preenchimento e Exibição
Para percorrer uma matriz, utilizamos **dois laços** `para` **aninhados**: o primeiro controla as linhas e o segundo controla as colunas.

```text
para l <- 1 ate 3 passo 1 faca
   para c <- 1 ate 2 passo 1 faca
      Escreva("Digite o valor para [", l, ",", c, "]: ")
      Leia(M[l, c])
   fimpara
fimpara
```

---

### 4. Propriedades Especiais (Diagonal Principal)
Em matrizes quadradas (onde o número de linhas é igual ao de colunas):

* **Diagonal Principal:** Elementos onde `Linha = Coluna`.
* **Triângulo Superior:** Elementos onde `Coluna > Linha`.
* **Triângulo Inferior:** Elementos onde `Linha > Coluna`.

---

### 5. Exemplos Práticos

#### **Exemplo 1: Identificação de Números Pares**
```text
algoritmo "ParesNaMatriz"
var
   valores: vetor[1..3, 1..3] de inteiro
   l, c, totalPares: inteiro
inicio
   totalPares <- 0
   // Entrada de dados
   para l <- 1 ate 3 passo 1 faca
      para c <- 1 ate 3 passo 1 faca
         Escreva("Valor [", l, ",", c, "]: ")
         Leia(valores[l, c])
      fimpara
   fimpara
   
   // Exibição com destaque
   EscrevaL("MATRIZ FINAL:")
   para l <- 1 ate 3 passo 1 faca
      para c <- 1 ate 3 passo 1 faca
         se (valores[l, c] % 2 = 0) entao
            Escreva("{", valores[l, c]:2, "}") // Destaque para pares
            totalPares <- totalPares + 1
         senao
            Escreva(valores[l, c]:4)
         fimse
      fimpara
      EscrevaL("") // Pula linha ao final de cada linha da matriz
   fimpara
   EscrevaL("Ao todo foram digitados ", totalPares, " números pares.")
fimalgoritmo
```
O programa percorre cada "casa" da matriz. Se o número guardado for par (resto da divisão por 2 igual a zero), ele é exibido entre chaves e somado ao contador.
Ao final de cada laço de coluna, um `EscrevaL("")` é usado para garantir que a matriz seja desenhada no console com formato de grade.

#### **Exemplo 2: Matriz Identidade de 3ª Ordem**
```text
algoritmo "MatrizIdentidade"
var
   ident: vetor[1..3, 1..3] de inteiro
   i, j: inteiro
inicio
   para i <- 1 ate 3 passo 1 faca
      para j <- 1 ate 3 passo 1 faca
         se (i = j) entao
            ident[i, j] <- 1
         senao
            ident[i, j] <- 0
         fimse
      fimpara
   fimpara
   
   // Exibição
   para i <- 1 ate 3 passo 1 faca
      para j <- 1 ate 3 passo 1 faca
         Escreva(ident[i, j]:3)
      fimpara
      EscrevaL("")
   fimpara
fimalgoritmo
```
O algoritmo não pede dados ao usuário. Ele usa a lógica matemática: sempre que o índice da linha (`i`) for igual ao da coluna (`j`), a posição recebe o valor 1.
Caso contrário, recebe 0. Isso resulta em uma diagonal de "1" atravessando a matriz de zeros.
