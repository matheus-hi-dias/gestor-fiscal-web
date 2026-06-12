# ROADMAP: Frontend SaaS (React)

Este roadmap guia a construção de uma interface de usuário moderna, responsiva e focada na produtividade e na prevenção de erros operacionais dos escritórios de contabilidade.

## Stack Tecnológica Definida

- **Biblioteca Core:** React + Vite
- **Linguagem:** TypeScript
- **Estilização:** Tailwind CSS v4
- **Gerenciamento de Estado:** Zustand ou Context API
- **Formulários e Validação:** React Hook Form + Zod
- **Integração HTTP:** Clientes gerados via OpenSpec + Axios/Fetch

## Fases de Desenvolvimento

### Fase 1: Setup do Projeto e Design System

- [ ] Inicialização do projeto React com TypeScript via Vite.
- [ ] Instalação do Tailwind CSS v4.
- [ ] Configuração de Dark Mode nativo respeitando o SO.
- [ ] Criação de componentes UI genéricos.

### Fase 2: Integração OpenSpec e Autenticação

- [ ] Rotinas para gerar cliente HTTP a partir do OpenSpec.
- [ ] Tela de Login e Recuperação de Senha.
- [ ] Gerenciamento seguro do JWT.
- [ ] Rotas Privadas baseadas em permissão.

### Fase 3: Cadastros Principais e Prevenção de Erros

- [ ] Layout principal responsivo.
- [ ] Dashboard com indicadores.
- [ ] CRUD de **Tipos de Documentos**.
- [ ] **Validação de Conformidade na UI:** Schema Zod para bloquear submissões de tempo < 5 anos e trava de input (`min={5}`).
- [ ] CRUD de **Clientes do Escritório** e **Usuários**.

### Fase 4: Módulo de Documentos Fiscais

- [ ] Interface de **Gestão de Documentos**.
- [ ] Componente de Upload (drag and drop + progress bar).
- [ ] Integração com API S3.
- [ ] Visualizadores de PDF/Imagem embutidos.

### Fase 5: Experiência SaaS e Configurações

- [ ] Tela de **Onboarding**.
- [ ] Painel de **Assinatura e Faturamento**.
- [ ] Telas de exportação de **Relatórios**.
