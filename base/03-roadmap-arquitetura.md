# Roadmap & Arquitetura - Sistema de Reservas para Casas Noturnas

## 🏗️ Arquitetura Geral

### Visão Macro

```
┌─────────────────┐
│  Frontend Web   │  (React/Vue - Desktop/Mobile Web)
│  Mobile App     │  (React Native ou Flutter)
└────────┬────────┘
         │
         ▼
┌─────────────────────────────────┐
│      API Backend                │  (Node.js/Express ou Python/FastAPI)
│  - Auth                         │
│  - CRUD: Casas, Eventos, Promos │
│  - Reservas                     │
│  - Notificações                 │
│  - Analytics                    │
└────────┬────────────────────────┘
         │
    ┌────┴────┬──────────┬─────────────┐
    ▼         ▼          ▼             ▼
  ┌──────┐  ┌──────┐  ┌──────────┐  ┌─────────┐
  │  DB  │  │Cache │  │Instagram │  │ Notif.  │
  │ (SQL)│  │Redis │  │   API    │  │Firebase │
  └──────┘  └──────┘  └──────────┘  └─────────┘
```

### Componentes Principais

| Componente | Tecnologia | Descrição |
|-----------|-----------|-----------|
| **Frontend Web** | React 18 + TypeScript | SPA responsiva, roda em navegador |
| **Mobile** | React Native ou Flutter | App iOS/Android (Fase 2) |
| **Backend API** | Node.js + Express OU Python + FastAPI | Serviços RESTful (ou GraphQL) |
| **Database** | PostgreSQL | Dados persistentes (casas, eventos, reservas, usuários) |
| **Cache** | Redis (opcional) | Sessões, dados quentes (programação atual) |
| **Notificações** | Firebase Cloud Messaging (FCM) | Push notifications |
| **Autenticação** | JWT + OAuth2 | Login com email/senha, Google, Instagram |
| **Storage** | S3 ou Cloudinary | Imagens de eventos/casas |
| **Hosting** | Vercel/Netlify (frontend) + Heroku/Railway/Digital Ocean (backend) | Infraestrutura |

---

## 📅 Roadmap de Desenvolvimento

### ⚡ FASE 0: Prototipagem (1 semana)

**Objetivo:** Validar UX/UI antes de escrever código "sério"

**Deliverables:**
- [ ] Figma/Wireframe da navegação principal
- [ ] Mockup das 5 telas críticas:
  - Home (lista de casas)
  - Detalhe do evento
  - Tela de reserva
  - Meu perfil / minhas reservas
  - Painel gerente (simples)
- [ ] Validação com Luan/usuários
- [ ] Protótipo HTML interativo (opcional, pode fazer com Claude Code depois)

**Esforço:** 1 person-week  
**Stack:** Figma + HTML/CSS/JS (básico)

---

### 🚀 FASE 1: MVP (4-6 semanas)

**Objetivo:** Versão mínima viável com 1 casa piloto

#### Sprint 1.1: Setup + Autenticação (1 semana)

**Backend:**
- [ ] Configurar projeto Node.js/Express + TypeScript
- [ ] Setup database (PostgreSQL)
- [ ] Implementar autenticação (JWT + bcrypt)
- [ ] Endpoints básicos: POST /auth/register, POST /auth/login
- [ ] Validação de email (opcional no MVP)

**Frontend:**
- [ ] Setup React + TypeScript + Vite
- [ ] Configurar routing (React Router)
- [ ] Componentes base (Button, Card, Modal, etc)
- [ ] Tela de login/registro
- [ ] Context ou Redux para estado do usuário

**DevOps:**
- [ ] Setup repositório Git
- [ ] GitHub Actions para CI/CD básico
- [ ] Deploy automático (Vercel/Netlify para frontend)

**Entrega:** Usuário consegue fazer login

---

#### Sprint 1.2: Programação & Casas (1 semana)

