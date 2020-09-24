---
title: "AWS Cloud Practitioner: Conceitos de Nuvem"
author: Caio Pavanelli
date: 2020-09-24
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tags: 
- hard skills
- aws
- aws cloud practitioner
- cloud concepts
---

O exame AWS Certified Cloud Practitioner é destinado para avaliar uma compreensão geral da _cloud_ AWS. Esta postagem se concentrará na parte de conceitos de nuvem do exame e é baseada em notas de estudo feitas para o teste. Estas notas são fortemente baseadas no video do Andrew Brown do canal do FreeCodeCamp no YouTube, e também com base no curso [AWS Cloud Practitioner Essentials](https://www.aws.training/Details/Curriculum?id=27076) disponível gratuitamente. Esta é a parte 1 de 4.

{{< youtube 3hLmDS179YE >}}

## Objetivos do exame

O AWS Certified Cloud Practitioner é o nível de entrada das certificações de _cloud_ da AWS, mas que já cobre uma ampla gama de tópicos. Os objetivos do exame **CLF-C01** são:

- Definir o que é a _cloud_ AWS e sua infraestrutura global;
- Descrever os princípios básicos da arquitetura de _cloud_ AWS;
- Compreender a proposta de valor da _cloud_ AWS;
- Falar sobre os serviços comuns da AWS e seus casos de uso comuns;
- Definir aspectos básicos de segurança e _compliance_ da plataforma AWS e seu modelo de segurança compartilhado;
- Definir os modelos de faturamento, gerenciamento de contas e precificação;
- Identificar fontes de documentação e assistência técnica;
- Descrever as características básicas de implantação e operação na _cloud_ AWS.

## Computação em Nuvem

Já mencionamos a palavra **cloud** várias vezes em apenas alguns parágrafos, mas o que realmente é **computação em nuvem**?

**Computação em nuvem** significa a entrega sob demanda de recursos e aplicações via Internet. Em outras palavras, é a prática de usar uma rede de servidores remotos hospedados na Internet para armazenar, gerenciar e processar dados, ao invés de usar um servidor local ou um computador pessoal. Esses recursos fornecem:

- Servidores;
- Bancos de dados;
- Componentes de aplicativos de alto nível;
- Novos modelos de segurança:
  - Teste frequentemente;
  - Aplique mudanças e correções rapidamente;
  - Responda a incidentes o mais rápido possível.

No entanto, também traz:

- Escalabilidade;
- Agilidade;
- Elasticidade;
- Confiabilidade;
- Tolerância a erros;
- Monitoramento contínuo.

## Provedores de nuvem x local

Ao trabalhar em um ambiente local, a empresa será essencialmente a proprietária dos servidores. Ela é totalmente responsável pela contratação do pessoal de TI, pagamento ou aluguel do imóvel, bem como por todos os riscos que impliquem no funcionamento de um data center.

Por outro lado, quando uma empresa trabalha com um provedor de nuvem, a empresa é responsável apenas por configurar seus serviços de nuvem e código. O provedor de nuvem se responsabiliza pelo funcionamento do data center e pelos riscos das atividades envolvidas. Portanto, **computação em nuvem** tem algumas vantagens perceptíveis.

## Vantagens da computação em nuvem

### 1. Negociar despesas de capital para despesas variáveis

Não há custo inicial. Você está pagando apenas pelo que realmente usa. Em vez de pagar por _data centers_ e servidores, pague apenas quando consumir recursos de computação.

### 2. Beneficie de economias devido escala

Você está compartilhando o custo com outros clientes para obter economias. Compartilhamento com centenas de milhares de clientes na nuvem.

### 3. Pare de adivinhar a capacidade

Elimine suposições sobre as necessidades de capacidade da infraestrutura. Em vez de pagar por servidores ociosos ou subutilizados, você pode aumentar ou diminuir a escala e quantidade de recursos para atender às necessidades atuais.

### 4. Aumente a velocidade e agilidade

Disponibilize recursos com apenas alguns cliques, em minutos. Não há necessidade de esperar dias ou semanas para que a TI implemente a solução no servidor local.

### 5. Pare de gastar dinheiro na operação e manutenção de data centers

Concentre-se em seus próprios clientes, em vez de se concetrar no trabalho pesado de instalar e energizar servidores.

### 6. Torne-se global em minutos

Implante aplicativos em várias regiões ao redor do mundo com apenas um conjunto de configurações. Isso permite o fornecimento de uma menor latência e uma melhor experiência para seus clientes a um custo reduzido.

## Tipos de computação em nuvem

**Computação em nuvem** é oferecida de três maneiras distintas: **SaaS**, **PaaS** e **IaaS**.

1. **Software as a Service (SaaS)**
   1. Direcionado para clientes;
   2. Um produto completo executado e gerenciado pelo provedor de serviços.

2. **Platform as a Service (PaaS)**
   1. Direcionado para desenvolvedores;
   2. Elimina a necessidade da organização gerenciar infraestrutura;
   3. Os desenvolvedores podem se concentrar na implantação e gerenciamento de seus aplicativos.

3. **Infrastructure as a Service (IaaS)**
   1. Direcionado para administradores;
   2. Os blocos básicos de construção para TI em nuvem;
   3. Fornece acesso a recursos de rede, computação e espaço de armazenamento de dados.

## Modelos de implantação

Ao trabalhar com _cloud_, você pode optar por usar apenas a nuvem ou usar um modelo híbrido.

Startups, novas empresas e projetos que podem começar do zero podem se beneficiar com a adoção de apenas _cloud_. É mais fácil experimentar e se beneficiar das ofertas de SaaS.

Um modelo de implantação híbrido existe quando uma empresa combina o uso de recursos na nuvem e locais. Poderia funcionar para bancos, fintechs, empresas de gestão de investimentos, grandes provedores de serviços profissionais e sistemas legados em operação local.

Também existem aqueles que exigem somente operações locais. Ao implantar localmente usando ferramentas de virtualização e gerenciamento de recursos, chamamos às vezes de **nuvem privada**. Isso pode ser verdade para o setor público e hospitais, onde existem dados super sensíveis, ou grandes empresas com regulamentações pesadas, como companhias de seguros.

---

## Produtos baseados em nuvem da AWS

A AWS oferece uma variedade de produtos baseados em nuvem, abrangendo:

- Computação;
- Armazenamento;
- Bancos de dados;
- Analytics;
- Redes;
- Desenvolvimento móvel;
- Ferramentas de desenvolvimento;
- Ferramentas de gerenciamento;
- IoT;
- Segurança;
- Aplicações _Enterprise_.

Os recursos da AWS podem ser gerenciados por meio de três interfaces diferentes:

- AWS Management Console;
- AWS Command Line Interface (CLI);
- SDKs da AWS.

Os serviços principais da AWS são:

- EC2 (Elastic Compute Cloud);
- EBS (Elastic Block Store);
- S3 (Simple Storage Services);
- Infraestrutura global da Amazon.

### EC2

**EC2** fornece instâncias _pay-as-you-go_ de computação, que pode escalar de maneira configurável.

Cada instância EC2 requer:

- Uma região;
- Um **AMI** (Amazon Machine Image), que significa o software executado na VM;
- Tipo de instância (hardware);
- Configuração de rede;
- Configuração de armazenamento (EBS);
- Configuração do grupo de segurança;
- Pares de chaves para fornecer acesso SSH.

Os benefícios de usar instâncias do Amazon EC2 em comparação com servidores físicos locais em sua própria infraestrutura são que você paga apenas pela capacidade que usar e pela capacidade de ter diferentes requisitos de armazenamento.

### EBS

**EBS** podem ser usados ​​como unidades de armazenamento para instâncias EC2. Ele também funciona em um modelo _pay-as-you-go_ e tem as seguintes características:

- Pode ter armazenamento magnético ou SSD;
- Possui replicação de blocos;
- Tem a capacidade de tirar _snapshots_ do sistema;
- As cópias entre as instâncias EC2 são criptografadas no nível da instância EC2;
- Um EBS deve ser criado na mesma zona de disponibilidade que a instância EC2 para estar disponível para uso;
- Uma vez criado, um EBS deve ser anexado a uma instância EC2;
- Um EBS anexado pode ser formatado e virar uma partição, e configurado para um ponto de montagem;
- As tags são úteis para identificar a finalidade e os volumes do grupo em relatórios de faturamento.

### S3

**S3** é um serviço de armazenamento em nuvem totalmente gerenciado, ou seja, não está conectado a nenhum servidor. Abaixo estão algumas notas sobre o S3:

- Pode armazenar praticamente um número ilimitado de objetos, que podem ser acessados ​​a qualquer hora e em qualquer lugar;
- Possui controles de segurança que contemplam políticas de gerenciamento de acesso de identidade, políticas de acesso por bucket e até mesmo controles de acesso de nível de objeto;
- Quando um _bucket_ é criado no S3, ele é automaticamente replicado em outras instalações na mesma zona de disponibilidade;
- S3 também suporta nativamente altos volumes de acesso;
- A URL do objeto é composto do nome do _bucket_, um endpoint específico da região e a chave do objeto;
- A chave do objeto é uma _string_, onde é uma prática comum representar um caminho de diretório;
- Cada nome de _bucket_ deve ser exclusivo na zona de disponibilidade e pode conter apenas caracteres seguros para URL;
- Cada _bucket_ tem uma região.

Casos de uso comuns para S3 são:

- Armazenar ativos de aplicativos;
- Hospedagem Estática na Web;
- Backup e recuperação;
- Armazenamento para Big Data:
  - Os dados podem ser carregados no Redshift
  - Processados em EMR
  - Consultados localmente com AWS Athena

### Infraestrutura global da Amazon

A infraestrutura global da Amazon é formada por **regiões**, **zonas de disponibilidade** e **edge locations**.

**Regiões** têm duas ou mais zonas de disponibilidade.

**Zonas de disponibilidade** são conjuntos de data centers fisicamente separados uns dos outros. Cada data center é alimentado por um fornecedor de rede elétrica diferente e infraestrutura de rede independente.

**Edge locations** são estratégicamente localizadas perto de áreas de alta densidade. É o Amazon CloudFront (CDN), que é responsável por entregar conteúdo aos consumidores finais.

<!-- ---
Introduction
⌨️ (0:00:00) Meet Your Instructor Andrew Brown
⌨️ (0:00:40) Why Get AWS Cloud Practitioner Certified?
⌨️ (0:06:40) Exam Guide Overview

☁️ Cloud Concepts
⌨️ (0:09:57) What is Cloud Computing?
⌨️ (0:12:10) Six Advantages and Benefits of Cloud Computing
⌨️ (0:14:42) Types of Cloud Computing
⌨️ (0:16:48) Cloud Computing Deployment Models

☁️ Getting Started
⌨️ (0:29:20) Creating an AWS Account
⌨️ (0:32:43) Billing Preferences, Budgets and Alarms
⌨️ (0:40:09) Change IAM Users Sign-in Link
⌨️ (0:41:14) Activate MFA on Root Account
⌨️ (0:43:40) Create individual IAM user
⌨️ (0:48:44) Set a password policy -->
