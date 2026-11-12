# 📚 Guia de Estudos: AWS CodeDeploy
#tag #aws #cloud #devtools #codedeploy #cd #bluegreen #canary #rollback

> [!info] Visão Geral
> O AWS CodeDeploy é o serviço gerenciado de implantação para EC2/on-premises, AWS Lambda e Amazon ECS: coordena a entrega de novas versões com estratégias in-place, blue/green e tráfego gradual (canary/linear), hooks de validação, monitoramento por alarmes e rollback automático. Este guia cobre fundamentos, AppSpec e ciclo de vida em EC2, implantações em Lambda e ECS, rollbacks e validação, integração e segurança (CodePipeline, roles, multi-conta) e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Implantação automatizada**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/1. Fundamentos/1.1 Visão geral/1.1.1. Implantação automatizada/1.1.1.1. O que é AWS CodeDeploy — plataformas EC2, Lambda e ECS, aplicações, deployment groups, revisões, estratégias in-place e blue-green e quando usar|1.1.1.1. O que é AWS CodeDeploy — plataformas EC2, Lambda e ECS, aplicações, deployment groups, revisões, estratégias in-place e blue-green e quando usar]]

---

## 2 Domínio: AppSpec e ciclo de vida

### 2.1 EC2 e on-premises
- **2.1.1. appspec.yml e hooks**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/2. AppSpec e ciclo de vida/2.1 EC2 e on-premises/2.1.1. appspec.yml e hooks/2.1.1.1. Implantações em EC2 e on-premises — agent, appspec.yml, hooks do ciclo de vida, in-place vs blue-green, configurações de implantação e integração com Auto Scaling e ELB|2.1.1.1. Implantações em EC2 e on-premises — agent, appspec.yml, hooks do ciclo de vida, in-place vs blue-green, configurações de implantação e integração com Auto Scaling e ELB]]

---

## 3 Domínio: Lambda e ECS

### 3.1 Tráfego gradual
- **3.1.1. Canary, linear e blue-green**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/3. Lambda e ECS/3.1 Tráfego gradual/3.1.1. Canary, linear e blue-green/3.1.1.1. Implantações em Lambda e ECS — aliases e pesos, canary e linear, blue-green com ALB, hooks de validação, SAM DeploymentPreference e alarmes|3.1.1.1. Implantações em Lambda e ECS — aliases e pesos, canary e linear, blue-green com ALB, hooks de validação, SAM DeploymentPreference e alarmes]]

---

## 4 Domínio: Rollback e validação

### 4.1 Alarmes e reversão
- **4.1.1. Rollbacks automáticos e testes de validação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/4. Rollback e validação/4.1 Alarmes e reversão/4.1.1. Rollbacks automáticos e testes de validação/4.1.1.1. Rollbacks, alarmes e validação no CodeDeploy — falha automática, alarmes do CloudWatch, hooks de validação, health checks, estratégias de release segura e testes em produção|4.1.1.1. Rollbacks, alarmes e validação no CodeDeploy — falha automática, alarmes do CloudWatch, hooks de validação, health checks, estratégias de release segura e testes em produção]]

---

## 5 Domínio: Integração e segurança

### 5.1 CodePipeline, IAM e rede
- **5.1.1. Roles, pipelines e multi-conta**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/5. Integração e segurança/5.1 CodePipeline, IAM e rede/5.1.1. Roles, pipelines e multi-conta/5.1.1.1. Integração e segurança do CodeDeploy — CodePipeline, service role e instance profile, S3 e KMS, deploy multi-conta, rede privada, SAM e CloudFormation e boas práticas|5.1.1.1. Integração e segurança do CodeDeploy — CodePipeline, service role e instance profile, S3 e KMS, deploy multi-conta, rede privada, SAM e CloudFormation e boas práticas]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Logs, falhas e custos
- **6.1.1. Diagnóstico de implantações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/6. Operação e troubleshooting/6.1 Logs, falhas e custos/6.1.1. Diagnóstico de implantações/6.1.1.1. Operação do CodeDeploy — logs do agent e dos hooks, estados e falhas comuns, métricas e eventos, quotas, custos e checklist de produção|6.1.1.1. Operação do CodeDeploy — logs do agent e dos hooks, estados e falhas comuns, métricas e eventos, quotas, custos e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.1. AWS CodeCommit/0 AWS CodeCommit (Tópicos )|AWS CodeCommit]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/0 AWS CodeBuild (Tópicos )|AWS CodeBuild]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/0 AWS CodePipeline (Tópicos )|AWS CodePipeline]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.3. Amazon ECS/0 Amazon ECS (Tópicos )|Amazon ECS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/0 Elastic Load Balancing (Tópicos )|Elastic Load Balancing]]
