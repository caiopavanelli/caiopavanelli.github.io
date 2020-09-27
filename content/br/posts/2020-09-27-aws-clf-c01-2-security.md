---
title: "AWS Cloud Practitioner: Segurança"
author: Caio Pavanelli
date: 2020-09-27
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tags: 
- hard skills
- aws
- aws cloud practitioner
- security
---

O exame AWS Certified Cloud Practitioner é destinado a avaliar uma compreensão geral da AWS Cloud. Esta postagem se concentrará no tópico de segurança do exame e é baseada em notas de estudo feitas para o teste. Essas notas são amplamente baseadas no video do [Andrew Brown no canal FreeCodeCamp no YouTube](https://www.youtube.com/watch?v=3hLmDS179YE) e no curso disponível gratuitamente [AWS Cloud Practitioner Essentials](https://www.aws.training/Details/Curriculum?id=27076). Esta é a parte 2 de 4.

## Segurança

A segurança na _cloud_ AWS é abordada no exame para cobrir os seguintes tópicos:

- Definir o modelo de responsabilidade compartilhada da AWS;
- Definir os conceitos de segurança e conformidade da _cloud_ AWS;
- Identificar os recursos de gerenciamento de acesso da AWS;
- Identificar recursos para suporte de segurança.

### Modelo de responsabilidade compartilhada

Para a AWS, a segurança é tanto responsabilidade dela quanto de seus clientes. A AWS se responsabiliza pela segurança **da** nuvem, e os clientes se responsabilizam ​​pela segurança **na** nuvem. O que isso significa? A AWS protege o hardware, a operação de serviços gerenciados e a infraestrutura global. Os clientes protegem seus dados e todas as configurações.

> A AWS se encarrega da segurança **da** nuvem, e os clientes se responsabilizam ​​pela segurança **na** nuvem.

É responsabilidade do cliente cuidar de:

- Dados;
- Plataformas;
- Aplicações;
- IAM (Identity and Access Management);
- Sistema operacional;
- Configuração de rede;
- Configuração de firewall;
- Criptografia de dados do lado do cliente e autenticação de integridade de dados;
- Criptografia do lado do servidor (sistema de arquivos e/ou dados);
- Proteção de tráfego de rede (criptografia, integridade, identidade);

AWS permanece responsável por:

- Software AWS para:
  - Computação;
  - Armazenamento;
  - Banco de dados;
  - Networking;
- Hardware AWS para:
  - Regiões;
  - Zonas de disponibilidade;
  - Edge locations.

### Programas de conformidade da AWS

Os programas de conformidade da AWS são um conjunto de políticas e procedimentos internos de uma empresa para cumprir as leis, regras e regulamentos ou para manter a reputação comercial.

### Artefato AWS

O AWS Artifact é gratuito. Ele é um portal de autoatendimento para acesso sob demanda aos relatórios de segurança e conformidade da AWS e contratos selecionados online. A intenção desses documentos é provar como a AWS atende a essas conformidades.

### Amazon Inspector

Amazon Inspector é um serviço que executa um benchmark de segurança em instâncias específicas EC2, no qual você pode executar uma variedade de benchmarks de segurança. Isso ajuda a provar se uma determinada instância do EC2 passou por um processo de _hardening_ ou não, por exemplo.

> Hardening é o ato de eliminar o máximo possível de riscos de segurança.

Ele também pode realizar avaliações de rede e de host. O processo instalará um agente AWS em sua instância EC2 para executar a avaliação. Com os dados do resultado, você pode revisar suas descobertas e corrigir quaisquer problemas de segurança.

Uma referência popular para o Amazon Inspector é o CIS (Center of Internet Security).

### AWS WAF

O AWS Web Application Firewall protege seus aplicativos da web de ataques comuns da web. Você pode escrever suas próprias regras para **permitir** ou **negar** o tráfego com base no conteúdo das solicitações HTTP ou usar um **conjunto de regras** de um parceiro de segurança AWS confiável no _marketplace_ WAF da AWS.

WAFs podem ser anexados ao **CloudFront** ou a um **Application Load Balancer**. A proteção pode ser abrangente contra dez dos ataques mais perigosos do OWASP (Open Web Application Security Project):

1. Injeção;
2. Autenticação quebrada;
3. Exposição de dados sensíveis;
4. Entidades externas XML (XXE);
5. Controle de acesso quebrado;
6. Configurações incorretas de segurança;
7. Cross Site Scripting (XSS);
8. Desserialização insegura;
9. Uso de componentes com vulnerabilidades bem conhecidas;
10. Registro e monitoramento insuficientes.

![WAF](/images/aws/waf.png)

### AWS Shield

O AWS Shield é um serviço gerenciado de proteção **DDoS** (Distributed Denial of Service) que protege aplicativos em execução na AWS.

Um ataque DDoS é uma tentativa maliciosa de interromper o tráfego normal, inundando um site com uma grande quantidade de tráfego falso.

Todos os clientes da AWS se beneficiam das proteções automáticas do **AWS Shield Standard**, sem custo adicional. Ao rotear seu tráfego por meio do **Route 53** ou **CloudFront**, você está usando o AWS Shield Standard.

O AWS Shield protege contra ataques das camadas 3, 4 e 7.

- camada 3 = rede;
- camada 4 = transporte;
- camada 7 = aplicação.

![AWS Shield](/images/aws/shield.png)

#### AWS Shield Standard

O AWS Shield Standard é direcionado para proteção contra ataques DDoS mais comuns e acesso a ferramentas e práticas recomendadas para construir arquiteturas resilientes a DDoS.

Está automaticamente disponível em todos os serviços da AWS.

#### AWS Shield Advanced

O AWS Shield Advanced é direcionado para proteção adicional contra ataques maiores e mais sofisticados, para ter visibilidade dos ataques e para ter acesso 24 horas por dia, 7 dias por semana a especialistas em DDoS para casos complexos.

---

O AWS Shield está disponível em:

- Amazon Route 53;
- Amazon CloudFront;
- Elastic Load Balancing;
- AWS Global Accelerator;
- Elastic IP (Amazon Elastic Compute Cloud e Network Load Balancer).

### Penetration Testing

> Pentesting é um ataque simulado autorizado a um sistema de computador, realizado para avaliar a segurança do sistema.

AWS permite pentesting em um conjunto de serviços:

- Instâncias EC2;
- Gateways NAT;
- ELB (Elastic Load Balancer);
- RDS (Relational Database Services);
- CloudFront;
- Aurora;
- Gateways API;
- Funções AWS Lambda e Lambda@Edge;
- Recursos Lightsail;
- Ambientes Elastic Beanstalk.

Por outro lado, nem todos os tipos de pentesting são permitidos e, portanto, as seguintes atividades são estritamente proibidas:

- Negação de serviço (DoS);
- Negação de serviço distribuída (DDoS);
- DoS simulado;
- DDoS simulado;
- Port flooding;
- Protocol flooding;
- Request flooding (login request flooding, API request flooding).

Para outros eventos simulados, você precisará enviar uma solicitação à AWS. A resposta geralmente leva até 7 dias.

### Guard Duty

**Guard Duty** é um serviço de detecção de ameaças que usa um **IDS/IPS** que monitora continuamente atividades maliciosas/suspeitas e comportamento não autorizado. Ele usa aprendizado de máquina para analisar os seguintes registros da AWS:

- Logs do CloudTrail;
- Registros de fluxo VPC;
- logs de DNS.

> Intrusion Detection System (IDS) e Intrusion Protection System (IPS) são um dispositivo ou software que monitora uma rede ou sistema em busca de atividades maliciosas ou violações de políticas.

O Guard Duty irá alertá-lo sobre as descobertas, que você pode automatizar uma resposta a incidentes por meio de eventos CloudWatch ou com serviços de terceiros.

### Key Management Service (KMS)

**KMS** é um serviço gerenciado que torna mais fácil para você criar e controlar as chaves de criptografia usadas para criptografar seus dados. É um HSM multi-tenant (Hardware Security Module).

Muitos serviços da AWS são integrados para usar KMS para criptografar seus dados apenas com uma simples configuração.

KSM usa criptografia de envelope. Quando você criptografa seus dados, eles são protegidos, mas você também precisa proteger sua chave de proteção. Assim, você envolve sua chave de dados criptografando-a com uma chave mestra como uma camada adicional de segurança.

### Amazon Macie

Amazon Macie é um serviço totalmente gerenciado que monitora continuamente a atividade de acesso a dados do **Amazon S3** em busca de anomalias e gera alertas detalhados quando detecta um risco de acesso não autorizado ou vazamento de dados.

Ele funciona usando aprendizado de máquina para analisar seus logs do CloudTrail. O Macie também identificará seus usuários de maior risco, e que podem levar a um comprometimento de dados.

Macie tem uma variedade de alertas:

- Acesso anônimo;
- Conformidade de configuração;
- Perda de credencial;
- Conformidade de dados;
- Hospedagem de arquivos;
- Enumeração de identidade;
- Perda de informações;
- Anomalia de localização;
- Abertura de permissões;
- Escalonamento de privilégios;
- Ramsomware;
- Interrupção do serviço;
- Acesso suspeito.

### Security Groups vs NACLs

Um **Security Group** atua como um firewall no nível da **instância**. Ele nega implicitamente todo o tráfego e você deve criar **regras de permissão**.

**Network Access Control Lists** (NACLs) atuam como firewalls no nível de **subnet**. Nesse caso, você deve criar regras de **permitir** e **negar**.

### VPN AWS

A AWS VPN permite que você estabeleça um túnel seguro e privado de sua rede ou dispositivo para a rede global AWS. Existem dois tipos de acesso VPN:

- **AWS VPN site-to-site**: conecte com segurança a rede local no site da filial ao VPC.
- **AWS VPN client**: conecte com segurança os usuários às redes locais da AWS.

## Organizations e contas da AWS

**Organizations** permitem que você gerencie centralmente o faturamento, controle o acesso, a conformidade, a segurança e compartilhe recursos em suas contas AWS. Cada organization tem um **usuário root**, que é uma identidade de login único que tem acesso completo a todos os serviços e recursos da AWS em uma conta. Cada conta possui um usuário root vinculado. Um grupo de contas da AWS em uma organização pode ser isolado em uma **organization unit**. As organization units também podem conter outras unidades criando assim uma hierarquia.

**Service Control Policies** fornecem controle central sobre as permissões de todas as contas em sua organização, ajudando a garantir que suas contas permaneçam dentro das diretrizes de sua organização.

<!-- ☁️ Security
⌨️ (3:13:49) Shared Responsibility Model
⌨️ (3:15:34) AWS Compliance programs
⌨️ (3:17:59) AWS Artifact
⌨️ (3:19:05) AWS Artifact Follow Along
⌨️ (3:21:35) Amazon Inspector
⌨️ (3:23:04) AWS WAF
⌨️ (3:24:17) AWS Shield
⌨️ (3:27:42) Penetration Testing
⌨️ (3:29:29) Guard Duty
⌨️ (3:31:13) Key Management Service
⌨️ (3:32:50) Amazon Macie
⌨️ (3:35:06) Security Groups vs NACLs
⌨️ (3:37:02) AWS VPN -->