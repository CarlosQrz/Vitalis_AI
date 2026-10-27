# 🩺 VitalisAI

<div align="center">
  <p><b>Gestão Inteligente de Exames Laboratoriais e Monitoramento Preventivo de Saúde</b></p>
  <p>Plataforma web full-stack desenvolvida para simplificar a interpretação de laudos médicos, centralizar o histórico de saúde familiar e automatizar análises preventivas através de inteligência artificial.</p>
</div>

---

## 📌 1. Descrição do Projeto
O **VitalisAI** é uma aplicação web moderna voltada para o acompanhamento preventivo de saúde e exames laboratoriais. O sistema permite o upload de exames em formato PDF com extração automatizada de dados (OCR), categorização inteligente por marcadores clínicos, alertas visuais por semáforo de risco e visualização longitudinal da evolução de saúde ao longo do tempo.

## 🎯 2. Problema Abordado
* **Desorganização de Laudos:** Pacientes costumam acumular pastas físicas de papel com exames impressos de diferentes laboratórios, dificultando o acompanhamento médico[cite: 2].
* **Complexidade Técnica:** Nomes técnicos e valores de referência confusos geram ansiedade e dificultam a compreensão rápida pelo paciente[cite: 2].
* **Falta de Histórico Unificado:** Dificuldade em cruzar dados de múltiplos familiares (como pais idosos ou dependentes) em uma única plataforma centralizada e segura[cite: 2, 3].

## 🚀 3. Objetivos
* **Automação de Leitura:** Extrair e estruturar dados de exames laboratoriais em PDF sem digitação manual[cite: 3].
* **Interface Intuitiva ("Glanceable UI"):** Apresentar o estado de saúde através de indicadores visuais claros (Verde, Amarelo e Vermelho)[cite: 3].
* **Gestão Multiusuário/Multiperfil:** Permitir que o usuário gerencie exames próprios e de dependentes de forma segregada e segura[cite: 3].
* **Histórico Longitunidal:** Fornecer gráficos de evolução temporal para facilitar consultas médicas preditivas[cite: 2, 3].

## 🛠️ 4. Principais Tecnologias Previstas
* **Frontend:** React, TypeScript, Vite, Tailwind CSS, shadcn/ui, Radix UI.
* **Backend & Banco de Dados:** Supabase (PostgreSQL, Supabase Auth, Storage).
* **Processamento Serverless:** Supabase Edge Functions (Deno/TypeScript) para extração OCR e avaliação de riscos.
* **Controle de Versão & Ferramentas:** Git, GitHub, Node.js / Bun.

## 📁 5. Organização do Repositório
A estrutura de diretórios do projeto foi organizada para garantir alta modularidade, separação de responsabilidades e escalabilidade:

```text
VitalisAI/
├── public/                 # Arquivos estáticos globais (favicon, robôs, assets)
├── reference/              # Documentações de referência, protótipos HTML estáticos e assets visuais
├── src/                    # Código-fonte principal da aplicação React
│   ├── components/         # Componentes reutilizáveis de UI e modais específicos
│   │   ├── onboarding/     # Componentes do fluxo inicial e questionários de saúde
│   │   └── ui/             # Biblioteca de componentes atômicos (shadcn/ui)
│   ├── constants/          # Constantes globais (mapeamentos de alergias, subs, etc.)
│   ├── contexts/           # Contextos React (ex: ThemeContext para modo claro/escuro)
│   ├── data/               # Bases de dados locais e mapeadores de marcadores
│   ├── hooks/              # Custom Hooks para lógica de negócio e integração (Auth, Exames, Perfil)
│   ├── i18n/               # Configuração de internacionalização e arquivos de tradução (pt-br, en, es)
│   ├── integrations/       # Clientes de serviços externos (Configuração do Supabase)
│   ├── lib/                # Utilitários de lógica pesada (OCR, conversores PDF, cálculo de eficácia)
│   ├── pages/              # Páginas principais de rotas (Dashboard, Exames, Análises, Nutrição, Perfil)
│   ├── types/              # Tipagens e interfaces TypeScript (banco de dados e estados)
│   ├── utils/              # Funções auxiliares gerais (tratamento de erros de autenticação)
│   ├── App.tsx             # Componente raiz com roteamento e provedores
│   ├── index.css           # Estilos globais e configurações do Tailwind
│   └── main.tsx            # Ponto de entrada da aplicação
├── supabase/               # Configurações e backend serverless do Supabase
│   ├── functions/          # Edge Functions Deno/TS (process-exam, evaluate-health-risk, send-reminders)
│   └── migrations/         # Scripts SQL de controle de versão do esquema PostgreSQL
├── tailwind.config.ts      # Configurações de estilização do Tailwind CSS
├── tsconfig.json           # Configurações globais do TypeScript
└── vite.config.ts          # Configurações do bundler Vite
