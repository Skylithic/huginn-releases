# Huginn - League of Legends Coach

> **Assistente inteligente para League of Legends focado em privacidade, performance e funcionamento offline.**

O **Huginn** é uma aplicação desktop que auxilia jogadores de League of Legends com overlays, recomendações de picks, e análise de jogo em tempo real. Diferente de outros apps, o Huginn prioriza uma arquitetura "Local-first": seus dados ficam na sua máquina, e o app funciona mesmo sem internet.

---

## 🚀 Funcionalidades (Atual e Planejado)

- **Overlay Leve**: Informações sobre a partida, cooldowns e gold.
- **Draft Assist**: Sugestões de picks e bans baseados no meta e nos seus campeões.
- **Privacidade Total**: Nenhuma credencial do LoL é enviada para a nuvem.
- **Offline Mode**: O core do app funciona sem conexão com nossos servidores.
- **Arquivos de Dados**:
    - `matches.jsonl`: Fonte da verdade das partidas.
    - `drafts.jsonl`: Histórico de drafts e escolhas.
    - `reports.jsonl`: Relatórios prontos para análise por IA.
    - `match_index.json`: Índice para evitar duplicatas.