**Backend:**
- [ ] CRUD: Casas (GET, POST, PUT, DELETE)
- [ ] CRUD: Eventos/Programação (GET, POST, PUT, DELETE)
- [ ] Endpoints:
  - `GET /casas` - listar todas
  - `GET /casas/:id` - detalhe
  - `GET /casas/:id/eventos` - eventos de uma casa
  - `GET /eventos` - todos os eventos (futuros)

**Frontend:**
- [ ] Tela Home: grid/lista de casas
- [ ] Tela detalhe da casa: info + programação da semana
- [ ] Tela detalhe do evento: horário, DJs, descrição
- [ ] Filtros: por dia da semana, por gênero musical
- [ ] Favoritar casa (salvar em localStorage ou DB)

**Design:**
- [ ] Dark mode? Light mode? Decidir estilo visual
- [ ] Cores do app (paleta visual)
- [ ] Tipografia

**Entrega:** Usuário vê programação de casas, consegue filtrar

---

#### Sprint 1.3: Promoções & Detalhes do Evento (1 semana)

**Backend:**
- [ ] CRUD: Promoções
- [ ] Endpoints:
  - `GET /eventos/:id/promocoes` - promos do evento
  - `POST /promocoes` (admin/gerente)
  - `PUT /promocoes/:id` (admin/gerente)

**Frontend:**
- [ ] Tela detalhe evento expande: mostra promoções com horários
- [ ] Visual claro: combos, descontos, entrada (free/paga)
- [ ] Badge/destaque para "ENTRADA FREE"
- [ ] Timeline de promoções (às 21h muda, etc)

**Entrega:** Usuário vê promoções de forma clara

---

#### Sprint 1.4: Reservas Básicas (1.5 semanas)

**Backend:**
- [ ] CRUD: Reservas
- [ ] Endpoints:
  - `POST /reservas` - criar reserva
  - `GET /reservas/meus` - minhas reservas
  - `GET /eventos/:id/reservas` (gerente) - reservas do evento
  - `DELETE /reservas/:id` - cancelar reserva
  - `PUT /reservas/:id` (gerente) - marcar como "compareceu"

**Validações:**
- [ ] Reserva só funciona se ainda tem espaço
- [ ] Usuário só pode reservar 1x por evento (ou múltiplas vezes?)
- [ ] Resposta deve ser imediata (confirmada) ou sistema avisa depois?

**Frontend:**
- [ ] Tela detalhe evento: botão "RESERVAR"
- [ ] Modal: "Quantas pessoas?" + "Confirmar telefone?"
- [ ] Tela "Minhas Reservas": lista com próximos eventos
- [ ] Poder cancelar reserva (com ação)
- [ ] Confirmação de reserva (toast/popup)

**Notificações:**
- [ ] Enviar notificação quando reserva é confirmada
- [ ] Email de confirmação (opcional)

**Entrega:** Usuário consegue fazer reserva e vê confirmação

---

#### Sprint 1.5: Painel Gerente Básico (1 semana)

**Backend:**
- [ ] Middleware de permissões (usuário é gerente de qual casa?)
- [ ] Endpoints admin:
  - `POST /eventos` - criar evento
  - `PUT /eventos/:id` - editar evento
  - `DELETE /eventos/:id` - deletar evento
  - `GET /casas/:id/reservas` - ver todas as reservas (com filtros)

**Frontend:**
- [ ] Dashboard gerente: visão geral da casa
- [ ] Formulário para criar/editar evento (data, hora, DJs, descrição)
- [ ] Formulário para criar/editar promoção
- [ ] Listagem de reservas (por evento ou geral)
- [ ] Marcar como "compareceu" (check-in simples)

**Autenticação:**
- [ ] Modo "gerente" diferente de usuário comum
- [ ] Acesso restrito (só gerente da casa X vê dados de X)

**Entrega:** Gerente consegue criar eventos e ver reservas

---

#### Sprint 1.6: Polish & Testes (1 semana)

- [ ] Testes unitários (backend + frontend)
- [ ] Testes E2E (Cypress ou Playwright)
- [ ] Review de UX/design
- [ ] Performance (lazy loading, otimizar imagens)
- [ ] Responsividade (mobile, tablet, desktop)
- [ ] Bug fixes, ajustes

