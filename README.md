# 🚀 Lattes Data Pipeline

ETL pipeline para extração, transformação e carga (ETL) de currículos da plataforma Lattes usando Apache Hop, PostgreSQL e Power BI.

## 📌 Visão Geral
Pipeline que:
1. Extrai dados de arquivos XML do Lattes
2. Transforma e estrutura as informações
3. Carrega em banco de dados PostgreSQL
4. Gera visualizações no Power BI

## 🛠️ Tecnologias
- **Apache Hop 2.12.0** (Orquestração ETL)
- **PostgreSQL** (Banco de dados)
- **Docker** (Container do PostgreSQL)
- **Power BI** (Visualização)

## 📂 Estrutura do Projeto

```bash
lattes-data-pipeline/
├── config/
│   ├── hop/                  # Configurações do Apache Hop
│   └── docker/               # Arquivos Docker (Dockerfile, init_db.sh)
├── docs/                     # Documentação complementar
├── samples/                  # Exemplos de arquivos XML do Lattes
└── scripts/                  # Scripts auxiliares
```

## ⚙️ Pré-requisitos
- Docker instalado
- Apache Hop 2.12.0+
- PostgreSQL client (HeidiSQL, DBeaver, etc.)
- Power BI Desktop (opcional)

## 🚀 Como Executar
1. **Inicie o container PostgreSQL**:

2. Importe o projeto no Apache Hop:
  Abra o Hop e carregue o projeto config/projects/lattes/

3. Execute os pipelines:

  Dados_Pesquisador.hpl (Extrai dados básicos)
  Dados_Producoes.hpl (Extrai produções acadêmicas)

## 📊 Resultados Esperados  

### 🗃️ **Tabelas no PostgreSQL**  
- **`pesquisadores`** 👩🔬  
  - Dados dos autores (ID Lattes, nome completo)  
  - Chave primária UUID gerada automaticamente  

- **`producoes`** 📑  
  - Artigos indexados (ISSN, título, ano de publicação)  
  - Relacionamento com a tabela `pesquisadores` via chave estrangeira  

### 📈 **Dashboard no Power BI**  
- **Gráfico de colunas**:  
  - `Artigos publicados por ano` (Evolução temporal da produção acadêmica)  

- **Gráfico de relacionamento**:  
  - `Pesquisadores x Produções` (Rede de colaboração científica)  

- **Filtros interativos**:  
  - Seleção por pesquisador, ano ou área de pesquisa  

### ✅ **Saída Esperada**  
```sql  
-- Exemplo de dados na tabela 'pesquisadores':  
| pesquisadores_id          | lattes_id       | nome                     |  
|---------------------------|-----------------|--------------------------|  
| 550e8400-e29b-41d4-a716... | 88185375588     | Eduardo Manuel de F. Jorge|  

-- Exemplo de dados na tabela 'producoes':  
| producoes_id              | pesquisadores_id          | issn      | nome_artigo              | ano_artigo |  
|---------------------------|---------------------------|-----------|--------------------------|------------|  
| 3f3e3e3e-4d4d-4d4d-8f8f... | 550e8400-e29b-41d4-a716... | 1234-5678 | Análise de Dados com Hop  | 2023       |
```

## ✉️ Contato  

**Elias Reis**  
[<img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white">](https://www.linkedin.com/in/elias-reis-/)  
[<img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white">](mailto:eliasreis1704@gmail.com)  

### 📍 **Redes Sociais**  
- **LinkedIn**: [Elias Reis](https://www.linkedin.com/in/elias-reis-/) 
- **GitHub**: [@EliasReis13](https://github.com/EliasReis13)  

### 📬 **Contato Profissional**  
✉️ **Email**: [Elias Reis](mailto:eliasreis1704@gmail.com)  
