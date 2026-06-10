# 🛒 ShopFlow – Sistema de E-commerce (Loja Virtual) 👨‍💻

> [!NOTE]
> O ShopFlow digitaliza o fluxo completo de uma loja virtual — da navegação no catálogo à entrega do pedido — centralizando carrinho de compras, pedidos, estoque, pagamentos e notificações em uma única plataforma web.

<table>
  <tr>
    <td width="800px">
      <div align="justify">
        O <b>ShopFlow</b> é uma plataforma de comércio eletrônico para lojas de pequeno e médio porte. Ele organiza o ciclo de venda em torno do <b>Pedido</b>: navegação no catálogo com busca e categorias, gerenciamento de carrinho com verificação de estoque, checkout com múltiplos meios de pagamento (cartão, Pix e boleto), confirmação automática via gateway, rastreamento da entrega e avaliação do produto. Este repositório contém a <i>documentação de projeto</i> (Trabalho 2 da disciplina Projeto de Software), incluindo todos os diagramas UML elaborados em <b>PlantUML</b>.
      </div>
    </td>
    <td>
      <div align="center">
        🛒📦
      </div>
    </td>
  </tr>
</table>

---

## 🚧 Status do Projeto

[![Versão](https://img.shields.io/badge/Versão-v1.0.0-blue?style=for-the-badge)]() ![TypeScript](https://img.shields.io/badge/TypeScript-5.x-007ec6?style=for-the-badge&logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/React-18-007ec6?style=for-the-badge&logo=react&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-14-007ec6?style=for-the-badge&logo=nextdotjs&logoColor=white) ![NestJS](https://img.shields.io/badge/NestJS-10-007ec6?style=for-the-badge&logo=nestjs&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-007ec6?style=for-the-badge&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-7-007ec6?style=for-the-badge&logo=redis&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-Compose-007ec6?style=for-the-badge&logo=docker&logoColor=white) ![Status](https://img.shields.io/badge/Status-Documentação%20de%20Projeto-yellow?style=for-the-badge)

> ⚠️ **Escopo do trabalho:** apenas projeto / diagramação / arquitetura. Não há código de implementação neste repositório.

---

## 📚 Índice
- [Links Úteis](#-links-úteis)
- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Arquitetura](#-arquitetura)
- [Instalação e Execução](#-instalação-e-execução)
- [Deploy](#-deploy)
- [Estrutura de Pastas](#-estrutura-de-pastas)
- [Demonstração](#-demonstração)
- [Testes](#-testes)
- [Documentações utilizadas](#-documentações-utilizadas)
- [Autores](#-autores)
- [Contribuição](#-contribuição)
- [Agradecimentos](#-agradecimentos)
- [Licença](#-licença)

---

## 🔗 Links Úteis
* 🌐 **Demo Online:** *(não aplicável — projeto sem implementação)*
* 📖 **Documentação:** [Documentação de Projeto (PDF)](./docs/Documentação_de_Projeto_ShopFlow_Thiago_Costa_Soares.pdf)
* 🧩 **Diagramas PlantUML:** [/diagramas](./diagramas)
* 🖼️ **Diagramas Renderizados (PNG):** [/diagramas/png](./diagramas/png)
* 🖥️ **Editor PlantUML Online:** [plantuml.com](https://plantuml.com/)

---

## 📝 Sobre o Projeto

Pequenos lojistas que migram para a venda online frequentemente improvisam com planilhas, redes sociais e controles manuais: pedidos se perdem, o estoque anunciado diverge do real e o cliente não tem visibilidade do status da compra. O ShopFlow nasce nesse contexto acadêmico (disciplina **Projeto de Software**) para projetar uma solução que resolva essas dores.

- **Por que existe:** eliminar retrabalho e perda de informação no fluxo de venda online.
- **Problema que resolve:** controle confiável de catálogo, carrinho, pedido, estoque, pagamento e entrega em um único lugar.
- **Contexto:** acadêmico, com regras de negócio realistas de uma loja virtual.
- **Onde pode ser usado:** lojas virtuais independentes e pequenos varejistas em transição para o digital.

O valor central é o **ciclo de vida rastreável do Pedido** (Aguardando Pagamento → Confirmado → Em Preparação → Enviado → Entregue, com cancelamento controlado), garantindo que nenhum pedido seja confirmado sem pagamento aprovado (RN-01) e que todo item vendido tenha baixa em estoque (RN-02), com preço congelado no momento da compra (RN-03).

---

## ✨ Funcionalidades Principais

- 🔐 **Autenticação Segura:** cadastro e login de clientes e administradores com token JWT (UC-01).
- 🗂️ **Catálogo de Produtos:** navegação por categorias, busca por nome e faixa de preço (UC-02, UC-03, UC-04).
- 🛒 **Carrinho de Compras:** adição, remoção e alteração de quantidades com verificação de estoque (UC-05).
- 💳 **Checkout e Pagamentos:** finalização de pedido com cartão de crédito/débito, Pix e boleto via gateway externo (UC-06, UC-07).
- 🚚 **Rastreamento de Pedidos:** consulta de status e histórico de entrega via API de entrega (UC-08).
- ⭐ **Avaliações:** nota e comentário liberados somente após a entrega do produto — RN-04 (UC-09).
- 🔩 **Gestão de Produtos e Estoque:** CRUD de produtos/categorias e alertas de estoque mínimo (UC-10, UC-11).
- 📦 **Gestão de Pedidos:** acompanhamento e atualização do ciclo de vida pelos administradores (UC-12).
- 📊 **Relatórios Gerenciais:** vendas por período, pedidos por status e giro de estoque (UC-13).
- 📧 **Notificações Transacionais:** e-mails automáticos de confirmação e mudança de status (UC-14).

---

## 🛠 Tecnologias Utilizadas

### 💻 Front-end
* **Framework/Biblioteca:** React 18 + Next.js 14 (Web) e React Native (Mobile)
* **Linguagem/Superset:** TypeScript 5
* **Estilização:** Tailwind CSS + shadcn/ui
* **Gerenciamento de Estado:** Context API + TanStack Query
* **Build Tool:** Vite / Next.js

### 🖥️ Back-end
* **Linguagem/Runtime:** Node.js 20 LTS (TypeScript)
* **Framework:** NestJS 10 (microsserviços)
* **Banco de Dados:** PostgreSQL 16
* **Cache / Sessões:** Redis 7
* **ORM / Query Builder:** Prisma
* **Autenticação:** JWT (emitido no API Gateway)

### ⚙️ Infraestrutura & DevOps
* **Containerização:** Docker e Docker Compose
* **Orquestração:** Kubernetes (EKS)
* **Cloud:** AWS — RDS (PostgreSQL), ElastiCache (Redis), S3 + CDN (imagens), ALB
* **CI/CD:** GitHub Actions

### 🧩 Modelagem
* **Diagramas:** PlantUML (todos os códigos-fonte em [/diagramas](./diagramas))

---

## 🏗 Arquitetura

O ShopFlow segue uma **arquitetura em camadas com decomposição em microsserviços**:

- **Apresentação (Web/Mobile):** SPA em React/Next.js e app React Native consumindo a API JSON.
- **Borda (API Gateway):** ponto único de entrada — autenticação JWT, rate limiting e roteamento.
- **Aplicação (Microsserviços):** serviços independentes por domínio — Autenticação, Catálogo, Carrinho, Pedidos, Pagamento e Notificação.
- **Dados:** PostgreSQL para dados transacionais, Redis para cache/sessões e S3 para imagens.
- **Integração:** componentes dedicados para gateway de pagamento, API de entrega e serviço de e-mail.

**Padrões adotados:** Controller, Service Layer, Repository, DTOs, State (ciclo de vida do Pedido) e injeção de dependências.

**Decisões e trade-offs:** optou-se por **microsserviços por domínio de negócio** (D-01) para permitir escala independente do catálogo (alta leitura) em relação a pedidos/pagamentos (alta consistência); o custo é maior complexidade operacional, mitigada pelo Kubernetes gerenciado. A API stateless com JWT centralizado no Gateway (D-02) simplifica a segurança e o deploy horizontal.

### Exemplos de diagramas

| Diagrama | Arquivo PlantUML |
| :--- | :--- |
| Casos de Uso | [`UC-ECommerce.puml`](./diagramas/UC-ECommerce.puml) |
| DSS (UC-01, UC-05, UC-06) | [`SD-UC01-Login`](./diagramas/SD-UC01-Login.puml) · [`SD-UC05-Carrinho`](./diagramas/SD-UC05-Carrinho.puml) · [`SD-UC06-FinalizarPedido`](./diagramas/SD-UC06-FinalizarPedido.puml) |
| Arquitetura | [`Arquitetura-ECommerce.puml`](./diagramas/Arquitetura-ECommerce.puml) |
| Componentes / Implantação | [`Componentes`](./diagramas/Componentes-ECommerce.puml) · [`Implantacao`](./diagramas/Implantacao-ECommerce.puml) |
| Classes | [`Classes-ECommerce.puml`](./diagramas/Classes-ECommerce.puml) |
| Comunicação | [`Comunicacao-FinalizarPedido.puml`](./diagramas/Comunicacao-FinalizarPedido.puml) |
| Estados (Pedido) | [`Estado-Pedido.puml`](./diagramas/Estado-Pedido.puml) |
| Modelo de Dados (DER) | [`ER-ECommerce.puml`](./diagramas/ER-ECommerce.puml) |

---

## 🔧 Instalação e Execução

> ⚠️ Seção ilustrativa: descreve como o sistema **seria** executado caso implementado.

### Pré-requisitos
* **Node.js:** v20 LTS ou superior
* **Docker / Docker Compose**
* **Gerenciador de Pacotes:** npm

### 🔑 Variáveis de Ambiente

#### 1️⃣ Back-end (NestJS)
```env
DATABASE_URL=postgresql://shopflow:shopflow@localhost:5432/shopflow
REDIS_URL=redis://localhost:6379
JWT_SECRET=troque-este-segredo
GATEWAY_PAGAMENTO_URL=https://api.gateway-exemplo.com
GATEWAY_PAGAMENTO_TOKEN=token-ficticio
API_ENTREGA_URL=https://api.correios-exemplo.com
SMTP_URL=smtp://usuario:senha@smtp.sendgrid-exemplo.net:587
S3_BUCKET=shopflow-imagens-produtos
```

#### 2️⃣ Front-end (Next.js)
```env
NEXT_PUBLIC_API_BASE_URL=http://localhost:8080/api
```

### 📦 Instalação de Dependências

#### Front-end (Next.js)
```bash
cd frontend
npm install
```

#### Back-end (NestJS)
```bash
cd backend
npm install
```

### 🗄 Inicialização do Banco de Dados e Cache (PostgreSQL + Redis)
```bash
docker run -d --name postgres-shopflow -e POSTGRES_DB=shopflow \
  -e POSTGRES_USER=shopflow -e POSTGRES_PASSWORD=shopflow -p 5432:5432 postgres:16

docker run -d --name redis-shopflow -p 6379:6379 redis:7
```

### ▶️ Como Executar a Aplicação

#### Terminal 1: Back-end (NestJS)
```bash
cd backend && npm run start:dev
```

#### Terminal 2: Front-end (Next.js)
```bash
cd frontend && npm run dev
```

#### 🐳 Execução Local Completa com Docker Compose
```bash
docker compose up --build
```

---

## 🚀 Deploy

- **Front-end:** build estático (`npm run build`) publicado na Vercel, com imagens servidas via CDN.
- **Back-end:** microsserviços em containers Docker orquestrados por Kubernetes (EKS), atrás de um Application Load Balancer.
- **Dados:** PostgreSQL gerenciado (RDS), Redis (ElastiCache) e imagens de produtos em S3.
- **CI/CD:** GitHub Actions executa build, testes e publicação das imagens a cada push na `main`.

---

## 📁 Estrutura de Pastas

```text
shopflow/
├── docs/
│   └── Documentação_de_Projeto_ShopFlow_Thiago_Costa_Soares.pdf
├── diagramas/
│   ├── UC-ECommerce.puml
│   ├── SD-UC01-Login.puml
│   ├── SD-UC05-Carrinho.puml
│   ├── SD-UC06-FinalizarPedido.puml
│   ├── Arquitetura-ECommerce.puml
│   ├── Componentes-ECommerce.puml
│   ├── Implantacao-ECommerce.puml
│   ├── Classes-ECommerce.puml
│   ├── Comunicacao-FinalizarPedido.puml
│   ├── Estado-Pedido.puml
│   ├── ER-ECommerce.puml
│   └── png/                # diagramas renderizados
└── README.md
```

---

## 🎬 Demonstração

### 💻 Aplicação Web
*(não aplicável — o escopo do trabalho é exclusivamente o projeto/diagramação; as telas seriam: vitrine do catálogo com busca e filtros, página de produto com avaliações, carrinho/checkout em etapas e painel administrativo com pedidos por status)*

### 🖥️ Exemplo de saída no Terminal (para Back-end, API, CLI)
```text
2026-06-09T10:00:00  LOG  [Bootstrap] Serviço de Pedidos iniciado na porta 8084
2026-06-09T10:01:12  LOG  [PedidoService] Pedido 2026-000457 criado (status=AGUARDANDO_PAGAMENTO)
2026-06-09T10:01:15  LOG  [PagamentoService] Transação tx_9f3a aprovada — Pedido 2026-000457 → CONFIRMADO
```

---

## 🧪 Testes

Estratégia prevista:
- **Unitários (Jest):** regras de negócio dos Services (transições de StatusPedido, cálculo de totais, reserva e baixa de estoque).
- **Integração (Supertest + Testcontainers):** endpoints dos microsserviços contra PostgreSQL e Redis reais em containers.
- **Front-end (Vitest + React Testing Library):** componentes críticos de carrinho e checkout.
- **E2E (Playwright):** fluxo completo de compra — do catálogo à confirmação do pedido.

---

## 📖 Documentações utilizadas

* [PlantUML](https://plantuml.com/)
* [NestJS](https://docs.nestjs.com/)
* [Prisma](https://www.prisma.io/docs)
* [React](https://react.dev/)
* [Next.js](https://nextjs.org/docs)
* [PostgreSQL 16](https://www.postgresql.org/docs/16/)
* [Redis](https://redis.io/docs/)
* Larman, C. *Utilizando UML e Padrões* (contratos de operação e DSS)

---

## 👥 Autores

| Aluno | Curso | Instituição |
| :--- | :--- | :--- |
| **Thiago Costa Soares** | Engenharia de Software | *(sua instituição)* |

Trabalho **individual** da disciplina **Projeto de Software**.

---

## 🤝 Contribuição

Por se tratar de um trabalho acadêmico individual, contribuições externas não são aceitas. Sugestões podem ser registradas via *Issues*.

---

## 🙏 Agradecimentos

Ao professor da disciplina de Projeto de Software pelo template de documentação e pelas orientações de modelagem.

---

## 📄 Licença

Este projeto é de uso acadêmico. Distribuído sob a licença **MIT** para fins de estudo.
