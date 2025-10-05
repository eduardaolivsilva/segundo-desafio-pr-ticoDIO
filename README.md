# Workflows Automatizados com AWS Step Functions

## 📝 Descrição do Projeto
Este projeto tem como objetivo implementar e documentar um **workflow automatizado utilizando AWS Step Functions**.  
A proposta faz parte do desafio da DIO e visa consolidar os conceitos de **orquestração de serviços AWS**, automação de processos e documentação técnica.

---

## 🎯 Objetivos de Aprendizagem
- Aplicar os conceitos aprendidos sobre AWS Step Functions em um ambiente prático.
- Integrar diferentes serviços AWS em um fluxo automatizado.
- Documentar o processo de forma técnica e clara.
- Utilizar o GitHub para compartilhar e versionar documentação técnica.

---

## ⚙️ Tecnologias e Serviços Utilizados
- **AWS Step Functions**
- **AWS Lambda**
- **Amazon S3**
- **Amazon DynamoDB** (opcional)
- **AWS CloudWatch** (para monitoramento)
- **AWS Console / CLI**

---

## 🚀 Implementação do Workflow

### 1️⃣ Criação da State Machine
Acesse o console da AWS → **Step Functions → Create state machine**  
Selecione o tipo **Standard** e configure o fluxo utilizando o **Amazon States Language (ASL)** em formato JSON.

Exemplo de definição simplificada:

```json
{
  "Comment": "Exemplo de workflow Step Functions",
  "StartAt": "ProcessarArquivo",
  "States": {
    "ProcessarArquivo": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:REGIAO:ID:function:ProcessarArquivoLambda",
      "Next": "Finalizado"
    },
    "Finalizado": {
      "Type": "Succeed"
    }
  }
}
