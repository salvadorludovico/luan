# Definições Pendentes & Perguntas Críticas

## 🎯 Questões para a Conversa com Luan

### 📊 SOBRE O NEGÓCIO

#### MVP & Prioridade
- [ ] **Qual é a casa prioritária para começar?** (Môi, Point, Mosaic, Vernissage, Fluxo, Cajuína?)
  - Por que essa casa? (volume, disponibilidade, comprometimento?)
  - As outras virão depois?

- [ ] **Qual é o problema mais urgente que o app precisa resolver?**
  - Pessoas não sabem que eventos/promoções existem?
  - Dificuldade em fazer/gerenciar reservas (fila, desistência)?
  - Falta de controle sobre lotação/ocupação?
  - Perda de clientes por falta de comunicação?

- [ ] **Timeline realista?** Quanto vocês conseguem investir em desenvolvimento?
  - 4-6 semanas é factível ou precisa ser mais rápido?
  - Qual é o deadline ideal?

#### Modelo de Receita
- [ ] **Como vocês pretendem ganhar com isso?**
  - Comissão por reserva confirmada? (quantos %?)
  - Taxa mensal por casa? (quanto?)
  - Porcentagem do ingresso vendido?
  - Premium features para gerentes?
  - Publicidade/anúncios no app?
  - Ou simplesmente aumentar ocupação nas casas?

- [ ] **As casas pagariam por usar?** Ou seria valor zero enquanto testa?

#### Audiência & Escala
- [ ] **Quantas pessoas acompanham essas casas hoje?**
  - Total de seguidores no Instagram (soma de todas)?
  - Conversão esperada para o app?
  - Qual é a meta de usuários no primeiro mês/trimestre?

---

### 🔄 SOBRE RESERVAS (Core Feature)

#### Fluxo Atual
- [ ] **Como funciona a reserva hoje?** 
  - Telefonema? WhatsApp? Instagram DM?
  - Quanto tempo leva pra confirmar?
  - Qual é a taxa de desistência?

#### Requisitos Técnicos
- [ ] **Como funciona a confirmação de reserva?**
  - A casa confirma automaticamente (até lotação máxima)?
  - Ou precisa de aprovação manual do gerente?
  - Confirmação imediata ou recebe mensagem depois?

- [ ] **Quanto tempo antes do evento as pessoas reservam?**
  - No dia? 1-2 dias antes? 1 semana?
  - Afeta o design da notificação?

- [ ] **Limite de lugares por noite?**
  - Varia por dia (sexta é lotado, quarta tem espaço)?
  - Como determinar capacidade?
  - Precisa avisar quando está lotado?

- [ ] **Cancelamento de reserva**
  - Usuário pode cancelar até quando?
  - Casa pode desabilitar reservas em eventos específicos?

- [ ] **Identificação do usuário**
  - Email + Senha? Social login (Google/Instagram)?
  - Precisa de foto/ID para validar presença?
  - Telefone é obrigatório?

#### Integração com Pagamento
- [ ] **Haverá cobrança de entrada no app?**
  - Sim: quanto, como pagar (débito, crédito, Pix)?
  - Não: por enquanto é só confirmação?

- [ ] **Se houver pagamento, quem recebe?**
  - App fica com taxa? Quanto?
  - Casa recebe via transferência? Pix?

---

### 📢 SOBRE NOTIFICAÇÕES

#### Estratégia
- [ ] **Quando notificar?**
  - Quando novo evento é publicado?
  - Virada de lote (ingresso fica mais caro)?
  - Último horário (ainda tem lugar pra hoje)?
  - Lembretes (você tem reserva amanhã)?

- [ ] **Como não incomodar?**
  - Usuário escolhe quais casas quer notificações?
  - Pode ligar/desligar por tipo de notificação?
  - Frequência máxima de notificações por dia?

- [ ] **Qual é o poder esperado das notificações?**
  - Aumentar ocupação em dias vazios?
  - Converter "interessado" em "confirmado"?
  - Trazer pessoas que desistiram?

---

### 🎨 SOBRE CONTEÚDO & MÍDIAS