**Entrega:** MVP está pronto para soft launch

---

### ✨ FASE 2: Expansão (2-3 semanas)

**Objetivo:** Mais casas, notificações inteligentes, gamificação

#### 2.1 Notificações Inteligentes
- [ ] Permissões de notificação (usuário escolhe casas + tipos)
- [ ] Sistema de notificações (queue + worker)
- [ ] Triggers:
  - Novo evento é publicado
  - Virada de lote (ingresso fica mais caro)
  - Último horário (ainda tem vaga pra hoje)
  - Lembretes (você tem reserva amanhã)
- [ ] Horários: não enviar após 23h, por exemplo
- [ ] Limite de frequência (max 3 notificações/dia por casa)

**Stack:** Bull (job queue) + Redis

---

#### 2.2 Integração Instagram (Embed)
- [ ] Usar Instagram Graph API ou simples iframe
- [ ] Posts da casa aparecem no detalhe (gallery)
- [ ] Link direto pro Instagram

---

#### 2.3 Gamificação Básica
- [ ] Passport: visitas às casas (contador)
- [ ] Pontos por ações (reserva, check-in)
- [ ] Badges (primeirx da casa, visitou todas, etc)
- [ ] Leaderboard (opcional)

**Frontend:** Nova aba "Perfil" com stats

---

#### 2.4 Apoio a Atrações, Festas Itinerantes e Produtores (Ex: Beat Proibido, Cultura Subcult)
- [ ] Cadastro de perfis de artistas e festas (imagem, biografia, redes sociais, grupos oficiais)
- [ ] Implementar feed de shows e edições (vinculado às casas ou locais temporários)
- [ ] Badge visual ("Atração Parceira", "Festa Itinerante") para diferenciar de estabelecimento físico fixo
- [ ] Fluxo para direcionamento para links de vendas externos (ex: Sympla, Eventbrite)
- [ ] Tela/Seção de Créditos & Idealização no app integrando o perfil do Luan (@luan.sbarbosa)

---

#### 2.5 Expandir para Mais Casas
- [ ] Onboarding de gerente de casa
- [ ] Cópia de dados de casas (Instagram, endereço)
- [ ] Testes com cada casa

---

#### 2.6 Analytics Básico
- [ ] Dashboard gerente: views, reservas, presença
- [ ] Gráficos (Recharts ou similar)
- [ ] Relatório por período (semanal, mensal)

---

### 🔥 FASE 3: Monetização & Premium (3-4 semanas)

#### 3.1 Integração de Pagamento
- [ ] Stripe ou Pix (Mercado Pago, PagSeguro)
- [ ] Cobrar entrada via app
- [ ] Processar pagamentos, webhooks
- [ ] Emitir comprovante (PDF)

---

#### 3.2 Anúncios de Virada de Lote
- [ ] Sistema de lotes (ex: 100 ingressos a R$20, depois R$30)
- [ ] Notificar quando muda de lote
- [ ] Urgência visual ("ÚLTIMOS INGRESSOS DO LOTE 1!")

---

#### 3.3 Descontos Dinâmicos
- [ ] Insights: segunda tem low occupancy?
- [ ] Sugerir desconto automático
- [ ] A/B test para ver se funciona

---

#### 3.4 Mobile App (iOS + Android)
- [ ] React Native: reusar lógica do web
- [ ] Ou Flutter para melhor performance
- [ ] App Store + Google Play deployment

---

### 📱 FASE 4: Evolução Contínua

- [ ] User reviews/ratings de eventos
- [ ] Recomendações (ML simples)
- [ ] Social features (compartilhar reserva, convidar amigos)
- [ ] Integração com Sympla (eventos com ingresso lá)
- [ ] IA gerando descrições de eventos (prompt templates)
- [ ] Dark mode
- [ ] Internationalization (EN, ES)

---

## 🛠️ Stack Técnico Recomendado (MVP)

