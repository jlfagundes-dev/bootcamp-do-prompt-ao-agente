Ferramentas que vamos utilizar nestes estudos para criar agentes inteligentes:

Framework: Google ADK (Agent Development Kit) - pip install google-adk litellm
![exemplo de uso do google adk](image-2.png)

Ferramentas: MCP toolbox para conectar banco de dados e APIs https://github.com/googleapis/mcp-toolbox
   ![exemplo](image.png)
   ![exmeplo2](image-1.png)

Segurança: Usar o Azure Key Vault para armazenar chaves de API e segredos de forma segura.

LLM: Usar uma apikey do gemini para acessar os modelos de linguagem avançados.
criado no aistudio.google.com

Infra: 
- Usar venv para criar um ambiente virtual isolado para o projeto.
- Usar o Azure Database for PostgreSQL para hospedar o banco de dados de estoque.

Troubleshooting: ![exemplo](image-3.png)

Criar um system_check.py para validar as configurações e conexões antes de rodar o agente. ![exemplo](image-4.png)

Configurações Basicas do projeto: 
Agente de Consulta de Estoque

Banco de dados: PostgreSQL para armazenar dados estruturados. no Azure Database for PostgreSQL

Ferramentas: Usar o MCP server porta 7000 para conectar o agente ao banco de dados e APIs externas. Configurar o MCP para acessar o PostgreSQL e outras APIs necessárias. ![exemplo](image-5.png) 
  obs.: testar o uso do -ui para facilitar a visualização e interação com o agente.

Crie o banco de dados e as tabelas necessárias para armazenar os dados de estoque. Exemplo de tabela:
CREATE TABLE inventory (
    id SERIAL PRIMARY KEY,
    product_name VARCHAR(255) NOT NULL,
    quantity INT NOT NULL,
    last_updated TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

Logica do agente: 
- considerar usar o toolbox-core para criar a lógica do agente, definindo as ações que ele pode realizar, como consultar o banco de dados, processar os resultados e responder às consultas dos usuários.

- implementar uma função de consulta que receba uma pergunta do usuário, execute a consulta SQL correspondente no banco de dados e retorne os resultados de forma clara e concisa para o usuário.

- configurar o agente para lidar com erros e exceções, garantindo que ele possa responder de forma adequada mesmo quando ocorrerem problemas de conexão ou consultas malformadas.

- testar o agente com diferentes tipos de perguntas para garantir que ele possa lidar com uma variedade de consultas e fornecer respostas precisas e úteis.

exemplos
![codigo do agente](image-6.png)




