![Logo UFRRJ](media/ufrrj.png)
<h1 style="text-align: center; font-size: 2.5rem; color: #284b8c">Documento de Especificação Funcional</h1>
<h2 style="text-align: center; font-size: 2rem; color: #284b8c">SDNN</h2>

<div style="page-break-after: always;"></div>

# Registro de Revisões
| Versão |    Data    |    Notas de revisão     | Responsável |
| :----: | :--------: | :---------------------: | :---------: |
|  1.0   | 03/04/2026 | Elaboração do Documento |   Rafael    |

<div style="page-break-after: always;"></div>
# Sumário
```table-of-contents
```

<div style="page-break-after: always;"></div>

# 1. Introdução
## 1.1 Objetivo
Este documento tem como objetivo descrever a metodologia e as soluções técnicas que serão adotadas na construção do SDNN.
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
Este documento entrará em detalhes sobre as seguintes questões:
- Tecnologias utilizadas no projeto;
- Integrações entre essas tecnologias;
- Práticas de desenvolvimento adotadas;
## 3.2 Fora de Escopo
Está fora do escopo desse documento fornecer justificativas para as soluções encontradas. Também não será abordada a modelagem do banco de dados.
# 4. 