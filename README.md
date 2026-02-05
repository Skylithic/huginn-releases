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

---

## 🛠️ Instalação e Execução (Desenvolvimento)

### Pré-requisitos
- **Rust** (versão estável recente)
- **Node.js** (v18+) & **pnpm** (ou npm)
- **Python 3.10+** (para o backend)
- **VS Code**: Recomendado com extensões Tauri e rust-analyzer.

### Rodando o Projeto

O projeto é dividido em `desktop` (Tauri + React + TS) e `backend` (Python).

1.  **Backend Setup**:
    ```bash
    cd apps/backend
    pip install -e .
    # Opcional: Para gerar executável
    # py -m PyInstaller lol-coach-backend.spec
    ```

    Para rodar apenas o backend (CLI):
    ```bash
    py -m lol_coach.cmd.coach_cli.main
    ```

2.  **Frontend Setup**:
    ```bash
    cd apps/desktop
    npm install
    ```

3.  **Rodar o App Completo (Dev Mode)**:
    ```bash
    cd apps/desktop
    npm run tauri dev
    ```
    Isso iniciará o frontend e, dependendo da configuração, o supervisor do Rust tentará iniciar o backend Python.

---

## 📂 Estrutura do Projeto

- `apps/desktop`: Frontend (React) e Core (Rust/Tauri). Responsável pela UI e comunicação com o sistema.
    - `src/features`: Lógica específica de cada funcionalidade.
    - `src/shared`: Componentes e serviços reutilizáveis.
    - `src/infra`: Implementações de baixo nível (Tauri API, WS).
- `apps/backend`: Agente LCU (Python). Conecta-se ao cliente do LoL e processa dados.
- `contracts`: Definições de esquema (JSON Schema) para comunicação entre processos.
- `docs`: Documentação centralizada (Arquitetura, Roadmap).

---

## 🤝 Contribuição e Padrões

### Gitflow & Conventional Commits
Este projeto segue **Gitflow** e **Conventional Commits**.
- **Commits em Inglês**: `type(scope): description`
  - Ex: `feat(backend): implement event envelope`
  - Ex: `fix(frontend): update ws provider types`
  - Ex: `docs: add architecture overview`
- **Branches**:
  - `feat/nome-da-feature`
  - `fix/nome-do-bug`
  - `release/vX.Y.Z`

Consulte `docs/ROADMAP.md` para ver o plano de evolução e `docs/ARCHITECTURE.md` para entender as decisões técnicas.
