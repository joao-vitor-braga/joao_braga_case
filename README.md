#### Case – Engenharia de Dados

Este projeto foi desenvolvido como parte de um **processo seletivo para Engenheiro de Dados**.  
O objetivo foi construir um **pipeline de dados** usando **Apache Spark** e **PostgreSQL**, com todo o ambiente automatizado via **Docker**, sem precisar configurar nada manualmente.

---

#### Objetivo do projeto

Demonstrar na prática o fluxo completo de um pipeline de dados — desde a extração do banco PostgreSQL, passando pelas transformações no Spark, até a geração do dataset final em CSV.  
O resultado final é um arquivo consolidado com as informações da movimentação financeira (`movimento_flat.csv`).

---

#### Tecnologias utilizadas

- **Apache Spark** → Processamento e transformações de dados 
- **PostgreSQL** → Armazenamento relacional das tabelas de origem  
- **Docker e Docker Compose** → Automação e isolamento do ambiente  
- **Python (PySpark)** → Linguagem principal para o ETL
- **SQL** → Linguagem para a criação e upload dos dados no PostgreSQL e também obtenção do dataframe movimento_flat;

---

#### Para executar:

1. **Instalar e Abrir o Programa Docker Desktop**

2. **Reproduzir o repositório:**
   ```bash
   git clone https://github.com/joao-vitor-braga/financial-data-pipeline-spark-postgres-docker.git
   cd financial-data-pipeline-spark-postgres-docker
   ```

3. **Subir os containers:**
   ```bash
   docker compose up --build
   ```

Após alguns instantes, o processo completo será executado automaticamente.  
O arquivo final estará disponível em `data/output/movimento_flat/`.

---

#### Decisões e organização
  
- Usei Docker para garantir portabilidade, conforme sugerido, onde qualquer pessoa pode rodar o projeto sem se preocupar com instalações locais.  
- Mantive os scripts e outputs o mais claro que consegui, para facilitar o entendimento e possíveis expansões.

---

#### Dificuldades e aprendizados

1. Entender como os **serviços se comunicam via Docker Compose** exigiu diversos testes de tentativa e erro;  
2. Ganhei uma visão prática de como funciona o ciclo completo de um pipeline de dados;

Essas dificuldades me ajudaram a consolidar o aprendizado e me aproximaram do dia a dia de um engenheiro de dados.

---

#### Próximos passos e melhorias

- Implementar **anonimização de dados pessoais** (ex: nome), seguindo boas práticas e LGPD;  
- Criar **testes automatizados** para validar as transformações nos DataFrames;  
- Criar **pipelines orquestrados** (ex: Airflow) em versões futuras.

---

#### Observações finais

- O campo `data_criacao_cartao` não existia no diagrama original, então mantive o modelo fiel ao fornecido.  
- O ambiente é totalmente containerizado — **não é necessário instalar Spark nem PostgreSQL** localmente.