### Frontend
```javascript
Framework: React 18 + TypeScript
State: Zustand ou Redux Toolkit
UI Components: Shadcn/ui ou Material-UI
Routing: React Router v6
HTTP: Axios ou Fetch API + react-query
Styling: Tailwind CSS
Bundler: Vite
Tests: Vitest + React Testing Library
Linting: ESLint + Prettier
```

### Backend
```javascript
Runtime: Node.js (v20+)
Framework: Express.js + TypeScript
Database: PostgreSQL + Prisma ORM
Auth: jsonwebtoken (JWT) + bcrypt
Validation: Zod ou joi
Logging: Winston ou Pino
Email: Nodemailer ou SendGrid
Tests: Jest + Supertest
Linting: ESLint + Prettier
```

### DevOps
```
VCS: GitHub
CI/CD: GitHub Actions
Frontend Hosting: Vercel ou Netlify
Backend Hosting: Railway, Heroku, ou Digital Ocean App Platform
Database: PostgreSQL Managed (Railway, Supabase, PlanetScale)
CDN: Cloudflare (grátis)
Container: Docker (opcional, mas recomendado)
```

---

## 📊 Estrutura de Pastas (Recomendada)

### Frontend
```
src/
├── app/
│   ├── App.tsx
│   └── main.tsx
├── components/
│   ├── common/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   └── Modal.tsx
│   ├── layout/
│   │   ├── Header.tsx
│   │   ├── Sidebar.tsx
│   │   └── Footer.tsx
│   └── features/
│       ├── auth/
│       ├── casa/
│       ├── evento/
│       ├── reserva/
│       └── gerente/
├── pages/
│   ├── Home.tsx
│   ├── CasaDetail.tsx
│   ├── EventoDetail.tsx
│   ├── Reservas.tsx
│   ├── Gerente/
│   └── 404.tsx
├── hooks/
│   ├── useAuth.ts
│   ├── useReserva.ts
│   └── useCasa.ts
├── services/
│   ├── api.ts (configuração axios)
│   ├── authService.ts
│   ├── casaService.ts
│   └── reservaService.ts
├── store/
│   ├── authStore.ts (Zustand)
│   └── appStore.ts
├── types/
│   └── index.ts (TypeScript interfaces)
├── utils/
│   ├── formatters.ts
│   └── validators.ts
├── styles/
│   └── globals.css (Tailwind)
└── env.d.ts
```

### Backend
```
src/
├── app.ts (setup express)
├── server.ts (start server)
├── middleware/
│   ├── auth.ts
│   ├── errorHandler.ts
│   └── cors.ts
├── routes/
│   ├── auth.routes.ts
│   ├── casa.routes.ts
│   ├── evento.routes.ts
│   ├── reserva.routes.ts
│   └── gerente.routes.ts
├── controllers/
│   ├── authController.ts
│   ├── casaController.ts
│   ├── eventoController.ts
│   ├── reservaController.ts
│   └── gerenteController.ts
├── services/
│   ├── authService.ts
│   ├── casaService.ts
│   ├── eventoService.ts
│   └── reservaService.ts
├── models/ (Prisma schemas)
│   └── schema.prisma
├── utils/
│   ├── jwt.ts
│   ├── validators.ts
│   └── errors.ts
├── config/
│   ├── env.ts
│   ├── database.ts
│   └── logger.ts
├── types/
│   └── index.ts
└── __tests__/
    ├── unit/
    └── integration/
```

---

## 🔐 Segurança (MVP)

- [ ] HTTPS sempre (obrigatório em produção)
- [ ] CORS configurado corretamente
- [ ] Rate limiting (para evitar brute force, DDoS)
- [ ] Input validation (Zod/joi no backend)
- [ ] Password hashing (bcrypt, min 12 rounds)
- [ ] JWT com expiração (15 min access, 7 dias refresh)
- [ ] SQL injection prevention (usar ORM: Prisma)
- [ ] XSS prevention (React sanitiza por default)
- [ ] CSRF tokens (se usar sessões em vez de JWT)
- [ ] Environment variables (.env.local, não committar)

---

