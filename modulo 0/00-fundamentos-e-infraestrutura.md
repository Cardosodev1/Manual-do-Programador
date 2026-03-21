## Módulo 0.0: O Mundo Digital (Fundamentos)
Neste módulo, mergulhamos no que acontece "debaixo do capô" antes mesmo de escrevermos nossa primeira linha de código. Entender a infraestrutura é o que diferencia um "digitador de código" de um programador que domina o ambiente onde seu software vive.

---

### 1. Como a Internet funciona?
A internet é a rede mundial de computadores interconectados.
* **Infraestrutura Física:** A conexão global ocorre principalmente por **cabos submarinos de fibra ótica** que atravessam oceanos, além de satélites e antenas.
* **TCP/IP (O Conjunto de Protocolos):** É a base da comunicação.
    * **IP (Internet Protocol):** É o endereço da sua máquina na rede. Sem ele, o servidor não sabe para onde enviar os dados.
    * **TCP (Transmission Control Protocol):** É o "gerente de logística". Ele divide a mensagem em **Pacotes**, garante que eles cheguem ao destino e os organiza na ordem correta. Se um pacote se perder, o TCP solicita o reenvio automaticamente.

<img width="1067" height="881" alt="image" src="https://github.com/user-attachments/assets/411f1b63-be92-4a04-a18f-75c7c7922746" />

---

### 2. Bits, Bytes e Dados
Como o computador entende o que você digita.
* **Binário (0 e 1):** O computador é uma máquina elétrica que entende apenas "tem sinal" (1) ou "não tem sinal" (0). Cada unidade dessa é um **Bit**.
* **O Byte:** Um grupo de 8 Bits forma um **Byte**. É a unidade mínima para representar um caractere (como a letra 'A').
* **Múltiplos (Base 2):** Na computação, usamos a potência de 2. Por isso, os valores não são "redondos" como no sistema métrico:
    * 1 KB = 1024 Bytes
    * 1 MB = 1024 KB
    * 1 GB = 1024 MB

---

### 3. Hardware: Onde o código "mora"
Para programar, você precisa entender como os recursos físicos do computador são consumidos.
* **CPU (Processador):** O "Cérebro". Ele executa as instruções matemáticas e lógicas do seu código. Quanto mais rápido, mais tarefas ele processa por segundo.
* **RAM (Memória de Curto Prazo):** A "Mesa de Trabalho". Armazena dados temporários enquanto o programa roda. É extremamente rápida, mas apaga tudo ao desligar o PC (**volátil**).
* **Armazenamento (SSD/HD):** O "Armário". Onde os arquivos ficam salvos permanentemente. O processador não consegue ler dados diretamente daqui na velocidade necessária, por isso eles são jogados para a RAM antes.

<img width="630" height="420" alt="image" src="https://github.com/user-attachments/assets/69963fc7-6cf3-497f-99a4-7c0c2ee0cf85" />

---

### 4. Software: A "Mente" da Máquina
Se o Hardware é o corpo, o Software é o pensamento. Ele é o conjunto de instruções que diz ao hardware exatamente o que fazer.
* **O que é:** Sequências lógicas de bits que o processador consegue ler e executar.
* **Software de Sistema:** Programas que controlam o hardware e fornecem uma base para outros programas (ex: Sistemas Operacionais, Drivers).
* **Software de Aplicação:** Programas que o usuário final utiliza para tarefas específicas (ex: Navegador, WhatsApp, o código que você vai escrever).
* **O Código:** O software começa como texto escrito por humanos (Código-Fonte) e é traduzido para linguagem de máquina para o hardware entender.

<img width="630" height="360" alt="image" src="https://github.com/user-attachments/assets/bbfbabb9-4ee8-4e97-a874-b656524a3c27" />

---

### 5. Sistemas Operacionais (SO)
O SO é o "gerente", o software mais importante do seu computador.
* **O Mediador:** Ele traduz as necessidades dos seus programas para o hardware. Sem o SO, você teria que programar instruções diferentes para cada modelo de placa de vídeo ou processador.
* **Gerenciamento de Processos:** Um programa em execução é um **Processo**. O SO decide quanto tempo de "atenção" da CPU cada processo recebe.
* **O Kernel:** É o núcleo do sistema. A parte que tem controle total sobre o hardware e a memória.
* **Sistemas de Arquivos:** É como o SO organiza os dados no seu SSD/HD em pastas e arquivos, controlando quem tem permissão para ler ou escrever neles.
* **Windows vs. Linux:** Enquanto o Windows é focado no usuário final, o **Linux** é o padrão da indústria para servidores e desenvolvimento, por ser mais leve, seguro e permitir controle total via terminal.

---

### 6. A Web (A World Wide Web)
A Web é um serviço que utiliza a infraestrutura da internet para funcionar. Se a internet é a estrada, a Web são os carros circulando.
* **O Modelo Cliente-Servidor:** O **Cliente** (seu navegador) solicita dados, e o **Servidor** (computador potente em um data center) envia a resposta.
* **Hospedagem:** É o "terreno" digital. Um servidor ligado 24h por dia onde os arquivos do seu site ou sistema ficam guardados.
* **Domínio:** É o nome amigável (ex: `google.com`) que usamos para não precisar decorar o IP do servidor.
* **DNS (Domain Name System):** O serviço que traduz o domínio que você digita para o IP real do servidor.
* **URL (Uniform Resource Locator):** O endereço completo de um recurso na rede. Ex: `https://www.meusite.com/img/foto.jpg`.
* **HTTP/HTTPS (O Diálogo):**
  * **HTTP (Hypertext Transfer Protocol):** É a "língua" oficial que o Cliente e o Servidor usam para conversar. É o protocolo que define como as informações são enviadas (request) e recebidas (response).
  * **HTTPS:** Adiciona uma camada de **Criptografia** (segurança). Sem o "S", qualquer um no caminho pode ler o que você envia ao servidor.

<img width="728" height="387" alt="image" src="https://github.com/user-attachments/assets/747a73e6-b590-44dd-83e6-a2afffe2f421" />

---

### 7. Frontend e Backend (Client-side vs. Server-side)
Na construção de aplicações, dividimos o trabalho em duas grandes frentes: o que o usuário vê e o que acontece nos bastidores.

#### **Frontend (Client-side)**
É a interface da aplicação, tudo o que o usuário interage diretamente.
* **Onde executa:** No dispositivo do usuário (navegador do cliente).
* **Tecnologias principais:** HTML (Estrutura), CSS (Visual) e JavaScript (Comportamento).
* **Analogia:** Em um restaurante, o Frontend é o **salão**, a decoração e o **garçom** que te atende.

#### **Backend (Server-side)**
É a inteligência por trás da aplicação. Ele cuida das regras de negócio, segurança e armazenamento de dados.
* **Onde executa:** No servidor remoto (computador do provedor).
* **O que faz:** Processa dados, consulta o banco de dados e envia as respostas para o frontend.
* **Linguagens comuns:** Java, Python, PHP, C#.
* **Analogia:** No restaurante, o Backend é a **cozinha**. Você não a vê, mas é lá que a comida (os dados) é preparada seguindo uma receita (a lógica).
