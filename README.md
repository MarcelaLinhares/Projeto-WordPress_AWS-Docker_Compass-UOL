# Projeto WordPress na AWS com Docker – PB Compass UOL – ABR 2025 | AWS & DevSecOps

## 📝 Descrição do Projeto

O projeto foi desenvolvido como parte da trilha Docker/AWS no Programa de Bolsas da Compass UOL – Abril 2025 | AWS & DevSecOps.

Este repositório documenta a criação de uma infraestrutura completa e escalável na AWS para hospedar uma aplicação WordPress, utilizando containers Docker em instâncias EC2 privadas, banco de dados gerenciado via RDS MySQL, armazenamento compartilhado com EFS, distribuição de tráfego com Load Balancer, escalabilidade automática com Auto Scaling Group, monitoramento com CloudWatch e automação de provisionamento via script *User Data*.

## ⚙️ Arquitetura do Projeto

A imagem abaixo representa a arquitetura principal do projeto WordPress na AWS, com ênfase em alta disponibilidade e escalabilidade:

![Diagrama da Arquitetura](img/01-arquitetura-projeto.png)

A arquitetura contempla:
- Instâncias EC2 privadas com WordPress
- Load Balancer
- RDS (MySQL)
- EFS
- Auto Scaling Group
- Distribuição entre duas zonas de disponibilidade (AZs)

### ➕ Serviços complementares presentes no projeto

Além dos recursos representados na imagem, o projeto também implementa:

- Monitoramento com **Amazon CloudWatch**
- Regras personalizadas de **Auto Scaling**

> Esses serviços não estão ilustrados no diagrama, mas fazem parte da infraestrutura documentada e aplicada na prática.

## 🛠️ Tecnologias Utilizadas

<a href="https://aws.amazon.com/pt/" target="_blank">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" />
</a>
<a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html" target="_blank">
  <img src="https://img.shields.io/badge/Amazon EC2-FF9900?style=for-the-badge&logo=amazon-ec2&logoColor=white" />
</a>
<a href="https://www.mysql.com/" target="_blank">
  <img src="https://img.shields.io/badge/RDS MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
</a>
<a href="https://docs.aws.amazon.com/efs/" target="_blank">
  <img src="https://img.shields.io/badge/Amazon EFS-FF9900?style=for-the-badge&logo=amazons3&logoColor=white" />
</a>
<a href="https://docs.aws.amazon.com/elasticloadbalancing/" target="_blank">
  <img src="https://img.shields.io/badge/Application Load Balancer-0052CC?style=for-the-badge&logo=load-balancer&logoColor=white" />
</a>
<a href="https://docs.docker.com/" target="_blank">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</a>
<a href="https://docs.docker.com/compose/" target="_blank">
  <img src="https://img.shields.io/badge/Docker Compose-4285F4?style=for-the-badge&logo=docker&logoColor=white" />
</a>
<a href="https://docs.aws.amazon.com/autoscaling/" target="_blank">
  <img src="https://img.shields.io/badge/Auto Scaling-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" />
</a>
<a href="https://docs.aws.amazon.com/cloudwatch/" target="_blank">
  <img src="https://img.shields.io/badge/CloudWatch-FF4F8B?style=for-the-badge&logo=amazonaws&logoColor=white" />
</a>
<a href="https://wordpress.org/" target="_blank">
  <img src="https://img.shields.io/badge/WordPress-21759B?style=for-the-badge&logo=wordpress&logoColor=white" />
</a>
<a href="https://www.markdownguide.org/" target="_blank">
  <img src="https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white" />
</a>
<a href="https://www.gnu.org/software/bash/" target="_blank">
  <img src="https://img.shields.io/badge/Shell-Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" />
</a>
<a href="https://yaml.org/" target="_blank">
  <img src="https://img.shields.io/badge/YAML-000000?style=for-the-badge&logo=yaml&logoColor=white" />
</a>
<a href="https://aws.amazon.com/amazon-linux/">
  <img src="https://img.shields.io/badge/Amazon%20Linux%202023-232F3E?style=for-the-badge&logo=linux&logoColor=white" />
</a>
<a href="https://git-scm.com/" target="_blank">
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
</a>
<a href="https://github.com/" target="_blank">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
</a>
<a href="https://code.visualstudio.com/" target="_blank">
  <img src="https://img.shields.io/badge/VS Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" />
</a>

## 🔽 Etapas do Projeto

Cada etapa possui um README próprio com o passo a passo detalhado da implementação.

### ➤ Etapa 01 – Criar Rede (VPC, Subnets, NAT, IGW)  
Criação da rede na AWS conforme boas práticas de arquitetura.  
Configuração da VPC, subnets públicas e privadas, gateway de internet, NAT gateway e tabelas de rota.

**[PASSO A PASSO COMPLETO DA ETAPA 01](etapa-01-criar-rede.md)**

### ➤ Etapa 02 – Grupos de Segurança  
Criação dos grupos de segurança para EC2, RDS, EFS e Load Balancer com regras de entrada e saída conforme necessidade da aplicação.

**[PASSO A PASSO COMPLETO DA ETAPA 02](etapa-02-grupos-seguranca.md)**

### ➤ Etapa 03 – Criar Banco de Dados (RDS MySQL)  
Criação da instância RDS MySQL.

**[PASSO A PASSO COMPLETO DA ETAPA 03](etapa-03-rds-mysql.md)**

### ➤ Etapa 04 – Criar EFS  
Criação de sistema de arquivos elástico (EFS) com pontos de montagem e regras de segurança.

**[PASSO A PASSO COMPLETO DA ETAPA 04](etapa-04-efs.md)**

### ➤ Etapa 05 – Launch Template e EC2 com Docker  
Configuração do Launch Template com EC2 em subnet privada, instalação via User Data (Docker, Docker Compose, montagem do EFS), e implantação do WordPress via Docker Compose.

**[PASSO A PASSO COMPLETO DA ETAPA 05](etapa-05-launch-template-ec2.md)**

### ➤ Etapa 06 – Load Balancer  
Criação de um Application Load Balancer com Target Group associado às instâncias EC2. Health checks configurados no caminho raiz (`/`).

**[PASSO A PASSO COMPLETO DA ETAPA 06](etapa-06-load-balancer.md)**

### ➤ Etapa 07 – Auto Scaling Group  
Criação do Auto Scaling Group com Launch Template, associação ao Target Group e definição das regras de escalabilidade. 

**[PASSO A PASSO COMPLETO DA ETAPA 07](etapa-07-auto-scaling.md)**

### ➤ Etapa 08 – Monitoramento com CloudWatch  
Criação de alarme de CPU e dashboard para acompanhamento da EC2 e do Auto Scaling.

**[PASSO A PASSO COMPLETO DA ETAPA 08](etapa-08-cloudwatch.md)**

### ➤ Etapa 09 – Testes da Infraestrutura  
Verificação completa do funcionamento do WordPress (via navegador), conexão com o RDS, persistência via EFS e balanceamento de carga.

**[PASSO A PASSO COMPLETO DA ETAPA 09](etapa-09-testes.md)**

## 👩‍💻 Desenvolvido por:

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/MarcelaLinhares">
        <img src="https://avatars.githubusercontent.com/u/141354578?v=4" width="80px;" alt="Foto de perfil GitHub da Marcela Linhares"/><br />
        <sub><b>Marcela Linhares</b></sub>
      </a>
    </td>
  </tr>
</table>