#### Instagram
- [ ] **Integração com Instagram é crítica no MVP?**
  - Posts do Instagram aparecem no app?
  - Só o evento ou a promoção também?
  - Link direto pra comprar ingresso no Sympla (alguns eventos)?

#### IA para Criar Posts
- [ ] **Vocês querem IA gerando texto dos eventos?**
  - Template/modelo que IA preenchere com detalhes?
  - Ou copiar manualmente do Instagram pro app?
  - Prioridade alta ou baixa pra MVP?

#### Mídias (Fotos/Vídeos)
- [ ] **Como a casa forneceria fotos/vídeos do evento?**
  - Upload manual no app?
  - Puxar do Instagram automaticamente?
  - Câmera ao vivo/stories?

---

### 👥 SOBRE PAPÉIS & GERENTES

#### Quem Usa o App?
- [ ] **Papéis no sistema:**
  - Usuário comum (reserva, vê programação, recebe notificações)
  - Gerente de casa (controla programação, vê reservas)
  - Admin da plataforma (suporte, relatórios)
  - Outros? (Marketing da casa? DJ?)

- [ ] **Como o gerente atualiza programação?**
  - Painel web simples?
  - App mobile também?
  - Form com todos os detalhes ou editor visual?

- [ ] **Quem cria as promoções?**
  - Gerente da casa? Marketing?
  - App auxilia com templates/sugestões?

---

### 🎮 SOBRE GAMIFICAÇÃO

#### Se Quiser Implementar
- [ ] **Qual é a gamificação ideal?**
  - Passport/passaporte (visita todas as casas)?
  - Pontos por reserva/check-in? Resgata em quê?
  - Badges/troféus por desafios?
  - Ranking (top visitantes)?

- [ ] **Quando implementar?**
  - MVP já tem? Ou é Fase 2?

- [ ] **Objetivo da gamificação:**
  - Pura diversão ou aumentar frequência?
  - Pode oferecer desconto no app (ex: 10 visitas = 50 off)?

---

### 📈 SOBRE ANALYTICS & DADOS

#### Para os Gerentes
- [ ] **Quais dados importam pro gerente?**
  - Quantas pessoas viram o evento?
  - Quantas fizeram reserva?
  - Quantas realmente foram? (via check-in)
  - Taxa de conversão (visualização → reserva → presença)?

- [ ] **Reports/Dashboard:**
  - Semanal? Mensal?
  - Visual ou exportar em Excel/PDF?

#### Para a Plataforma
- [ ] **Monitoramento (Audit Log):**
  - Crítico desde o start?
  - Rastrear edições de programação?
  - Rastrear cancelamentos de reserva?

---

### 🚀 SOBRE ROADMAP

#### Sequência de Lançamento
- [ ] **MVP mínimo (Semana 1):**
  - Apenas browse + programação + promoções (sem reserva ainda)?
  - Ou já com reserva no dia 1?

- [ ] **Quando expandir para mais casas?**
  - Depois que MVP tiver estável (2 semanas)?
  - Depois que atingir N usuários?
  - Assim que cada casa pedir?

- [ ] **Prioridade das features:**
  - Se tivesse que cortar 3 features, quais seriam?
  - Qual feature gera mais valor/impacto?

---

### 💻 SOBRE TÉCNICA

#### Plataforma
- [ ] **Web, Mobile ou ambos?**
  - MVP é web + mobile (React Native)?
  - Ou começa só web e mobile depois?

#### Infraestrutura
- [ ] **Hospedagem/Cloud:**
  - Prefere gerenciado (Firebase, Vercel)?
  - Ou VPS/self-hosted?
  - Budget para infraestrutura?

#### Integração
- [ ] **APIs necessárias:**
  - Instagram API (embed posts)?
  - Sympla API (se tiver ingresso lá)?
  - Pagamento (Stripe, PagSeguro, Pix)?

---

## 📋 DECISÕES CRÍTICAS A TOMAR

