## Módulo 0: O Mundo Digital (Fundamentos)
Onde tudo começa. Antes do código, entendemos a infraestrutura.

### 1. Como a Internet funciona?
A internet é a rede mundial de computadores interconectados.
* **Infraestrutura Física:** A conexão global ocorre principalmente por **cabos submarinos de fibra ótica** que atravessam oceanos, além de satélites e antenas.
* **TCP/IP:** Um **conjunto de protocolos** que formam a base de como a internet funciona. Ele divide a mensagem em pequenas unidades chamadas pacotes. O **IP** identifica o endereço da máquina, e o **TCP** garante que os dados cheguem sem erros, reordenando os pacotes no destino (que chegam bagunçados) e reenviando automaticamente caso algum pacote se perca no caminho.

<img width="1067" height="881" alt="image" src="https://github.com/user-attachments/assets/411f1b63-be92-4a04-a18f-75c7c7922746" />


### 2. A Web (A World Wide Web)
Muitos confundem Internet com Web, mas a Web é apenas um serviço que utiliza a internet como estrada.
* **Hospedagem:** É o "terreno" digital. Um servidor ligado 24h por dia onde os arquivos do seu site ou sistema ficam armazenados.
* **O Modelo Cliente-Servidor:** O **Cliente** (seu navegador) solicita dados, e o **Servidor** (computador potente em um data center) envia a resposta.
* **Domínio:** É o nome amigável (ex: `google.com`) que usamos para não precisar decorar o IP do servidor.
* **DNS (Domain Name System):** O serviço que traduz o domínio que você digita para o IP real do servidor.
* **URL (Uniform Resource Locator):** O endereço completo de um recurso na rede. Ex: `https://www.meusite.com/blog/post-1`.
* **HTTP:** O protocolo de transferência de hipertexto. É como as informações são enviadas e recebidas.
* **HTTPS:** A versão segura (o 'S' vem de SSL/TLS). Ele criptografa os dados entre o cliente e o servidor, garantindo que ninguém "grampeie" a conversa.

<img width="728" height="387" alt="image" src="https://github.com/user-attachments/assets/747a73e6-b590-44dd-83e6-a2afffe2f421" />

## 3. Bits, Bytes e Dados
Como o computador entende o que você digita.
* **Binário (0 e 1):** O computador é uma máquina elétrica que entende apenas "tem sinal" (1) ou "não tem sinal" (0). Cada unidade dessa é um **Bit**.
* **O Byte:** Um grupo de 8 Bits forma um **Byte**. É a unidade mínima para representar um caractere (como a letra 'A').
* **Múltiplos:** 1024 Bytes = 1 KB; 1024 KB = 1 MB; 1024 MB = 1 GB... (A base é 1024 por ser potência de 2).
