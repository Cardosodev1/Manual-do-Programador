## Módulo 1.2: Operadores e Expressões
Agora que sabemos guardar dados, precisamos aprender a transformá-los e compará-los usando operadores.

---

### 1. Operadores Aritméticos e Precedência
Para processar dados numéricos, usamos operadores básicos:

| Operador | Operação | Exemplo | Resultado |
| :--- | :--- | :--- | :--- |
| `+` | Adição | `5 + 2` | `7` |
| `-` | Subtração | `5 - 2` | `3` |
| `*` | Multiplicação | `5 * 2` | `10` |
| `/` | Divisão Real (gera números quebrados) | `5 / 2` | `2.5` |
| `\` ou `DIV` | Divisão Inteira | `5 \ 2` | `2` |
| `%` ou `MOD` | Resto da Divisão (muito usado para saber se um número é par ou ímpar) | `5 % 2` | `1` |
| `^` | Potenciação | `5 ^ 2` | `25` |

#### **Ordem de Execução (Precedência)**
O computador resolve as contas nesta ordem de prioridade:

1. **Parênteses** `( )`
2. **Potenciação** `^`
3. **Multiplicação e Divisões** (`*`, `/`, `%`, `\`)
4. **Adição e Subtração** (`+`, `-`)

---

### 2. Operadores Relacionais (Comparações)
Estes operadores são usados para criar **expressões lógicas** que resultam sempre em `verdadeiro` ou `falso`.

#### **Relacionais (Comparações)**
| Operador | Significado | Exemplo |
| :--- | :--- | :--- |
| `=` | Igual a | `5 = 5` (Verdadeiro) |
| `<>` | Diferente de | `5 <> 3` (Verdadeiro) |
| `>` | Maior que | `10 > 20` (Falso) |
| `<` | Menor que | `7 < 10` (Verdadeiro) |
| `>=` | Maior ou igual a | `18 >= 18` (Verdadeiro) |

---

#### 3. Operadores Lógicos (Conectivos)
Usados para unir duas ou mais comparações em uma única expressão.

* **E (AND):** Resulta em verdadeiro apenas se **todas** as condições forem verdadeiras.
* **OU (OR):** Resulta em verdadeiro se **pelo menos uma** condição for verdadeira.
* **NÃO (NOT):** Inverte o valor (o que é verdadeiro vira falso e vice-versa).

---

### 4. Exemplo Prático
Aqui está a estrutura de um algoritmo simples que aplica todos os conceitos acima:

#### Exemplo 1: Calculadora de Média
```text
algoritmo "CalculadoraDeMedia"
var
   n1, n2, media: real
inicio
   Escreva("Digite a primeira nota: ")
   Leia(n1)
   Escreva("Digite a segunda nota: ")
   Leia(n2)
   
   media <- (n1 + n2) / 2
   
   Escreva("A média final é: ", media)
fimalgoritmo
```
O programa reserva espaço para três números decimais. Ele solicita e lê as notas, realiza o cálculo (usando parênteses para somar antes de dividir) e exibe o resultado final na tela.

#### Exemplo 2: Validação de Entrada
```text
algoritmo "ValidarEntrada"
var
   idade: inteiro
   acompanhado: logico
   podeEntrar: logico
inicio
   Escreva("Qual sua idade? ")
   Leia(idade)
   Escreva("Está acompanhado pelos pais? (verdadeiro/falso): ")
   Leia(acompanhado)
   
   podeEntrar <- (idade >= 18) ou (acompanhado = verdadeiro)
   
   Escreva("Acesso permitido: ", podeEntrar)
fimalgoritmo
```
O programa avalia duas condições. Se o usuário tiver 18 anos ou mais, a primeira parte é verdadeira. Se ele estiver acompanhado, a segunda é verdadeira. Como usamos o operador **OU**, se qualquer uma dessas for real, o `podeEntrar` será verdadeiro.
