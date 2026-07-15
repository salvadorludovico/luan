# Base Informacional - Sistema de Reservas para Casas Noturnas

## 📋 Resumo Executivo

Projeto de desenvolvimento de aplicativo mobile/web para gerenciar **programação**, **promoções** e **reservas** de casas noturnas e bares em Goiânia. O app consolida informações dispersas em Instagram e WhatsApp em uma plataforma centralizada.

**Objetivo Principal:** Simplificar a descoberta de eventos e facilitando as reservas para clientes, enquanto oferece dados e controle para os gerentes das casas.

---

## 🎯 Os 3 Pilares do Projeto

### 1. **PROGRAMAÇÃO**
Informações sobre quando a casa funciona e o que acontece lá

- Dia da semana
- Horário de funcionamento (abertura e fechamento)
- Nome do Evento/Nome da Noite
- DJs/Artistas que estarão tocando
- Estilo de música/tipo de festa (Funk, Pagode, Latin, etc.)

**Exemplo:**
```
QUARTA - DáoPlay! (Môi)
18h a 1h | Você no comando do som
DJs: [lista de DJs]
```

### 2. **PROMOÇÕES**
Descontos, combos e ofertas especiais

- Itens em promoção (comidas e bebidas)
- Tipo: percentual OFF, valor fixo, combos, dobradinhas
- Horário de validade da promoção
- Entrada FREE ou paga (e por quanto tempo)

**Exemplo:**
```
QUARTA - Môi
Dobradinha Caipirinha R$30
Sandubas 20%OFF
Válido até 21h
~ ENTRADA FREE (sujeito a alteração)
```

### 3. **RESERVAS**
Sistema de confirmação de presença nas casas

- Usuário faz reserva antecipadamente
- Casa confirma disponibilidade
- Notificações sobre reserva (confirmação, lembretes, cancelamento)
- Possível integração com pagamento?

---

## 🏢 Casas Mapeadas

| Casa | Instagram | Setor/Bairro | Especialidade |
|------|-----------|--------------|----------------|
| **Môi** | @moigoiania | Setor Bueno | Funk, Eletrônico, Copa do Mundo |
| **Point** | @pointgoiania | (Não informado) | Funk, Baile, Eventos especiais |
| **Mosaic** | @mosaic.goiania | (Não informado) | Pop, Eletropop, Hyperpop |
| **Vernissage Club** | @vernissageclub | (Não informado) | Funk, Latin, Eletrônico, Temático |
| **Fluxo** | @ofluxodegoiania | Setor Sul | Funk, Pop, Rap, Trap |
| **Cajuína** | @cajuina.goiania | Setor Sul | Pagode, Forró, Sertanejo |

---

## 🎧 Atrações e Artistas Parceiros

Além de casas noturnas e bares físicos, o sistema também divulgará a agenda de atrações e artistas parceiros de relevância. 

**Nota importante:** Não se comportam como uma casa noturna física (não possuem reservas diretas no local/estabelecimento próprio), mas terão suas apresentações e eventos individuais divulgados na plataforma para direcionar o público aos locais onde estarão tocando.

