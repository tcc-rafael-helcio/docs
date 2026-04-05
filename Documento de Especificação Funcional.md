![Logo UFRRJ](media/ufrrj.png)
<h1 style="text-align: center; font-size: 2.5rem; color: #284b8c">Documento de Especificação Funcional</h1>
<h2 style="text-align: center; font-size: 2rem; color: #284b8c">SDNN</h2>

<div style="page-break-after: always;"></div>

# Registro de Revisões
| Versão |    Data    |    Notas de revisão     | Responsável |
| :----: | :--------: | :---------------------: | :---------: |
|  1.0   | 01/04/2026 | Elaboração do Documento |   Rafael    |

<div style="page-break-after: always;"></div>
<!--# Sumário
- [[#1. Introdução|1 Introdução]]
	- [[#1.1 Objetivo|1.1 Objetivo]]
	- [[#1.2 Definições, acrônimos e abreviações|1.2 Definições, acrônimos e abreviações]]
- [[#2. Premissas|2 Premissas]]
- [[#3. Definição de Escopo|3. Definição de Escopo]]
	- [[#3.1 Dentro do Escopo|3.1 Dentro do Escopo]]
	- [[#3.2 Fora de Escopo|3.2 Fora de Escopo]]
- [[#4. Regras de Negócio|4. Regras de Negócio]]
	- [[#4.1 Requisitos Funcionais|4.1 Requisitos Funcionais]]
	- [[#4.2 Regras de Negócio|4.2 Regras de Negócio]]
 
<div style="page-break-after: always;"></div>-->

# 1. Introdução
## 1.1 Objetivo
Este documento tem como objetivo descrever os Requisitos Funcionais para o SDNN.
## 1.2 Definições, acrônimos e abreviações

| Sigla/Termo |                                 Significado                                  |
| :---------: | :--------------------------------------------------------------------------: |
|    SDNN     |                       Sistema de Datasets Não Nomeado                        |
|     CSV     | formato de arquivo para planilhas onde os valores são separados por vírgulas |
# 2. Premissas
Temos como premissas para o escopo inicial do SDNN:
- O upload inicial de *datasets* será limitado a arquivos no formato CSV, sendo responsabilidade do usuário garantir a integridade e padronização mínima dos dados enviados.
# 3. Definição de Escopo
## 3.1 Dentro do Escopo
Este documento visa abordar as regras de funcionamento geral do sistema, assim como suas características principais.
## 3.2 Fora de Escopo
Está fora do escopo desse documento abordar questões específicas sobre a arquitetura do projeto.
# 4. Regras de Negócio
## 4.1 Requisitos Funcionais

| Código |                                Requisito Funcional                                |
| :----: | :-------------------------------------------------------------------------------: |
|  RF01  |                  O sistema deve permitir o upload de *datasets*                   |
|  RF02  |              O sistema deve permitir a criação de grupos de usuários              |
|  RF03  |             O sistema deve permitir a criação de *datasets* privados              |
|  RF04  |               O sistema deve permitir o versionamento de *datasets*               |
|  RF05  |  O sistema deve permitir a descrição e o licenciamento de *datasets* publicados   |
|  RF06  | O sistema deve permitir que usuários não autenticados acessem *datasets* públicos |
|  RF07  |                 O sistema deve permitir o download de *datasets*                  |
## 4.2 Regras de Negócio
- O sistema deve limitar a publicação de *datasets* à usuários autorizados
- O sistema deve permitir usuários não registrados a visualização e o download de *datasets* públicos
- Todo *dataset* publicado deve possuir uma licença associada
- *Datasets* não publicados devem ser visíveis apenas pelo usuário/grupo associado