# Criando-um-Dashboard-Corporativo-no-Power-BI-com-integração-com-MySQL-e-Azure

📊 Integração de Dados com MySQL Azure e Power BI

📌 Descrição do Projeto

Este projeto tem como objetivo demonstrar a integração de dados entre o MySQL hospedado na Azure e o Power BI, além de aplicar técnicas de transformação e tratamento de dados para análise.

O desafio simula um cenário real de engenharia e análise de dados, envolvendo desde a criação da infraestrutura em nuvem até a modelagem dos dados para visualização.

🎯 Objetivos
Criar uma instância de banco de dados MySQL na Azure
Importar uma base de dados existente
Integrar o banco de dados ao Power BI
Identificar e corrigir problemas na base de dados
Realizar transformações para análise eficiente
🧱 Arquitetura do Projeto
Azure MySQL Database
        │
        ▼
MySQL Workbench / Cloud Shell
        │
        ▼
Power BI (Transformação e Visualização)
🚀 Etapas do Desenvolvimento
🔹 1. Criação da Instância MySQL na Azure
Provisionamento do banco de dados MySQL na plataforma Azure
Configuração inicial do servidor
🔹 2. Configuração de Acesso
Criação de regra de firewall para permitir acesso externo
Teste de conexão via Cloud Shell
🔹 3. Conexão com MySQL Workbench
Conexão ao banco utilizando cliente gráfico
Validação da estrutura da base de dados
🔹 4. Importação dos Dados
Criação do banco de dados a partir de scripts disponíveis
Inserção de dados nas tabelas
🔹 5. Integração com Power BI
Conexão do Power BI ao banco MySQL na Azure
Importação das tabelas para análise
🔧 Transformação dos Dados (Power BI)

Durante o processo de ETL (Extração, Transformação e Carga), foram realizadas as seguintes etapas:

✔️ Limpeza e Padronização
Verificação de cabeçalhos e tipos de dados
Conversão de valores monetários para tipo Double
Tratamento de valores nulos
✔️ Regras de Negócio
Identificação de colaboradores sem gerente (Super_ssn)
Verificação de departamentos sem gerente
Preenchimento de dados ausentes (quando necessário)
✔️ Transformações Estruturais
Separação de colunas complexas
Remoção de colunas desnecessárias
Ajuste de dados inconsistentes (ex: horas de projetos)
✔️ Modelagem dos Dados
Mesclagem das tabelas employee e department
Criação de tabela de colaboradores com nome do departamento
Junção entre colaboradores e seus respectivos gerentes
🧠 Query SQL utilizada (exemplo):
SELECT 
    e.Fname,
    e.Lname,
    d.Dname AS Department,
    m.Fname AS Manager_Fname,
    m.Lname AS Manager_Lname
FROM employee e
LEFT JOIN department d ON e.Dno = d.Dnumber
LEFT JOIN employee m ON e.Super_ssn = m.Ssn;
🔄 Transformações Adicionais
Criação de coluna de nome completo (Nome + Sobrenome)
Combinação de Departamento + Localização
Agrupamento para análise de quantidade de colaboradores por gerente
📊 Modelagem (Visão Futuro - Modelo Estrela)

A junção entre departamento e localização foi realizada para garantir unicidade e facilitar a futura implementação de um modelo estrela, melhorando a performance e organização das análises.

❓ Por que usar "Mesclar" ao invés de "Atribuir"?

No Power BI:

Mesclar (Merge) é utilizado quando precisamos combinar dados de diferentes tabelas com base em uma chave (JOIN)
Atribuir (Append) é utilizado para empilhar dados (UNION)

Neste projeto, utilizamos Mesclar pois queremos enriquecer os dados existentes, e não apenas adicionar novas linhas.

📈 Resultados Esperados
Base de dados tratada e consistente
Relatórios no Power BI com dados confiáveis
Melhor compreensão da estrutura organizacional (colaboradores, gerentes, departamentos)
🛠️ Tecnologias Utilizadas
☁️ Microsoft Azure (MySQL Database)
🗄️ MySQL
🧰 MySQL Workbench
📊 Power BI
🐚 Azure Cloud Shell
📁 Estrutura do Repositório
/dataset
/scripts
/powerbi
/README.md
👨‍💻 Autor

Projeto desenvolvido por Iacer Duarte

Observações

Este projeto é parte de um desafio prático com foco em:

Engenharia de Dados
ETL
Business Intelligence
