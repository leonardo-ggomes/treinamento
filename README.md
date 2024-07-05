# Desafio de Desenvolvimento de Software Desktop para o Setor do Agronegócio

## Objetivo
Desenvolver um aplicativo desktop utilizando C# e .NET, com integração a um banco de dados SQL Server, voltado para a gestão de fazendas de produção agrícola. O sistema deverá permitir o gerenciamento de cultivos e gerar relatórios analíticos e gráficos interativos.

## Requisitos Funcionais

1. **Monitoramento de Cultivos:**
   - **Tela de Visão Geral dos Cultivos:**
     - Apresentar uma lista de cultivos com informações básicas (nome, tipo, área plantada, datas de plantio e colheita).
     - Utilizar `DataGridView` para exibir os dados de forma organizada e permitir filtragem e ordenação.
   - **Detalhamento do Cultivo:**
     - Fornecer detalhes específicos sobre cada cultivo, incluindo gráficos de crescimento e indicadores de saúde.
     - Utilizar `Windows Forms Chart` para exibir gráficos de linha ou barra que mostram o progresso do crescimento e a saúde ao longo do tempo.

2. **Alertas e Notificações:**
   - **Sistema de Notificações:**
     - Implementar notificações para atividades agrícolas importantes, como irrigação ou aplicação de fertilizantes.
     - Utilizar `NotifyIcon` para criar balões de notificação que apareçam na bandeja do sistema.
   - **Configuração de Alertas:**
     - Permitir que o usuário configure alertas para diferentes atividades e condições, como níveis baixos de estoque de insumos ou datas de aplicação de fertilizantes.
     - Implementar uma interface simples para a configuração desses alertas.

3. **Análise de Dados:**
   - **Relatórios Gerenciais:**
     - Geração de relatórios utilizando Power BI para análise avançada de dados.
     - Os relatórios devem incluir dados de produção por cultivo, uso de insumos e desempenho das atividades agrícolas.
   - **Dashboards Interativos:**
     - Criar dashboards no Power BI que permitam a visualização interativa dos dados, com gráficos, tabelas e filtros dinâmicos.

## Requisitos Não Funcionais

- **Interface de Usuário:**
  - Aplicativo desenvolvido em Windows Forms.
  - Interface intuitiva e fácil de usar, com um design claro e organizado.
  - Utilização de controles padrão do Windows Forms para entrada e visualização de dados.

- **Banco de Dados:**
  - Utilização do SQL Server para armazenamento de dados.
  - ADO.NET para integração com o banco de dados.
  - Estrutura de banco de dados otimizada para consultas rápidas e eficientes.

- **Documentação:**
  - Diagrama de classes UML para representar a arquitetura do sistema.
  - Documentação detalhada das funcionalidades e instruções de uso.
  - Comentários no código para facilitar a manutenção e entendimento.

## Tecnologias e Ferramentas

- **Linguagem de Programação:** C#
- **Framework:** .NET Framework ou .NET Core
- **Interface de Usuário:** Windows Forms
- **Banco de Dados:** SQL Server
- **ORM:** ADO.NET
- **Relatórios:** Power BI
- **Modelagem:** UML

## Desafio Prático

1. **Configuração Inicial:**
   - Configurar o ambiente de desenvolvimento com Visual Studio.
   - Criar o projeto base em Windows Forms e configurar a conexão com o SQL Server.

2. **Desenvolvimento das Funcionalidades:**
   - **Tela de Visão Geral dos Cultivos:**
     - Implementar a tela principal que exibe a lista de cultivos utilizando `DataGridView`.
     - Adicionar funcionalidades de filtragem e ordenação de dados.
   - **Detalhamento do Cultivo:**
     - Criar uma interface que mostre detalhes de cada cultivo, incluindo gráficos de crescimento.
     - Utilizar `Windows Forms Chart` para exibir os gráficos.
   - **Sistema de Notificações:**
     - Implementar `NotifyIcon` para balões de notificação.
     - Adicionar uma interface para configuração de alertas.

3. **Integração com Banco de Dados:**
   - Utilizar ADO.NET para conectar o aplicativo ao SQL Server.
   - Implementar operações de leitura e atualização de dados dos cultivos.

4. **Documentação:**
   - Elaborar diagramas UML para descrever a estrutura do sistema.
   - Documentar o código e as funcionalidades do sistema, incluindo instruções de uso.

## Estrutura de Tabelas SQL (APLICAR A NORMALIZAÇÃO)

```sql
CREATE TABLE Cultivos (
    CultivoID INT PRIMARY KEY,
    Nome NVARCHAR(100),
    Tipo NVARCHAR(50),
    AreaPlantada DECIMAL(10, 2),
    DataPlantio DATE,
    DataColheita DATE,
    EstadoCrescimento NVARCHAR(50),
    Saude NVARCHAR(50)
);

CREATE TABLE Insumos (
    InsumoID INT PRIMARY KEY,
    Tipo NVARCHAR(50),
    QuantidadeEstoque DECIMAL(10, 2),
    QuantidadeUtilizada DECIMAL(10, 2),
    DataAquisicao DATE,
    DataAplicacao DATE
);

CREATE TABLE AtividadesAgricolas (
    AtividadeID INT PRIMARY KEY,
    TipoAtividade NVARCHAR(50),
    DataHora DATETIME,
    Funcionario NVARCHAR(100),
    Duracao DECIMAL(10, 2),
    Resultados NVARCHAR(200)
);

CREATE TABLE DadosClimaticos (
    Data DATE PRIMARY KEY,
    Temperatura DECIMAL(5, 2),
    Precipitacao DECIMAL(5, 2),
    UmidadeSolo DECIMAL(5, 2)
);
