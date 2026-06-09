<a href="https://classroom.github.com/online_ide?assignment_repo_id=99999999&assignment_repo_type=AssignmentRepo"><img src="https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg" width="200"/></a> <a href="https://classroom.github.com/open-in-codespaces?assignment_repo_id=99999999"><img src="https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg" width="250"/></a>

---

# AutoFix — Sistema de Gestao de Oficina Mecanica

> **Sistema web completo para gestao de oficinas mecanicas**, abrangendo controle de clientes, veiculos, ordens de servico, estoque de pecas e pagamentos.

<table>
  <tr>
    <td width="800px">
      <div align="justify">
        O <b>AutoFix</b> e um sistema de gestao desenvolvido para oficinas mecanicas de pequeno e medio porte. Ele permite o <i>cadastro de clientes e veiculos</i>, a <i>abertura e acompanhamento de ordens de servico</i>, o <i>controle de estoque de pecas</i>, o <i>registro de diagnosticos por mecanicos</i> e o <i>processamento de pagamentos</i>. O objetivo e <b>centralizar e digitalizar todo o fluxo operacional</b> de uma oficina, substituindo controles manuais em papel por uma aplicacao web moderna, acessivel e eficiente. Este projeto foi elaborado como parte da disciplina <b>Projeto de Software</b> da <a href="https://www.pucminas.br/unidade/coracao-eucaristico/ensino/graduacao/Paginas/Engenharia-de-Software.aspx">Engenharia de Software — PUC Minas</a>.
      </div>
    </td>
    <td>
      <div>
        <img src="https://joaopauloaramuni.github.io/image/logo_ES_vertical.png" alt="Logo AutoFix" width="120px"/>
      </div>
    </td>
  </tr>
</table>

---

## Status do Projeto

