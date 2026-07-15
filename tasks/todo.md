# Plano de Desenvolvimento: Protótipo Visual Mobile-First (Sistema de Reservas)

## 🎯 Objetivos
Criar uma proposta sólida de protótipo visual interativo em HTML/CSS/JS para simular um aplicativo mobile-first voltado para descoberta de eventos, consulta de promoções e reservas de casas noturnas em Goiânia. O protótipo será ideal para demonstração em conversas iniciais com parceiros e clientes (como o Luan e donos de casas).

## 📋 Lista de Tarefas (Todos)

- [x] **Fase de Planejamento e Design**: Criar proposta estruturada para apresentação e alinhar os pilares do app.
- [x] **Estrutura Base do App**: Criar `index.html` com layout mobile-first premium, simulação de frame de celular para desktop, e design responsivo.
- [x] **Listagem de Casas**: Implementar aba de descoberta de casas (Môi, Cajuína, Mosaic, etc.) com busca e filtros por Setor/Gênero.
- [x] **Programação & Promoções**: Exibir detalhes reais das casas e eventos conforme mapeado em `01-base-informacional.md` (Girls&Wine, DáoPlay, etc.).
- [x] **Fluxo de Reserva Interativo**: Permitir simulação completa de reserva (nome, telefone, quantidade de pessoas) com feedback visual de sucesso.
- [x] **Área 'Minhas Reservas'**: Listagem das reservas realizadas com QR Code simulado e status de presença.
- [x] **Aba 'Vibes' (Feed de Vídeos Verticais)**: Criar o feed imersivo de vídeos verticais estilo TikTok/Reels com rolagem fluida (`snap-y`), autoplay com `IntersectionObserver` de alta performance, mutar/desmutar sincronizado, progress bar de reprodução e integração nativa com o modal de reserva.
- [x] **Polimento Visual & UX**: Efeitos de neon, transições suaves de abas, ícones elegantes (Lucide Icons) e visual premium em Dark Mode (perfeito para o nicho de baladas).
- [x] **Validação & Entrega**: Revisar todos os fluxos e documentar resultados em `tasks/todo.md`.

## 🏗️ Decisões de Design (UX/UI)
- **Visual Nightlife Premium**: Cores escuras dominantes (background quase preto, cinzas profundos) combinados com acentos neon vibrantes (roxo, rosa, ciano).
- **Abas Inferiores (Bottom Nav)**: Navegação típica de app mobile (Descobrir, Vibes, Benefícios, Listas).
- **Responsividade Dupla**: No desktop, exibe um frame simulando um iPhone moderno centralizado na tela. No celular, expande para ocupar 100% da tela como um Web App nativo.
- **Interatividade Real**: Sem backend, mas usa estado no JavaScript (e persistência local opcional via localStorage) para salvar reservas adicionadas.
- **Experiência Vibes Imersiva**: Oculta o cabeçalho padrão para imersão total de ponta a ponta na aba Vibes, deixando apenas a barra de navegação visível sob efeitos dinâmicos de desfoque.

## 📄 Revisão de Resultados
- **Aba Vibes**: Implementada e 100% otimizada para dispositivos móveis com controle inteligente de áudio e renderização suave. Os vídeos curtos representam fidedignamente o estilo visual e lineup das principais festas e bares de Goiânia (Subcult, Beat Proibido, Môi e Fluxo).
- **Consistência de Dados**: O botão "Garantir Lista" na aba Vibes invoca a função nativa `openReservationModal(eventId, houseId)` passando as chaves correspondentes. Isso possibilita que os usuários se registrem diretamente a partir do feed de vídeos curtos.
- **Portabilidade**: Desenvolvido integralmente em vanilla HTML/CSS/JS com dependências de CDN de carregamento ultra-rápido (Tailwind, Lucide).

*Última atualização: Julho de 2026.*
