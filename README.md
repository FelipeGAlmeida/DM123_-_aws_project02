# DM123 - aws_project02

Repositório criado para versionamento do código desenvolvido durante a aula DM123, ministrada pelo professor Paulo Cesar Siecola.
O código é uma aplicação Java (API RESTful), que foi configurada para operar nas seguintes condições:
- Ser executado dentro de um container Docker;
- Ser hospedado em um cluster na AWS;
- Fazer operações com um banco de dados relacional MySQL hospedado na AWS;
- Envio de notificações SNS para um usuário especificado no serviço SNS da AWS;
- Exibição de logs;

## Funcionamento

O projeto está preparado para consumir as mensagens do serviço SNS do projeto [DM123 - aws_project01](https://github.com/FelipeGAlmeida/DM123_-_aws_project01), tanto a fila de produtos, quanto a de faturas. Essas mensagens consumidas são tratadas e enviadas ao serviço de banco de dados não relacional (NoSQL) DynamoDB, onde são armazenados cada uma em suas respectivas tabelas (ou na tabela de produtos, ou na de faturas). É possivel também consultar os eventos ocorridos com chamadas de API.

## Chamadas de API

**URL base:** *project02-lb-10213605.us-east-1.elb.amazonaws.com:9090*

### Resquests de eventos de Produtos:

**GET** *api/events*  
Response: 200 -> {{Product List}}

**GET** *api/events/{{username}}*  
Response: 200 -> {{Product}}  
&emsp;&emsp;&emsp;&emsp;&thinsp;&thinsp; 404 -> Not Found

_**Observações:** Por motivos de tempo, não foram feitas todas validações e tratamento de exceções nesta API._