| Decisão | Opção A | Opção B | Opção C | Status |
|---------|---------|---------|---------|--------|
| **Começar com quantas casas?** | 1 (piloto) | 2-3 | Todas 6 | ❓ |
| **Reserva é obrigatória?** | Sim | Não (só notificação) | Opcional | ❓ |
| **Cobrança de entrada** | Sim (via app) | Não (só reserva) | Depois | ❓ |
| **Gamificação no MVP?** | Sim | Não (Fase 2) | - | ❓ |
| **Instagram embed?** | Crítico | Nice-to-have | Fase 2 | ❓ |
| **Plataforma** | Web first | Mobile first | Ambas | ❓ |

---

## 🎯 FLUXOS AINDA NÃO DETALHADOS

### Fluxo de Reserva (Ponta a Ponta)
```
1. Usuário vê evento na timeline
2. Clica "Reservar"
3. Confirma quantidade de pessoas + telefone
4. Sistema valida (ainda tem espaço?)
5. Reserva é confirmada ou listada como "aguardando"?
6. Usuário recebe confirmação (notificação + email?)
7. Gerente vê a reserva no painel
8. Dia do evento: usuário faz check-in no app ou por QR code?
9. Gerente marca como "compareceu"
10. Unlock: pontos, badge, etc?
```

**O que falta definir:**
- Passo 4: Automático ou manual?
- Passo 6: Apenas notificação ou também email/SMS?
- Passo 8: QR code é obrigatório? Ou confiança?
- Passo 10: Gamificação já ativa?

---

### Fluxo de Notificação Inteligente
```
1. Usuário segue casa A, B, C
2. Casa A publica novo evento (sexta à noite)
3. Sistema identifica: sexta noite, gênero que usuário gosta?
4. Envia notificação: "House A tem nova festa sexta!"
5. Usuário clica notificação
6. Abre página do evento
7. Faz reserva ou só curte?
```

**O que falta definir:**
- Passo 3: Como saber o gênero/preferência do usuário?
  - Primeira vez que abre app, pede pra escolher?
  - Aprende com cliques/reservas?
- Frequência: 1 notificação/dia? 3? Sem limite?
- Hora da notificação: quando enviar? (manhã, tarde, noite?)

---

### 🎧 SOBRE ATRAÇÕES/ARTISTAS PARCEIROS (Ex: Beat Proibido)

#### Fluxo de Divulgação
- [ ] **Como serão exibidos os eventos de artistas como o Beat Proibido?**
  - Aparecerão na timeline geral de eventos como "Beat Proibido no Môi" ou "Beat Proibido no Point"?
  - O perfil do artista terá uma página dedicada listando sua agenda de shows?
  - Haverá link direto para as reservas da casa onde eles vão tocar?

- [ ] **Como diferenciar claramente uma atração de uma casa física?**
  - Badge visual ("Atração", "DJ Duo", etc.) para evitar que o usuário tente reservar o "Beat Proibido" como se fosse uma casa física.
  - Mensagem explicativa no perfil do artista informando que se trata de uma atração/dupla de DJs e direcionando para as casas noturnas onde ocorrerão as apresentações.

- [ ] **Gerenciamento do perfil do artista:**
  - O próprio Luan/Beat Proibido terá um acesso de "Gerente de Artista" para atualizar sua agenda?
  - Ou os eventos de show serão criados e vinculados pelos gerentes das casas onde eles tocarão?

---

## 📝 Checklist Pré-Conversa com Luan

- [ ] Imprimir este documento ou compartilhar digital
- [ ] Trazer o documento `01-base-informacional.md`
- [ ] Pensar em 3 cenários possíveis (otimista, realista, pessimista) de timeline
- [ ] Ter pen e papel para anotar respostas
- [ ] Perguntar pelos problemas atuais (não só apresentar solução)
- [ ] Validar se as 6 casas estão 100% interessadas ou só algumas
- [ ] Deixar claro: MVP é rápido, depois evolui
- [ ] Discutir o fluxo de promoção de artistas/atrações (Beat Proibido) no app e como as agendas serão cadastradas.

---

**Data de criação:** 15/07/2026  
**Última atualização:** Pré-conversa com Luan  
**Status:** Aguardando respostas