| Atração / Artista | Instagram | Tipo / Gênero | Observações |
|---|---|---|---|
| **Beat Proibido** | [@beatproibido](https://www.instagram.com/beatproibido/) | Funk & Bruxaria (Duo de DJs do Luan) | *Não é uma casa física.* Divulgação das datas e locais dos shows/eventos onde se apresentam. |

---

## 📱 Exemplos de Conteúdo Real

### Programação Típica (Môi)

```
QUINTA: 19h às 2h
Girls&Wine
- Vinho: 2 taças por R$30 | válido até 22h para mulheres
~ ENTRADA FREE (sujeito a alteração)

SEXTA: 19h às 3h
- Chá de Rolezeiro - 2 por R$40 | válido ate 21h
~ ENTRADA FREE até 20h | Após R$10 (sujeito a alteração)

SÁBADO: 19h às 3h
- Dobradinha SHOT - Pede um e ganha outro | válido ate 21h
~ ENTRADA FREE até 20h | Após R$10 (sujeito a alteração)

DOMINGO: 14h às 23h
TRANSMISSÃO AO VIVO FINAL COPA DO MUNDO
- Dobradinha Fitzgerald até início do jogo
- Baldinho de Longneck até o final do jogo
- Double Shot Ballena até o final da noite
~ENTRADA FREE até 17h
```

### Tipos de Eventos Comuns

- **Transmissão ao Vivo** (Copa, Jogos, Finals)
- **Temáticos** (Girls&Wine, Latin Night, Baile Funk)
- **Apresentações Ao Vivo** (Bandas, DJs conhecidos)
- **Festividades** (Arraiá, Baile Junino)

---

## 🔧 Funcionalidades Já Pensadas

### Para Usuários Finais
- **Descoberta de eventos** - Browse programação das casas
- **Notificações inteligentes** - Receber alertas sobre eventos de interesse
- **Reservas** - Confirmar presença em eventos
- **Gamificação** - Passport/passaporte das casas (visitou todas?)
- **Check-in** - Confirmar presença no local (integrado com reserva)
- **Favoritos** - Seguir casas e receber notificações

### Para Gerentes/Marketing
- **Painel de controle** - Atualizar programação e promoções
- **Gerenciar reservas** - Ver quem confirmou, capacidade da casa
- **IA para criar posts** - Montar textos com templates/modelos
- **Embed Instagram** - Posts do Instagram aparecem no app
- **Audit log** - Monitorar ações na plataforma
- **Analytics básico** - Quantas pessoas viram o evento, confirmaram, foram

### Ideias Futuras
- **Anúncios de virada de lote** - Notificar quando ingresso fica mais caro (Vernissage)
- **Desconto dinâmico** - Promoções baseadas em demanda
- **Integração de pagamento** - Pagar a entrada via app
- **Reputação/Reviews** - Usuários avaliarem experiência
- **Recomendações** - "Se você gostou disso, talvez curta..."

---

## 📊 Estrutura Base do Projeto

### MVP (Fase 1) - Foco: Viabilidade + 1 Casa Piloto
**Tempo estimado: 4-6 semanas**

Core features:
- Browse programação das casas (pelo menos 1-2)
- Ver promoções por dia/hora
- Fazer reserva simples (sem pagamento)
- Notificações push básicas
- Painel gerente simples (CRUD de programação/promoções)

Stack sugerida:
- **Frontend:** React/Vue (web) + React Native (mobile futura)
- **Backend:** Node.js/Express ou Python/FastAPI
- **DB:** PostgreSQL ou Firebase
- **Notificações:** Firebase Cloud Messaging

### Fase 2 - Expansão
- Mais casas
- Gamificação (check-in, passport, pontos)
- Integração Instagram (embed de posts)
- Painel gerente completo
- Analytics básico

### Fase 3 - Monetização
- Integração de pagamento (entrada + bebidas)
- Anúncios de virada de lote
- Descontos dinâmicos
- Dados para as casas (insights de ocupação, demanda)

---

## 💰 Modelo de Negócio (Não Definido)

**Ainda a definir com Luan:**
- Será por comissão por reserva?
- Fee por casa por mês?
- Porcentagem dos ingressos vendidos?
- Modelo freemium (básico grátis, premium pago)?
- Anúncios dentro do app?

---

## 🎨 Estrutura de Dados (Prévia)

### Casa
```
{
  id: UUID
  nome: string
  instagram: string
  endereco: string
  setor: string
  descricao: string
  imagemCapaUrl: string
  horarioFuncionamento: {
    segunda: [aberto, fechado],
    ...
  }
}
```

### Evento/Programação
```
{
  id: UUID
  casaId: UUID
  diaSemana: enum (segunda-domingo)
  dataEspecifica: date (opcional)
  horarioInicio: time
  horarioFim: time
  nome: string (ex: "DáoPlay!")
  descricao: string
  djs: string[]
  generoMusical: string[]
}
```

### Promoção
```
{
  id: UUID
  eventoId: UUID
  nome: string (ex: "Dobradinha Caipirinha")
  descricao: string
  preco: number
  desconto: number (opcional)
  tipoDesconto: enum ("fixo", "percentual", "combo")
  horarioInicio: time
  horarioFim: time
}
```

### Reserva
```
{
  id: UUID
  usuarioId: UUID
  eventoId: UUID
  dataCriacao: datetime
  status: enum ("confirmada", "cancelada", "compareceu", "não compareceu")
  quantidadePessoas: number
  telefone: string (para contato)
}
```

---

## 📍 Próximos Passos

1. **Conversa com Luan** - Validar visão, responder perguntas pendentes
2. **Definir MVP exato** - Qual casa começa? Quais features são críticas?
3. **Decisões técnicas** - Stack, hospedagem, timeline
4. **Prototipagem** - HTML/Figma para validar UX
5. **Desenvolvimento** - Começar com backend + frontend simples

---

**Data de criação:** 15/07/2026  
**Status:** Preliminar - Aguardando validação com Luan
