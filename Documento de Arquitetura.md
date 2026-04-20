![Logo UFRRJ](media/ufrrj.png)
<h1 style="text-align: center; font-size: 2.5rem; color: #284b8c">Documento de Especificação Funcional</h1>
<h2 style="text-align: center; font-size: 2rem; color: #284b8c">SDNN</h2>

<div style="page-break-after: always;"></div>

# Registro de Revisões
| Versão |    Data    |    Notas de revisão     | Responsável |
| :----: | :--------: | :---------------------: | :---------: |
|  1.0   | 03/04/2026 | Elaboração do Documento |   Rafael    |

<div style="page-break-after: always;"></div>
<!--# Sumário
- [[#1. Introdução|1 Introdução]]
	- [[#1.1 Objetivo|1.1 Objetivo]]
	- [[#1.2 Definições, acrônimos e abreviações|1.2 Definições, acrônimos e abreviações]]
- [[#2. Premissas|2 Premissas]]
- [[#3. Definição de Escopo|3. Definição de Escopo]]
	- [[#3.1 Dentro do Escopo|3.1 Dentro do Escopo]]
	- [[#3.2 Fora de Escopo|3.2 Fora de Escopo]]
- [[#4. Detalhamento Técnico|4. Detalhamento Técnico]]
	- [[#4.1 Arquitetura|4.1 Arquitetura]]
	- [[#4.1 Arquitetura#4.2 Fluxo de Dados|4.2 Fluxo de Dados]]

<div style="page-break-after: always;"></div>-->

# 1. Introdução
## 1.1 Objetivo
Este documento tem como objetivo descrever a metodologia e as soluções técnicas que serão adotadas na construção do SDNN.
## 1.2 Definições, acrônimos e abreviações

| Sigla/Termo |                                                         Significado                                                          |
| :---------: | :--------------------------------------------------------------------------------------------------------------------------: |
|    SDNN     |                                               Sistema de Datasets Não Nomeado                                                |
|     CSV     |                         formato de arquivo para planilhas onde os valores são separados por vírgulas                         |
|  Markdown   |                Linguagem de marcação leve que permite adicionar elementos de formatação a documentos de texto                |
|  Adonis.js  | Framework específico para Node.js que fornece ferramentas prontas para criar aplicações web com organização e produtividade. |
|    React    |                                      Biblioteca front-end com foco em criar interfaces                                       |
|  Shadcn UI  |                                             Conjunto de componentes web modular                                              |

# 2. Premissas
Temos como premissas para o escopo inicial do SDNN:
- O upload inicial de *datasets* será limitado a arquivos no formato CSV, sendo responsabilidade do usuário garantir a integridade e padronização mínima dos dados enviados.
# 3. Definição de Escopo
## 3.1 Dentro do Escopo
Este documento entrará em detalhes sobre as seguintes questões:
- Tecnologias utilizadas no projeto;
- Integrações entre essas tecnologias;
## 3.2 Fora de Escopo
Está fora do escopo desse documento fornecer justificativas para as soluções encontradas. Também não será abordada a modelagem do banco de dados.
# 4. Detalhamento Técnico
## 4.1 Arquitetura
A solução é estruturada em uma arquitetura cliente-servidor que prioriza a integridade dos dados e a performance na entrega de grandes volumes de informação.

- **Backend**: Utilização do framework AdonisJS a partir de um starter kit para garantir as funcionalidades básicas
- **Frontend**: Desenvolvimento em React integrado ao Shadcn UI, garantindo uma interface modular, customizável e responsiva.
- **Versionamento de Dados**: Utilização de uma estrutura de pastas para o rastreio e versionamento de arquivos CSV e Markdown, mantendo-os fora do banco de dados relacional.
- **Banco de dados**: PostgreSQL executado em container Docker.

### 4.2 Estrutura de Pastas
Os datasets serão salvos na aplicação da seguinte forma:

```
Raiz/
├── Dataset X/
│   └── V1/
│       ├── README.md
│       └── planilha.csv
└── Dataset Y/
    └── V1/
        ├── README.md
        └── dados.xlsx
```

### 4.3 Fluxo de Dados
O fluxo de informações no SDNN segue regras estritas de acesso e otimização de leitura:

- **Ingestão de Dados**: Ao realizar o upload, a API processa os metadados (nome, licença, visibilidade) para o banco de dados, enquanto os arquivos físicos (CSV e Markdown) são entregues ao DVC para controle de versão.
- **Consumo de Datasets**: 
    - **Públicos**: Acessíveis via rota pública, permitindo visualização e download por usuários não autenticados.
    - **Privados/Times**: O acesso é validado por middleware que verifica a associação do usuário logado ao time proprietário do dataset.
- **Visualização (Preview)**: Para garantir a performance, o sistema gera uma versão de preview dos arquivos para ler e exibir apenas as primeiras linhas dos CSVs, evitando o carregamento total de arquivos extensos no navegador.
