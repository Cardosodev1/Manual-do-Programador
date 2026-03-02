## Módulo 2.1: Introdução e Ambiente Java

Diferente do Portugol, o Java é uma linguagem **fortemente tipada** e **orientada a objetos**. Aqui, a estrutura do código é mais rígida para garantir segurança e performance em sistemas profissionais.

---

### 1. O Ecossistema Java
Para desenvolver em Java, precisamos entender o papel de cada componente do kit de ferramentas:

| Sigla | Nome | Função |
| :--- | :--- | :--- |
| **JVM** | Java Virtual Machine | O "motor" que interpreta e executa bytecodes Java, traduzindo-os para código de máquina |
| **JRE** | Java Runtime Environment | O pacote (JVM, bibliotecas e componentes centrais) necessário para executar programas Java. |
| **JDK** | Java Development Kit | O kit completo para **desenvolvedores**, essencial para criar, compilar e depurar aplicativos Java. |

---

### 2. O Processo de Execução
O Java não é apenas interpretado; ele passa por um processo de compilação intermediária:

1. **Código Fonte (.java):** O texto que nós escrevemos.
2. **Compilador (javac):** Transforma o texto em **Bytecode**.
3. **Bytecode (.class):** Arquivo que a JVM consegue ler.
4. **JVM:** Executa o Bytecode no seu computador.

---

### 3. Comparação de Sintaxe: Portugol vs. Java
Veja como a estrutura que aprendemos se traduz para a linguagem profissional:

| Conceito | Em Portugol | Em Java |
| :--- | :--- | :--- |
| **Saída** | `EscrevaL("Olá")` | `System.out.println("Olá");` |
| **Entrada** | `Leia(nome)` | `scanner.nextLine();` |
| **Inteiro** | `idade: inteiro` | `int idade;` |
| **Real** | `preco: real` | `double preco;` |
| **Caractere** | `nome: caractere` | `String nome;` |
| **Lógico** | `ativo: logico` | `boolean ativo;` |
| **Atribuição** | `x <- 10` | `x = 10;` |
		
---

### 4. Anatomia do Primeiro Programa
Todo código Java deve estar dentro de uma **Classe**.

```java
public class OlaMundo {
    // O método 'main' é o ponto de entrada do programa
    public static void main(String[] args) {
        System.out.println("Olá, Java!"); // Saída de dados
    }
}
```

* `public class`: Define a classe principal. O nome deve ser igual ao nome do arquivo.
* `public static void main`: É o "Início" do seu algoritmo. Sem esse método, o Java não sabe por onde começar a execução.
* `;` **(Ponto e Vírgula):** Diferente do Portugol, no Java toda instrução **deve** terminar com `;`.
  Esquecer isso é a causa de 90% dos erros de iniciantes.
