# 🤖 Agents Server

Sistema backend para gerenciamento de agentes de IA construído com Node.js e TypeScript.

## 🚀 Tecnologias

- **Node.js** com TypeScript nativo (`--experimental-strip-types`)
- **Fastify** - Framework web rápido e eficiente
- **Drizzle ORM** - ORM type-safe para PostgreSQL
- **PostgreSQL** com extensão **pgvector** para operações de AI
- **Zod** - Validação de schemas e tipos
- **Biome** - Linting e formatação de código
- **Docker** - Containerização do banco de dados

## 📁 Padrões de Projeto

- **Arquitetura modular** com separação clara de responsabilidades
- **Type-safe** com validação de schemas usando Zod
- **Database-first** com migrations e schemas organizados
- **Environment-based configuration** para diferentes ambientes
- **RESTful API** com validação automática de tipos

## ⚙️ Configuração e Setup

### 1. Pré-requisitos

- Node.js 20+
- Docker e Docker Compose

### 2. Instalação

```bash
# Instalar dependências
npm install

# Iniciar banco de dados
docker-compose up -d

# Criar arquivo de ambiente
cp .env.example .env
```

### 3. Variáveis de Ambiente

Criar arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Executar Migrações

```bash
# Gerar migrations (se necessário)
npx drizzle-kit generate

# Aplicar migrations
npx drizzle-kit migrate

# Popular banco com dados iniciais
npm run db:seed
```

### 5. Executar Aplicação

```bash
# Desenvolvimento
npm run dev

# Produção
npm start
```

## 🔗 Endpoints

- `GET /health` - Health check da aplicação
- `GET /rooms` - Listar salas disponíveis

## 🐳 Docker

O projeto inclui configuração Docker Compose para PostgreSQL com extensão pgvector:

```bash
docker-compose up -d
```

## 📝 Scripts Disponíveis

- `npm run dev` - Executa em modo desenvolvimento com hot reload
- `npm start` - Executa em modo produção
- `npm run db:seed` - Popula o banco com dados iniciais

## 🏗️ Estrutura do Projeto

```
src/
├── db/           # Configuração e schemas do banco
├── http/         # Rotas e handlers HTTP
├── env.ts        # Validação de variáveis de ambiente
└── server.ts     # Configuração principal do servidor
```
