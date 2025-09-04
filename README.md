# portfolio-projetos
Repositório de portfólio com exemplos de projetos em concessões públicas, regulação econômica, auditoria independente e estudos de viabilidade econômico-financeira. Os materiais aqui organizados são ilustrativos, baseados em dados públicos e metodologias aplicadas em trabalhos reais.

Portfólio Profissional – Vanessa Martins Conceição

*Sobre*

Economista (CORECON/SC nº 3958), Doutoranda em Economia e Mestre em Serviço Social.
Atuo em concessões públicas, regulação econômica, auditoria independente e estudos de viabilidade econômico-financeira, com experiência em projetos de transporte, saneamento, infraestrutura e políticas públicas.

Este repositório apresenta parte do meu portfólio técnico, organizado em:

1. Quadro de Projetos por Área (síntese sem dados sensíveis).

2. Scripts e Modelos (SQL e R, com dados públicos).

3. Bases Públicas Tratadas para análises demonstrativas.

1. Portfólio de Projetos 📊

 🚍 Transporte Público

- Verificação Independente – Especialista em Análise Econômico-Financeira (avaliação de contratos de concessão municipal e cálculo tarifário).

- Estudos de Viabilidade – Especialista em Modelagem, Remodelagem e Viabilidade (cálculo tarifário, matriz de origem-destino, planos de concessão).

🏟️ Infraestrutura e Esporte

- Verificação Independente – Especialista em Regulação Econômica e Modelagem (análise econômico-financeira de arenas multiuso).

- PPP / Concessão Metro – Especialista em Modelagem e Viabilidade Econômico-Financeira (assessoria e consultoria financeira em contrato patrocinado).

🏗️ Rodovias e Relicitação

- Relicitação de Concessão – Economista Sênior / Especialista em Regulação (avaliação de bens reversíveis e cálculo de indenizações).

💧 Saneamento

- Verificação Independente – Especialista em Regulação e Análise Econômico-Financeira (acompanhamento de concessões de água e esgoto).

📊 Auditoria

- Auditoria e Verificação Independente – Auditora Assistente / Especialista (conferência econômico-financeira de contratos de concessão).

📈 Estudos Setoriais e Planos de Negócio

- Planos de Negócio – Especialista em Viabilidade Econômico-Financeira (elaboração e análise de cenários econômicos).

  📂 Estrutura do Repositório

sql/ → Script SQL de criação de tabela e consultas (tratamento.sql)

R/ → Script em R para análise com SQLite (analise.R)

data/ → Bases de dados públicas para demonstração (K3241_amostra5.csv, Negros_MercadoTrabalho_SC.xlsx)

README.md → Documentação do portfólio

🗄️ Scripts Técnicos
🔹 SQL

Exemplo de criação de tabela (tratamento.sql):

CREATE TABLE empresas (
    id TEXT,
    nome_razao TEXT,
    cod3 INTEGER,
    cod4 INTEGER,
    valor TEXT,
    cod6 INTEGER,
    observacao TEXT
);

🔹 R

Exemplo de análise (analise.R):

# Conectar ao banco SQLite
con <- dbConnect(SQLite(), "empresas.db")

# Ler primeiras linhas
head(dbReadTable(con, "empresas"), 5)

# Médias por cod4
dbGetQuery(con, "
  SELECT cod4,
         AVG(CAST(REPLACE(REPLACE(valor, '.', ''), ',', '.') AS REAL)) AS media_valores
  FROM empresas
  GROUP BY cod4
  ORDER BY media_valores DESC
  LIMIT 10;
")

dbDisconnect(con)

📈 Dados Tratados

K3241_amostra5.csv → Amostra de 5% de microdados públicos da Receita Federal, usada para demonstração em SQL e R.

Negros_MercadoTrabalho_SC.xlsx → Base consolidada sobre a participação de negros no mercado de trabalho em Santa Catarina.

🔎 Fonte dos Dados

Todos os dados utilizados neste repositório são públicos, provenientes de microdados da Receita Federal do Brasil, IBGE e demais bases oficiais.
Foram tratados exclusivamente para fins acadêmicos, técnicos e demonstrativos, em conformidade com a LGPD.

📬 Contato

👩‍💼 Vanessa Martins Conceição
Economista | Doutoranda em Economia | Mestre em Serviço Social 
CORECON/SC nº 3958

🌐 [LinkedIn](www.linkedin.com/in/vanessa-martins-conceicao)

📧 [E-mail](mailto:vahnessaa@gmail.com)
