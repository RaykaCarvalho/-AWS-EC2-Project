Este projeto foi desenvolvido como parte do desafio da DIO (Digital Innovation One) para consolidar conhecimentos em gerenciamento de instâncias EC2 na AWS. O objetivo foi criar uma documentação clara e estruturada, demonstrando o uso de conceitos fundamentais como AMIs (Amazon Machine Images), Snapshots EBS e a integração com uma arquitetura de serviços serverless.

O projeto prático combina uma arquitetura de aplicação tradicional (EC2 + RDS) com um fluxo de processamento de dados moderno e serverless (S3, Lambda e DynamoDB), mostrando a capacidade de integrar diferentes tecnologias da AWS para criar uma solução completa.

Conhecimentos Aplicados
Gerenciamento de Instâncias EC2: Demonstração de como iniciar, parar e personalizar instâncias para atender a diferentes necessidades.

AMIs (Amazon Machine Images): Criação de uma imagem customizada de uma instância EC2, que permite a replicação rápida e consistente de ambientes. Isso é essencial para escalabilidade e para manter a conformidade em ambientes de produção.

Snapshots EBS: Utilização de snapshots para criar backups pontuais de volumes EBS. Isso é uma prática crucial para a segurança e recuperação de desastres.

Modelo de Responsabilidade Compartilhada da AWS: Entendimento de que a AWS é responsável pela infraestrutura física, enquanto o cliente é responsável pela segurança e configuração dos recursos na nuvem.

Serviços Serverless: Conhecimento prático da integração entre S3, Lambda e DynamoDB para criar um fluxo de processamento de arquivos sem a necessidade de gerenciar servidores.

Ferramentas de Custo: Familiaridade com o AWS Price Calculator para estimar e planejar os gastos em nuvem.

Arquitetura do Projeto
O projeto é baseado em uma arquitetura híbrida, combinando o melhor dos mundos tradicional e serverless.

Fluxo de Processamento Serverless:

Um Actor (usuário ou sistema) faz o upload de um Arquivo para um bucket Amazon S3.

O upload no S3 atua como um Trigger que invoca uma função AWS Lambda.

A função Lambda, escrita em Python, Node.js ou .NET Core, processa o arquivo.

Os Dados Processados são armazenados em um banco de dados Amazon DynamoDB, ideal para workloads sem servidor.

Aplicação Tradicional:

Uma instância Amazon EC2 hospeda a aplicação principal.

Essa aplicação utiliza um banco de dados Amazon RDS para dados estruturados.

Essa arquitetura demonstra um entendimento de como as cargas de trabalho podem ser distribuídas de forma eficiente, usando a flexibilidade da arquitetura serverless para tarefas assíncronas e a robustez da arquitetura tradicional para a aplicação principal.

Passos para a Reprodução
Criação da Instância Base:

Lançamento de uma instância EC2 e configuração de um Security Group para acesso SSH e HTTP# AWS-EC2-Project
### **Desafio DIO: Gerenciando Instâncias EC2 e Criando uma Arquitetura na AWS**

---

### :rocket: **Sobre o Projeto**

Este projeto é a minha solução para o desafio "Gerenciamento de Instâncias EC2" da DIO. O objetivo foi aplicar conceitos práticos de cloud computing, consolidar o aprendizado e documentar todo o processo em um repositório.

A arquitetura demonstra a integração de serviços essenciais da AWS para criar um fluxo de trabalho completo, combinando o poder do **Amazon EC2** e **RDS** com a agilidade da arquitetura **serverless** (S3, Lambda e DynamoDB).

---

### :mortar_board: **Conhecimentos Aplicados**

-   **Gerenciamento de Instâncias EC2:**
    -   Lançamento, configuração e gerenciamento de máquinas virtuais na nuvem.
-   **AMIs (Amazon Machine Images):**
    -   Criação de imagens personalizadas para replicação rápida e consistente de ambientes.
-   **Snapshots EBS:**
    -   Estratégias de backup e recuperação de volumes de armazenamento.
-   **Modelo de Responsabilidade Compartilhada:**
    -   Compreensão clara das responsabilidades entre o cliente e a AWS.
-   **Arquitetura Serverless:**
    -   Construção de um fluxo de processamento de dados usando serviços sem servidor.
-   **Otimização de Custos:**
    -   Familiaridade com a ferramenta **AWS Price Calculator** para estimativas.

---

### :gear: **A Arquitetura**

A solução é um exemplo de arquitetura híbrida, que equilibra a performance de uma aplicação tradicional com a eficiência de um sistema orientado a eventos.

![Diagrama da Arquitetura AWS]
`**)

#### **Fluxo de Processamento de Dados:**

1.  Um **`Actor`** (usuário ou sistema) faz o upload de um **`Arquivo`** para um bucket **Amazon S3**.
2.  O upload no S3 atua como um **`Trigger`** que invoca uma função **AWS Lambda**.
3.  A função Lambda processa o arquivo e extrai informações.
4.  Os **`Dados Processados`** são salvos no banco de dados **Amazon DynamoDB**.

#### **Aplicação Principal:**

-   Uma aplicação roda em uma instância **Amazon EC2**.
-   Esta aplicação se conecta a um banco de dados relacional **Amazon RDS** para gerenciar dados estruturados.

---

### :hammer_and_wrench: **Passos para a Prática**

1.  **Instância Base:** Lançamento de uma instância EC2, configurando regras de `Security Group` para acesso seguro.
2.  **Criação da AMI:** A instância foi parada para garantir a consistência dos dados, e uma AMI foi criada, gerando automaticamente um Snapshot do volume EBS.
3.  **Backup com Snapshots:** Demonstração da criação e restauração de um volume EBS a partir de um Snapshot, uma etapa vital para qualquer estratégia de backup.

---

### :bulb: **Minhas Conclusões**

Este projeto foi fundamental para solidificar a teoria na prática. A experiência de construir e documentar cada etapa, desde a criação da AMI até a integração com serviços serverless, reforçou a importância de uma arquitetura bem planejada na nuvem.

Instalação e configuração de um servidor web na instância.

Criação da AMI:

Parada da instância para garantir a consistência dos dados.

Criação de uma AMI a partir da instância, que automaticamente gerou um Snapshot do volume EBS.

Gerenciamento de Snapshots:

Demonstração de como criar um Snapshot de um volume EBS.

Explicação de como um novo volume pode ser restaurado a partir desse Snapshot para backup e recuperação.

Conclusão
Este projeto foi uma excelente oportunidade para aplicar os conhecimentos adquiridos na prática e documentar o processo. A experiência de construir e entender a interconexão dos serviços da AWS reforçou a importância de conceitos como arquitetura, automação e segurança. O uso de AMIs e Snapshots, em particular, provou ser fundamental para a criação de soluções escaláveis e resilientes na nuvem.
