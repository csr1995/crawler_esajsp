# Diagrama de Arquitetura

A arquitetura pode ser representada da seguinte forma:

- AWS Lambda: Para executar o script de scraping periodicamente.
- Amazon S3: Para armazenar os dados extraídos.
- Amazon CloudWatch: Para agendamento da execução e monitoramento do Lambda.
- Amazon DynamoDB: Para armazenar informações de metadados, como a última data de execução ou estado do processo.
- Amazon SNS: Para notificar sobre erros ou status do processo.
- AWS CloudTrail e CloudWatch Logs: Para monitoramento e análise de logs.

# Descrição dos Componentes

1. AWS Lambda:

- Função: Executa o script de scraping para extrair dados do TJSP.
- Configuração: Configurado para ser acionado por um evento do CloudWatch (por exemplo, a cada 24 horas).

2. Amazon S3:

- Função: Armazena os dados extraídos pelo script. Pode armazenar arquivos CSV, JSON ou outros formatos de dados.
- Configuração: Define buckets e permissões para armazenar e acessar os dados.

3. Amazon CloudWatch:

- Função: Gerencia o agendamento da execução do AWS Lambda e coleta métricas de execução.
- Configuração: Configura regras de eventos para acionar a função Lambda em intervalos específicos.

4. Amazon DynamoDB:

- Função: Armazena informações de metadados como a última data de execução e o status do processo.
- Configuração: Define tabelas e índices para armazenar e consultar os dados.

5. Amazon SNS:

- Função: Envia notificações (por e-mail, SMS, etc.) sobre o status do processo ou erros encontrados durante a execução.
- Configuração: Define tópicos e assinaturas para enviar alertas.

6. AWS CloudTrail e CloudWatch Logs:

- Função: Monitoram e registram as atividades da função Lambda, ajudando na análise e resolução de problemas.
- Configuração: Configura logs e auditorias para monitorar e revisar a execução e problemas do Lambda.