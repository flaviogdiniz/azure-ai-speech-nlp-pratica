## 🚀 Prática: Speech e Language Studio

Nesta seção, documento a jornada de exploração das plataformas, simulando um cenário real de **atendimento ao cliente** para analisar voz e texto.

###  Data : 2025-10-30
###  Recursos Utilizados: Azure Speech Resource e Azure Language Service (Região East US)

---

###  Parte 1: Azure Speech Studio – Dando Voz à IA

O foco aqui foi transformar áudio em dados (Speech-to-Text) e texto em fala (Text-to-Speech) de forma expressiva.

#### **Cenário 1.1: Transcrição de Chamada de Suporte (Speech-to-Text)**

Realizei o upload de uma gravação de cliente insatisfeito para testar a precisão da transcrição e a capacidade do modelo de lidar com informações específicas.

| Elemento | Conteúdo Simulador |
| :--- | :--- |
| **Áudio de Teste** | *"Eu estou ligando porque o meu pedido, número 459, não foi entregue ontem, conforme prometido. É inaceitável essa demora..."* |
| **Resultado Transcrito**| *"Eu estou ligando porque o meu pedido, número quatrocentos e cinquenta e nove, não foi entregue ontem, conforme prometido. É inaceitável essa demora. Eu preciso de uma solução imediata."* |


* **Inteligência Numérica:** O modelo converteu "459" para o formato extenso ("quatrocentos e cinquenta e nove") com sucesso, o que é crucial para manter a integridade da informação em sistemas de *backend*.
* **Pontuação Automática:** A aplicação automática de pontuação (vírgulas e pontos) demonstrou ser um recurso valioso, reduzindo a necessidade de pós-processamento do texto.

#### **Cenário 1.2: Síntese de Resposta Empática (Text-to-Speech)**

Gerei uma resposta com tom empático para mitigar a frustração do cliente. Utilizei a voz **Francisca Neural (pt-BR)**.

| Configuração | Observação |
| :--- | :--- |
| **Voz Selecionada** | Francisca Neural (Português, Feminino) |
| **SSML Aplicado** | Sim, para adicionar pausa e entonação de lamento. |


* **O Poder do SSML:**  Consegui programar uma pausa e reduzir a velocidade/tom na frase de lamento, para simular uma fala humana e expressar empatia.

---

###  Parte 2: Azure Language Studio – Entendendo a Intenção

Utilizei o texto transcrito da Parte 1 para aplicar os modelos de Processamento de Linguagem Natural (NLP) e extrair dados estruturados e sentimentos.

#### **Cenário 2.1: Análise de Sentimento e a Descoberta da Razão (Mineração de Opinião)**

Submeti o texto do cliente ("É inaceitável essa demora...") para análise.

* **Sentimento Geral:** **Negativo** (com alta confiança: 98%).
* **O Destaque: Mineração de Opinião:** O serviço foi além do sentimento geral, identificando que o alvo da frustração era o **"atraso"** (ou **"demora"**).


* **Mineração de Opinião é Crucial:** Saber o *porquê* da insatisfação (o atraso) permite que a IA ou o sistema de roteamento direcione a solicitação para a solução específica (logística), tornando o atendimento muito mais eficiente.

#### **Cenário 2.2: Estruturação dos Dados com NER e Frases-Chave**

Apliquei os modelos para transformar o texto livre em dados que podem ser processados por um sistema.

| Serviço | Resultado Estruturado | Valor para o Negócio |
| :--- | :--- | :--- |
| **Reconhecimento de Entidades (NER)** | **Número 459** (Quantidade/Numérico), **Ontem** (Data) | Extrai identificadores vitais para a busca no sistema. |
| **Extração de Frases-Chave** | *Pedido, número 459, solução imediata, demora* | Cria um resumo conciso e acionável da solicitação. |

* A combinação desses serviços permite à IA **"entender"** a tarefa: **"Rastrear o pedido de identificador 459 com urgência, que está em atraso."**

 ##  Conclusão

O Azure oferece ferramentas robustas e de fácil acesso via Studio, o que facilita a prototipagem de soluções como *chatbots* avançados e sistemas de análise de *call center*.