[![Versao](https://img.shields.io/badge/Versao-v1.0.0-blue?style=for-the-badge)](https://github.com/mateus-ferrao/autofix/releases) ![Node.js](https://img.shields.io/badge/Node.js-20-007ec6?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-4.21-007ec6?style=for-the-badge&logo=express&logoColor=white) ![React](https://img.shields.io/badge/React-18.3-007ec6?style=for-the-badge&logo=react&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-5.4-007ec6?style=for-the-badge&logo=vite&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-007ec6?style=for-the-badge&logo=postgresql&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-5.6-007ec6?style=for-the-badge&logo=typescript&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-27-007ec6?style=for-the-badge&logo=docker&logoColor=white) ![Licenca](https://img.shields.io/badge/Licenca-MIT-007ec6?style=for-the-badge&logo=opensourceinitiative)

---

## Indice
- [Links Uteis](#-links-uteis)
- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Arquitetura](#-arquitetura)
  - [Diagramas](#diagramas)
- [Modelos de Usuario e Requisitos](#-modelos-de-usuario-e-requisitos)
  - [Descricao de Atores](#descricao-de-atores)
  - [Modelo de Casos de Uso](#modelo-de-casos-de-uso)
  - [Diagramas de Sequencia do Sistema](#diagramas-de-sequencia-do-sistema)
  - [Contratos de Operacao](#contratos-de-operacao)
- [Modelos de Projeto](#-modelos-de-projeto)
- [Modelos de Dados](#-modelos-de-dados)
- [Instalacao e Execucao](#-instalacao-e-execucao)
  - [Pre-requisitos](#pre-requisitos)
  - [Variaveis de Ambiente](#-variaveis-de-ambiente)
  - [Instalacao de Dependencias](#-instalacao-de-dependencias)
  - [Inicializacao do Banco de Dados](#-inicializacao-do-banco-de-dados-postgresql)
  - [Como Executar a Aplicacao](#-como-executar-a-aplicacao)
- [Deploy](#-deploy)
- [Estrutura de Pastas](#-estrutura-de-pastas)
- [Demonstracao](#-demonstracao)
- [Testes](#-testes)
- [Documentacoes Utilizadas](#-documentacoes-utilizadas)
- [Autores](#-autores)
- [Contribuicao](#-contribuicao)
- [Agradecimentos](#-agradecimentos)
- [Licenca](#-licenca)

---

## Links Uteis
* **Demo Online:** [Acesse a Aplicacao Web](https://autofix.vercel.app)
  > Link para a aplicacao em ambiente de producao hospedado na Vercel (frontend) e Railway (backend).
* **Documentacao da API:** [Swagger/OpenAPI](https://api.autofix.railway.app/api-docs)
  > Documentacao interativa dos endpoints REST da API.

---

## Sobre o Projeto

O **AutoFix** nasceu da necessidade real de oficinas mecanicas que ainda operam com fichas de papel, planilhas e comunicacao verbal para gerenciar seus servicos. Este cenario gera:

- **Perda de historico**: servicos anteriores nao sao facilmente recuperaveis.
- **Falta de controle de estoque**: pecas acabam sem aviso, atrasando reparos.
- **Dificuldade no faturamento**: calculos manuais propensos a erros e sem rastreabilidade.
- **Experiencia ruim para o cliente**: sem visibilidade do andamento do servico.

O sistema resolve esses problemas ao oferecer:

- Cadastro centralizado de clientes e veiculos com historico completo.
- Fluxo completo de ordens de servico: abertura, diagnostico, orcamento, aprovacao, execucao, conclusao e pagamento.
- Controle automatico de estoque de pecas com baixa automatica ao vincular a uma OS.
- Painel de gestao para o gerente com visao geral de todas as OS ativas.

**Contexto**: Projeto academico da disciplina Projeto de Software — PUC Minas, 2024/2.

> [!NOTE]
> Este projeto nao possui codigo implementado. Trata-se de um exercicio de **projeto e diagramacao de software**, com foco em modelagem UML, arquitetura e documentacao.

---

## Funcionalidades Principais

- **Cadastro de Clientes:** Registro completo com CPF, telefone, e-mail e endereco. Validacao de CPF unico.
- **Cadastro de Veiculos:** Vinculacao de veiculos a clientes com placa, marca, modelo, ano e quilometragem.
- **Ordens de Servico (OS):** Abertura, atribuicao de mecanico, diagnostico, orcamento, aprovacao, execucao e conclusao.
- **Controle de Estoque:** Gerenciamento de pecas com codigo, precos (custo/venda) e quantidade. Baixa automatica ao usar pecas em OS.
- **Catalogo de Servicos:** Servicos pre-cadastrados com preco de referencia e tempo estimado.
- **Pagamentos:** Processamento com suporte a dinheiro, cartao de credito, cartao de debito e PIX. Controle de status (pendente, aprovado, recusado, estornado).
- **Historico de Servicos:** Consulta completa do historico por cliente ou veiculo.
- **Notificacoes:** Envio de e-mail ao cliente sobre mudancas de status da OS.

---

## Tecnologias Utilizadas

### Frontend

* **Biblioteca:** React 18.3
* **Linguagem:** TypeScript 5.6
* **Build Tool:** Vite 5.4
* **Estilizacao:** Tailwind CSS 3.4
* **Gerenciamento de Estado:** Zustand 4.5
* **Roteamento:** React Router 6.x
* **HTTP Client:** Axios 1.7

### Backend

* **Runtime:** Node.js 20 LTS
* **Framework:** Express.js 4.21
* **Linguagem:** TypeScript 5.6
* **ORM:** Prisma 5.x
* **Banco de Dados:** PostgreSQL 16
* **Autenticacao:** JWT (jsonwebtoken)
* **Validacao:** Zod 3.x
* **Documentacao API:** Swagger (swagger-ui-express)

### Infraestrutura & DevOps

* **Containerizacao:** Docker 27, Docker Compose
* **Frontend Deploy:** Vercel
* **Backend Deploy:** Railway
* **CI/CD:** GitHub Actions
* **Testes:** Jest (backend), Vitest (frontend), Playwright (E2E)

---

## Arquitetura

O AutoFix segue uma **arquitetura em camadas (Layered Architecture)** com separacao clara entre frontend e backend, comunicando-se via API REST.

**Visao geral:**
- **Frontend (React SPA):** Renderizado no navegador, consome a API via HTTPS/JSON.
- **Backend (Express.js API):** API REST stateless com 3 camadas internas — Controller, Service e Repository.
- **Banco de Dados (PostgreSQL):** Persistencia relacional com Prisma como ORM.
- **Servico Externo (SendGrid):** Envio de notificacoes por e-mail.

**Padroes adotados:**
- **Repository Pattern:** Abstrai acesso a dados via Prisma.
- **Service Layer:** Encapsula regras de negocio.
- **DTO Pattern:** Transferencia de dados entre camadas sem expor entidades.
- **Middleware Pattern:** Autenticacao (JWT), validacao (Zod) e tratamento de erros.

### Diagramas

Todos os diagramas foram produzidos em **PlantUML** e estao na pasta [`diagrams/`](./diagrams/).

| Diagrama | Arquivo | Descricao |
| :--- | :--- | :--- |
| **Arquitetura C4** | [`arquitetura-c4-contexto-container.puml`](./diagrams/arquitetura-c4-contexto-container.puml) | Niveis Context e Container do C4 Model |
| **Componentes** | [`diagrama-componentes.puml`](./diagrams/diagrama-componentes.puml) | Componentes internos do backend (Controller/Service/Repository) |
| **Implantacao** | [`diagrama-implantacao.puml`](./diagrams/diagrama-implantacao.puml) | Nodes de deploy: Vercel, Railway, PostgreSQL, SendGrid |
| **Classes** | [`diagrama-classes.puml`](./diagrams/diagrama-classes.puml) | 9 entidades com atributos, metodos e relacionamentos |
| **ERD** | [`modelo-entidade-relacionamento.puml`](./diagrams/modelo-entidade-relacionamento.puml) | Modelo entidade-relacionamento com tipos e FKs |

---

## Modelos de Usuario e Requisitos

### Descricao de Atores

| Ator | Descricao |
| :--- | :--- |
| **Cliente** | Pessoa fisica que traz seu veiculo para manutencao na oficina. Pode consultar o historico de servicos realizados em seus veiculos. Interage com o sistema para acompanhar o andamento de suas ordens de servico. |
| **Mecanico** | Profissional tecnico da oficina, responsavel por diagnosticar problemas, executar servicos e registrar pecas utilizadas. Possui uma especialidade (motor, suspensao, eletrica, funilaria, pintura ou geral). |
| **Gerente** | Administrador da oficina. Responsavel por cadastrar clientes e veiculos, abrir ordens de servico, processar pagamentos e supervisionar o fluxo geral de trabalho. Possui acesso completo ao sistema. |

### Modelo de Casos de Uso

Diagrama completo: [`diagrams/diagrama-casos-de-uso.puml`](./diagrams/diagrama-casos-de-uso.puml)

| ID | Caso de Uso | Ator Principal | Descricao |
| :--- | :--- | :--- | :--- |
| UC-01 | Cadastrar Cliente | Gerente | Registra novo cliente com dados pessoais (nome, CPF, telefone, e-mail, endereco). CPF deve ser unico. |
| UC-02 | Cadastrar Veiculo | Gerente | Vincula um veiculo a um cliente existente com placa, marca, modelo, ano, cor e quilometragem. |
| UC-03 | Abrir Ordem de Servico | Gerente | Cria uma nova OS associando cliente, veiculo e descricao do problema relatado. Status inicial: "Aberta". |
| UC-04 | Registrar Diagnostico | Mecanico | Registra o diagnostico tecnico em uma OS atribuida ao mecanico. Pode incluir observacoes e fotos. |
| UC-05 | Adicionar Servico/Peca a OS | Mecanico | Adiciona itens de servico e/ou pecas a uma OS em execucao. Pecas sofrem baixa automatica no estoque. |
| UC-06 | Concluir Ordem de Servico | Mecanico | Finaliza a execucao da OS, calculando o valor total (servicos + pecas). Status muda para "Concluida". |
| UC-07 | Realizar Pagamento | Gerente | Processa o pagamento de uma OS concluida. Suporta dinheiro, cartao (credito/debito) e PIX. |
| UC-08 | Consultar Historico de Servicos | Cliente / Gerente | Lista todas as OS de um cliente ou veiculo, com detalhes de servicos, pecas e valores. |

### Diagramas de Sequencia do Sistema

Os SSDs modelam a interacao entre ator e sistema como caixa-preta para os 3 casos de uso mais complexos:

| UC | Diagrama |
| :--- | :--- |
| UC-03: Abrir Ordem de Servico | [`diagrams/sequencia-sistema-uc03-abrir-ordem-servico.puml`](./diagrams/sequencia-sistema-uc03-abrir-ordem-servico.puml) |
| UC-06: Concluir Ordem de Servico | [`diagrams/sequencia-sistema-uc06-concluir-ordem-servico.puml`](./diagrams/sequencia-sistema-uc06-concluir-ordem-servico.puml) |
| UC-07: Realizar Pagamento | [`diagrams/sequencia-sistema-uc07-realizar-pagamento.puml`](./diagrams/sequencia-sistema-uc07-realizar-pagamento.puml) |

### Contratos de Operacao

#### Contrato CO-01: abrirOrdemServico

| Campo | Descricao |
| :--- | :--- |
| **Operacao** | `abrirOrdemServico(clienteId, veiculoId, descricaoProblema)` |
| **Referencias cruzadas** | UC-03 (Abrir Ordem de Servico) |
| **Pre-condicoes** | Cliente com `clienteId` existe e esta ativo. Veiculo com `veiculoId` existe e pertence ao cliente. |
| **Pos-condicoes** | Uma instancia de `OrdemServico` foi criada com status "ABERTA". A `OrdemServico` foi associada ao `Cliente` e ao `Veiculo`. O atributo `dataAbertura` foi definido com a data/hora atual. Um `numero` sequencial unico foi atribuido a OS. |

#### Contrato CO-02: concluirOS

| Campo | Descricao |
| :--- | :--- |
| **Operacao** | `concluirOS(osId, diagnostico, servicos[], pecas[])` |
| **Referencias cruzadas** | UC-06 (Concluir Ordem de Servico) |
| **Pre-condicoes** | `OrdemServico` com `osId` existe e esta com status "EM_EXECUCAO". Mecanico esta atribuido a OS. Todas as pecas referenciadas possuem estoque suficiente. |
| **Pos-condicoes** | O atributo `diagnostico` da OS foi atualizado. Instancias de `ItemServico` foram criadas e associadas a OS. Instancias de `ItemPeca` foram criadas e associadas a OS. O `quantidadeEstoque` de cada `Peca` utilizada foi decrementado. O `valorTotal` da OS foi calculado (soma de servicos + pecas). O status da OS foi alterado para "CONCLUIDA". O atributo `dataConclusao` foi definido. |

#### Contrato CO-03: processarPagamento

| Campo | Descricao |
| :--- | :--- |
| **Operacao** | `processarPagamento(osId, valor, formaPagamento)` |
| **Referencias cruzadas** | UC-07 (Realizar Pagamento) |
| **Pre-condicoes** | `OrdemServico` com `osId` existe e esta com status "CONCLUIDA". O `valor` informado corresponde ao `valorTotal` da OS. A `formaPagamento` e valida (DINHEIRO, CARTAO_CREDITO, CARTAO_DEBITO ou PIX). |
| **Pos-condicoes** | Uma instancia de `Pagamento` foi criada e associada a OS. O status do `Pagamento` foi definido como "APROVADO" (em caso de sucesso). O status da `OrdemServico` foi alterado para "PAGA". |

---

## Modelos de Projeto

### Diagramas de Sequencia (Realizacao de Casos de Uso)

Diferente dos SSDs (que tratam o sistema como caixa-preta), estes diagramas mostram a interacao interna entre objetos para realizar cada caso de uso:

| UC | Diagrama |
| :--- | :--- |
| UC-03: Abrir OS | [`diagrams/sequencia-projeto-uc03-abrir-ordem-servico.puml`](./diagrams/sequencia-projeto-uc03-abrir-ordem-servico.puml) |
| UC-06: Concluir OS | [`diagrams/sequencia-projeto-uc06-concluir-ordem-servico.puml`](./diagrams/sequencia-projeto-uc06-concluir-ordem-servico.puml) |
| UC-07: Realizar Pagamento | [`diagrams/sequencia-projeto-uc07-realizar-pagamento.puml`](./diagrams/sequencia-projeto-uc07-realizar-pagamento.puml) |

### Diagramas de Comunicacao

Representacao alternativa das mesmas interacoes dos diagramas de sequencia, com foco na estrutura de objetos e mensagens numeradas:

| UC | Diagrama |
| :--- | :--- |
| UC-03: Abrir OS | [`diagrams/comunicacao-uc03-abrir-ordem-servico.puml`](./diagrams/comunicacao-uc03-abrir-ordem-servico.puml) |
| UC-07: Realizar Pagamento | [`diagrams/comunicacao-uc07-realizar-pagamento.puml`](./diagrams/comunicacao-uc07-realizar-pagamento.puml) |

### Diagramas de Estados

| Entidade | Diagrama | Descricao |
| :--- | :--- | :--- |
| **OrdemServico** | [`diagrams/estados-ordem-servico.puml`](./diagrams/estados-ordem-servico.puml) | 9 estados: Aberta, Em Diagnostico, Orcamento Gerado, Aprovada, Em Execucao, Concluida, Paga, Encerrada, Cancelada |
| **Pagamento** | [`diagrams/estados-pagamento.puml`](./diagrams/estados-pagamento.puml) | 5 estados: Pendente, Processando, Aprovado, Recusado, Estornado |

---

## Modelos de Dados

O modelo de dados relacional esta documentado no diagrama ERD: [`diagrams/modelo-entidade-relacionamento.puml`](./diagrams/modelo-entidade-relacionamento.puml)

### Tabelas do Banco de Dados

| Tabela | Descricao | Registros estimados |
| :--- | :--- | :--- |
| `cliente` | Dados pessoais dos clientes | ~500 |
| `veiculo` | Veiculos vinculados a clientes | ~800 |
| `mecanico` | Profissionais da oficina | ~10 |
| `servico` | Catalogo de servicos oferecidos | ~50 |
| `peca` | Estoque de pecas | ~200 |
| `ordem_servico` | Ordens de servico (entidade central) | ~2.000/ano |
| `item_servico` | Servicos realizados por OS | ~5.000/ano |
| `item_peca` | Pecas utilizadas por OS | ~4.000/ano |
| `pagamento` | Pagamentos vinculados a OS | ~2.000/ano |

### Estrategia de Mapeamento Objeto-Relacional

O mapeamento entre classes do dominio e tabelas do banco utiliza o **Prisma ORM** com as seguintes estrategias:

- **Heranca:** Nao utilizada — todas as entidades sao classes concretas mapeadas diretamente para tabelas.
- **Enumeracoes:** `StatusOS`, `FormaPagamento`, `StatusPagamento` e `Especialidade` sao mapeados como `VARCHAR` com validacao na camada de aplicacao (Zod).
- **Relacionamentos 1:N:** Implementados via chave estrangeira na tabela filha (ex: `veiculo.cliente_id` referencia `cliente.id`).
- **Relacionamento 1:1:** `pagamento.ordem_servico_id` com constraint `UNIQUE` para garantir um unico pagamento por OS.
- **Tabelas associativas:** `item_servico` e `item_peca` funcionam como tabelas intermediarias com atributos proprios (valor, quantidade).
- **Chaves primarias:** UUIDs gerados pela aplicacao (uuid v4) para evitar colisoes e facilitar integracao.
- **Indices:** Criados em `cliente.cpf`, `veiculo.placa`, `peca.codigo` e `ordem_servico.numero` para consultas frequentes.

---

## Instalacao e Execucao

### Pre-requisitos

* **Node.js:** Versao 20.x ou superior (LTS)
* **npm:** Versao 10.x ou superior (incluso no Node.js)
* **PostgreSQL:** Versao 16 ou superior
* **Docker** (Opcional, mas recomendado para o banco de dados)

---

### Variaveis de Ambiente

#### 1. Backend (Express.js)

Crie um arquivo **`.env`** na raiz da pasta `/backend`:

| Variavel | Descricao | Exemplo |
| :--- | :--- | :--- |
| `PORT` | Porta do servidor Express | `3001` |
| `DATABASE_URL` | URL de conexao PostgreSQL (Prisma) | `postgresql://postgres:senha123@localhost:5432/autofix` |
| `JWT_SECRET` | Chave secreta para tokens JWT | `minha_chave_jwt_super_secreta_2024` |
| `JWT_EXPIRES_IN` | Tempo de expiracao do token | `24h` |
| `SENDGRID_API_KEY` | Chave da API SendGrid para e-mails | `SG.xxxxx` |
| `FRONTEND_URL` | URL do frontend (CORS) | `http://localhost:5173` |

#### 2. Frontend (React, Vite)

Crie um arquivo **`.env`** na raiz da pasta `/frontend`:

| Variavel | Descricao | Exemplo |
| :--- | :--- | :--- |
| `VITE_API_URL` | URL base da API Express | `http://localhost:3001/api` |

---

### Instalacao de Dependencias

1. **Clone o Repositorio:**

```bash
git clone https://github.com/mateus-ferrao/autofix.git
cd autofix
```

2. **Instale as Dependencias:**

#### Frontend (React)

```bash
cd frontend
npm install
cd ..
```

#### Backend (Express.js)

```bash
cd backend
npm install
cd ..
```

---

### Inicializacao do Banco de Dados (PostgreSQL)

#### Opcao 1: Docker (Recomendado)

```bash
docker run --name autofix_db -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=senha123 -e POSTGRES_DB=autofix -p 5432:5432 -d postgres:16
```

#### Opcao 2: PostgreSQL local

Crie o banco manualmente:

```sql
CREATE DATABASE autofix;
```

#### Executar Migracoes (Prisma)

```bash
cd backend
npx prisma migrate dev
npx prisma generate
```

---

### Como Executar a Aplicacao

#### Terminal 1: Backend (Express.js)

```bash
cd backend
npm run dev
```

O backend estara disponivel em **http://localhost:3001**.

---

#### Terminal 2: Frontend (React, Vite)

```bash
cd frontend
npm run dev
```

O frontend estara disponivel em **http://localhost:5173**.

---

#### Execucao Local Completa com Docker Compose

```bash
docker-compose up --build -d
```

> O `docker-compose.yml` sobe frontend, backend e PostgreSQL automaticamente.

Para verificar os containers:

```bash
docker ps
```

Para parar:

```bash
docker-compose down
```

---

## Deploy

1. **Build do Projeto:**

```bash
# Frontend
cd frontend
npm run build

# Backend
cd ../backend
npm run build
```

2. **Configuracao do Ambiente de Producao:**

Defina as variaveis de ambiente no Vercel (frontend) e Railway (backend), especialmente `DATABASE_URL`, `JWT_SECRET` e `VITE_API_URL`.

3. **Deploy automatico:**

O projeto utiliza **GitHub Actions** para CI/CD. Cada push na branch `main` dispara:
- Build e testes automatizados
- Deploy do frontend na Vercel
- Deploy do backend no Railway

---

## Estrutura de Pastas

```
.
├── .github/                     # CI/CD (GitHub Actions)
│   └── workflows/
│       ├── ci.yml               # Pipeline de testes
│       └── deploy.yml           # Pipeline de deploy
├── .env.example                 # Exemplo de variaveis de ambiente
├── docker-compose.yml           # Orquestracao dos containers
├── README.md                    # Documentacao principal
├── LICENSE                      # Licenca MIT
│
├── /diagrams                    # Diagramas PlantUML (.puml)
│   ├── diagrama-casos-de-uso.puml
│   ├── sequencia-sistema-uc03-abrir-ordem-servico.puml
│   ├── sequencia-sistema-uc06-concluir-ordem-servico.puml
│   ├── sequencia-sistema-uc07-realizar-pagamento.puml
│   ├── arquitetura-c4-contexto-container.puml
│   ├── diagrama-componentes.puml
│   ├── diagrama-implantacao.puml
│   ├── diagrama-classes.puml
│   ├── sequencia-projeto-uc03-abrir-ordem-servico.puml
│   ├── sequencia-projeto-uc06-concluir-ordem-servico.puml
│   ├── sequencia-projeto-uc07-realizar-pagamento.puml
│   ├── comunicacao-uc03-abrir-ordem-servico.puml
│   ├── comunicacao-uc07-realizar-pagamento.puml
│   ├── estados-ordem-servico.puml
│   ├── estados-pagamento.puml
│   └── modelo-entidade-relacionamento.puml
│
├── /frontend                    # Aplicacao React
│   ├── .env.example
│   ├── Dockerfile
│   ├── vite.config.ts
│   ├── tailwind.config.js
│   ├── tsconfig.json
│   ├── /public
│   ├── /src
│   │   ├── /components          # Componentes reutilizaveis (UI)
│   │   │   ├── Button.tsx
│   │   │   ├── Table.tsx
│   │   │   ├── Modal.tsx
│   │   │   └── StatusBadge.tsx
│   │   ├── /pages               # Paginas/rotas
│   │   │   ├── Dashboard.tsx
│   │   │   ├── Clientes.tsx
│   │   │   ├── Veiculos.tsx
│   │   │   ├── OrdensServico.tsx
│   │   │   ├── Pecas.tsx
│   │   │   └── Pagamentos.tsx
│   │   ├── /services            # Chamadas HTTP (Axios)
│   │   │   ├── api.ts
│   │   │   ├── clienteService.ts
│   │   │   ├── veiculoService.ts
│   │   │   ├── osService.ts
│   │   │   └── pagamentoService.ts
│   │   ├── /hooks               # Hooks personalizados
│   │   ├── /store               # Zustand stores
│   │   ├── /types               # Tipos TypeScript
│   │   ├── /styles              # Estilos globais
│   │   └── /utils               # Funcoes utilitarias
│   ├── package.json
│   └── package-lock.json
│
├── /backend                     # API Express.js
│   ├── .env.example
│   ├── Dockerfile
│   ├── tsconfig.json
│   ├── /prisma
│   │   ├── schema.prisma        # Schema do banco (Prisma)
│   │   └── /migrations          # Migracoes do banco
│   ├── /src
│   │   ├── app.ts               # Configuracao Express
│   │   ├── server.ts            # Entrada da aplicacao
│   │   ├── /controllers
│   │   │   ├── ClienteController.ts
│   │   │   ├── VeiculoController.ts
│   │   │   ├── OrdemServicoController.ts
│   │   │   ├── PagamentoController.ts
│   │   │   ├── PecaController.ts
│   │   │   └── ServicoController.ts
│   │   ├── /services
│   │   │   ├── ClienteService.ts
│   │   │   ├── VeiculoService.ts
│   │   │   ├── OrdemServicoService.ts
│   │   │   ├── PagamentoService.ts
│   │   │   ├── PecaService.ts
│   │   │   └── ServicoService.ts
│   │   ├── /repositories
│   │   │   ├── ClienteRepository.ts
│   │   │   ├── VeiculoRepository.ts
│   │   │   ├── OrdemServicoRepository.ts
│   │   │   ├── PagamentoRepository.ts
│   │   │   ├── PecaRepository.ts
│   │   │   ├── ServicoRepository.ts
│   │   │   ├── ItemServicoRepository.ts
│   │   │   └── ItemPecaRepository.ts
│   │   ├── /middleware
│   │   │   ├── auth.ts
│   │   │   ├── errorHandler.ts
│   │   │   └── validation.ts
│   │   ├── /routes
│   │   │   └── index.ts
│   │   ├── /dtos
│   │   ├── /types
│   │   └── /utils
│   ├── /tests
│   │   ├── /unit
│   │   └── /integration
│   ├── package.json
│   └── package-lock.json
│
└── /tests                       # Testes End-to-End
    ├── playwright.config.ts
    └── /e2e
        ├── clientes.spec.ts
        ├── ordens-servico.spec.ts
        └── pagamentos.spec.ts
```

---

## Demonstracao

### Aplicacao Web

| Tela | Captura de Tela |
| :---: | :---: |
| **Dashboard** | **Listagem de OS** |
| <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Dashboard" width="120px" height="120px"> | <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Listagem OS" width="120px" height="120px"> |
| **Cadastro de Cliente** | **Detalhes da OS** |
| <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Cadastro Cliente" width="120px" height="120px"> | <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Detalhes OS" width="120px" height="120px"> |
| **Estoque de Pecas** | **Pagamento** |
| <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Estoque" width="120px" height="120px"> | <img src="https://joaopauloaramuni.github.io/image/aramunilogo.png" alt="Pagamento" width="120px" height="120px"> |

### Exemplo de Saida no Terminal (API)

```bash
curl -X POST 'http://localhost:3001/api/ordens-servico' \
     -H 'Authorization: Bearer <token>' \
     -H 'Content-Type: application/json' \
     -d '{"clienteId": "uuid-cliente", "veiculoId": "uuid-veiculo", "descricaoProblema": "Motor falhando ao acelerar"}'
```

**Saida Esperada:**
```json
{
  "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "numero": 1042,
  "status": "ABERTA",
  "dataAbertura": "2024-11-15T14:30:00.000Z",
  "descricaoProblema": "Motor falhando ao acelerar",
  "cliente": {
    "id": "uuid-cliente",
    "nome": "Joao Silva"
  },
  "veiculo": {
    "id": "uuid-veiculo",
    "placa": "ABC1D23",
    "modelo": "Honda Civic 2020"
  }
}
```

---

## Testes

### Testes Unitarios e de Integracao

```bash
# Backend (Jest)
cd backend
npm run test

# Frontend (Vitest)
cd frontend
npm run test
```

### Testes End-to-End (E2E)

```bash
npm run test:e2e
```

*Ferramenta utilizada: Playwright*

---

## Autores

| Nome | GitHub | LinkedIn | E-mail |
|------|--------|----------|--------|
| Mateus Ferrão da Costa | <div align="center"><a href="https://github.com/mateusferrao"><img src="https://joaopauloaramuni.github.io/image/github6.png" width="50px" height="50px"></a></div> | <div align="center"><a href="https://www.linkedin.com/in/mateusferrao"><img src="https://joaopauloaramuni.github.io/image/linkedin2.png" width="50px" height="50px"></a></div> | <div align="center"><a href="mailto:mateusferraocosta2000@gmail.com"><img src="https://joaopauloaramuni.github.io/image/gmail3.png" width="50px" height="50px"></a></div> |

---

## Contribuicao

1. Faca um `fork` do projeto.
2. Crie uma branch para sua feature (`git checkout -b feature/minha-feature`).
3. Commit suas mudancas (`git commit -m 'feat: Adiciona nova funcionalidade X'`). **(Utilize [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/))**
4. Faca o `push` para a branch (`git push origin feature/minha-feature`).
5. Abra um **Pull Request (PR)**.

> [!IMPORTANT]
> Por favor, verifique o arquivo [`CONTRIBUTING.md`](./CONTRIBUTING.md) para detalhes sobre nosso guia de estilo de codigo e o processo de submissao de PRs.

---

## Licenca

Este projeto e distribuido sob a **[Licenca MIT](./LICENSE)**.

---
