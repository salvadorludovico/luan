# Plano de Desenvolvimento: Protótipo Visual Mobile-First (Sistema de Reservas)

## 🎯 Objetivos
Criar uma proposta sólida de protótipo visual interativo em HTML/CSS/JS para simular um aplicativo mobile-first voltado para descoberta de eventos, consulta de promoções e reservas de casas noturnas em Goiânia. O protótipo será ideal para demonstração em conversas iniciais com parceiros e clientes (como o Luan e donos de casas).

## 📋 Lista de Tarefas (Todos)

- [ ] **Fase de Planejamento e Design**: Criar proposta estruturada para apresentação e alinhar os pilares do app.
- [ ] **Estrutura Base do App**: Criar `index.html` com layout mobile-first premium, simulação de frame de celular para desktop, e design responsivo.
- [ ] **Listagem de Casas**: Implementar aba de descoberta de casas (Môi, Cajuína, Mosaic, etc.) com busca e filtros por Setor/Gênero.
- [ ] **Programação & Promoções**: Exibir detalhes reais das casas e eventos conforme mapeado em `01-base-informacional.md` (Girls&Wine, DáoPlay, etc.).
- [ ] **Fluxo de Reserva Interativo**: Permitir simulação completa de reserva (nome, telefone, quantidade de pessoas) com feedback visual de sucesso.
- [ ] **Área 'Minhas Reservas'**: Listagem das reservas realizadas com QR Code simulado e status de presença.
- [ ] **Polimento Visual & UX**: Efeitos de neon, transições suaves de abas, ícones elegantes (Lucide Icons) e visual premium em Dark Mode (perfeito para o nicho de baladas).
- [ ] **Validação & Entrega**: Revisar todos os fluxos e documentar resultados em `tasks/todo.md`.

## 🏗️ Decisões de Design (UX/UI)
- **Visual Nightlife Premium**: Cores escuras dominantes (background quase preto, cinzas profundos) combinados com acentos neon vibrantes (roxo, rosa, ciano).
- **Abas Inferiores (Bottom Nav)**: Navegação típica de app mobile (Descobrir, Reservas, Perfil).
- **Responsividade Dupla**: No desktop, exibe um frame simulando um iPhone moderno centralizado na tela. No celular, expande para ocupar 100% da tela como um Web App nativo.
- **Interatividade Real**: Sem backend, mas usa estado no JavaScript (e persistência local opcional via localStorage) para salvar reservas adicionadas.

## 📄 Revisão de Resultados
*A ser documentado ao finalizar o projeto.*