## 📈 Performance & Escalabilidade (MVP)

- [ ] Lazy loading de imagens
- [ ] Code splitting (React.lazy + Suspense)
- [ ] Compressão Gzip (Express middleware)
- [ ] Cache de programação (Redis, 1h TTL)
- [ ] Pagination em listagens (20 itens/página)
- [ ] Indexação de database (eventos por dia, reservas por usuário)
- [ ] CDN para assets estáticos
- [ ] Monitoring (Sentry para erros, ou simple logging)

---

## 🧪 Testing Strategy (MVP)

### Frontend
- Unit tests: componentes isolados (React Testing Library)
- Integration tests: fluxo completo (Cypress)
- Coverage target: 70%+

### Backend
- Unit tests: services, validators (Jest)
- Integration tests: endpoints (Supertest)
- Coverage target: 80%+

---

## 📝 Documentação (MVP)

- [ ] README.md (setup, como rodar localmente)
- [ ] API docs (Swagger/OpenAPI)
- [ ] Database schema (diagrama)
- [ ] Architecture decision records (ADRs)

---

## 🚢 Deployment (MVP)

### Desenvolvimento
```bash
npm run dev  # Frontend
npm run dev  # Backend
```

### Staging
- Deploy automático a cada merge em `develop`
- Teste manual da feature

### Produção
- Deploy automático a cada tag/release
- Rollback rápido se houver problema

---

## 💰 Estimativa de Esforço

| Fase | Duração | FTEs | Total de Horas |
|------|---------|------|-----------------|
| **Fase 0** (Prototipagem) | 1 semana | 1 | 40h |
| **Fase 1** (MVP) | 5 semanas | 2 (dev + design) | 400h |
| **Fase 2** (Expansão) | 3 semanas | 2 | 240h |
| **Fase 3** (Monetização) | 3 semanas | 2 | 240h |
| **Total até Fase 3** | **12 semanas** | **2 devs** | **~920h** |

**FTE = Full-Time Equivalent (pessoa trabalhando 40h/semana)**

Se 2 devs trabalham em paralelo + 1 designer parcial = ~3-4 meses até versão com monetização.

---

## ⚠️ Riscos & Mitigações

| Risco | Impacto | Probabilidade | Mitigação |
|-------|---------|---------------|-----------|
| Escopo creep (mais features que o planejado) | Alto | Alta | MVP bem definido, nada de "só adicionamos" |
| Casas não usam o painel | Alto | Média | Onboarding forte, treinamento, suporte |
| Baixa adoção de usuários | Médio | Média | Marketing desde o start, community building |
| Problema técnico (DB, API) | Alto | Baixa | Testes rigorosos, monitoria, alertas |
| Timeline estoura | Médio | Média | 2-3 devs paralelo, priorizar features críticas |
| Integração Instagram falha | Baixo | Baixa | Instagram é nice-to-have, deixa pra Fase 2 |

---

## 🎯 Métricas de Sucesso (Fase 1)

- [ ] **Funcionalidade:** MVP funciona sem bugs críticos
- [ ] **Usabilidade:** Usuário consegue fazer reserva em < 5 cliques
- [ ] **Performance:** Página carrega em < 3s (Lighthouse 80+)
- [ ] **Cobertura:** 70%+ testes
- [ ] **Segurança:** Passa security scan (OWASP)
- [ ] **Adoção:** 100+ usuários ativos em 1 mês
- [ ] **Satisfação:** NPS > 40 (feedback de usuários)

---

**Data de criação:** 15/07/2026  
**Última atualização:** Pré-conversa  
**Status:** Proposta - Aguardando validação com Luan

---

## 📚 Referências Úteis

- **React Learning:** https://react.dev
- **Express.js:** https://expressjs.com
- **Prisma ORM:** https://www.prisma.io
- **Tailwind CSS:** https://tailwindcss.com
- **TypeScript Handbook:** https://www.typescriptlang.org/docs
- **REST API Best Practices:** https://restfulapi.net
- **Security Checklist:** https://cheatsheetseries.owasp.org

