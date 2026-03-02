## Módulo 1.4: Estruturas de Repetição (Loops)

As estruturas de repetição, também conhecidas como **laços** ou **loops**, permitem que um bloco de instruções seja executado várias vezes enquanto uma condição for atendida. Elas são fundamentais para evitar a repetição manual de código e para processar grandes volumes de dados.

Existem três tipos principais de estruturas, cada uma com um comportamento diferente em relação ao teste da condição.

---

### 1. Enquanto (Teste no Início)
É a estrutura mais comum. Ela verifica a condição **antes** de entrar no bloco de código. Se a condição for falsa logo na primeira verificação, as instruções dentro dela nunca serão executadas.

* **Comportamento:** Repete as instruções **enquanto** a condição for verdadeira.
* **Sintaxe:**
    ```text
    enquanto (condicao) faca
       // bloco de instruções
    fimenquanto
    ```

<p align="center">
  <img width="557" height="481" alt="image" src="https://github.com/user-attachments/assets/a8d754bc-e64b-440c-aeba-49e02099fc3c" />
</p>

---

### 2. Repita (Teste no Final)
Diferente da anterior, esta executa o bloco de instruções primeiro e só depois faz o teste. Isso garante que o código seja executado **pelo menos uma vez**, independentemente da condição.

* **Comportamento:** Repete as instruções **até que** a condição se torne verdadeira.
* **Sintaxe:**
    ```text
    repita
       // bloco de instruções
    ate (condicao)
    ```

<p align="center">
  <img width="455" height="622" alt="image" src="https://github.com/user-attachments/assets/ac9d1851-189b-4783-b8fd-23869a9bdd1b" />
</p>

---

### 3. Para (Variável de Controle)
Esta estrutura é utilizada quando sabemos exatamente **quantas vezes** o código deve ser repetido. Ela já traz em sua sintaxe a inicialização, o limite final e o incremento (salto) da variável.

* **Comportamento:** Controla a repetição através de um contador automático.
* **Sintaxe:**
    ```text
    para (variavel) <- (inicio) ate (fim) passo (contador) faca
       // bloco de instruções
    fimpara
    ```

<p align="center">
  <img width="401" height="611" alt="image" src="https://github.com/user-attachments/assets/baefc496-cc03-48f3-925d-28b3bef7fb27" />
</p>

---

### 4. Tabela Comparativa

| Estrutura | Momento do Teste | Quando utilizar? |
| :--- | :--- | :--- |
| **Enquanto** | No Início | Quando o número de repetições é desconhecido e o bloco pode nem ser executado. |
| **Repita** | No Final | Quando o bloco precisa ser executado obrigatoriamente ao menos uma vez. |
| **Para** | Automático | Quando o número de repetições é fixo e conhecido (ex: de 1 a 100). |

---

### 5. Exemplos Práticos

#### **Exemplo 1: Contador Progressivo (Enquanto)**
```text
algoritmo "ContarAteDez"
var
   contador: inteiro
inicio
   contador <- 1
   enquanto (contador <= 10) faca
      EscrevaL(contador)
      contador <- contador + 1
   fimenquanto
fimalgoritmo
```
O programa inicia o `contador` em 1. Antes de cada volta, ele checa: "O contador ainda é menor ou igual a 10?". Se sim, ele imprime o número e soma +1 (incremento).
Esse ciclo se repete até que o contador chegue a 11, tornando a condição **falsa** e encerrando o loop.

#### Exemplo 2: Soma de Valores (Repita)
```text
algoritmo "Somador"
var
   n, soma: inteiro
   resp: caractere
inicio
   soma <- 0
   repita
      Escreva("Digite um número: ")
      Leia(n)
      soma <- soma + n
      Escreva("Quer continuar? [S/N]: ")
      Leia(resp)
   ate (resp = "N")
   Escreva("A soma total é: ", soma)
fimalgoritmo
```
O programa entra direto no laço e pede um número para somar. Só após somar, ele pergunta se o usuário deseja continuar. Se for **falso** (usuário digitou 'S'), ele **repete** o ciclo.
Assim que o teste for **verdadeiro** (usuário digitou 'N'), ele encerra. Isso garante que pelo menos um número seja lido e somado, mesmo que o usuário queira sair logo depois.

#### Exemplo 3: Tabuada (Para)
```text
algoritmo "Tabuada"
var
   n, i, resultado: inteiro
inicio
   Escreva("Ver a tabuada de qual número? ")
   Leia(n)
   para i <- 1 ate 10 passo 1 faca
      resultado <- n * i
      EscrevaL(n, " x ", i, " = ", resultado)
   fimpara
fimalgoritmo
```
O programa recebe o número desejado e usa o para para gerenciar a variável `i`, que começa em 1 e, a cada volta do laço, `o passo 1` adiciona 1 automaticamente ao valor de `i` até que ele atinja o limite 10.
Em cada volta, ele calcula a multiplicação e mostra na tela.
