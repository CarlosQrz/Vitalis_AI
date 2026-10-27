# 🩺 VitalisAI — Gestão Inteligente de Exames e Saúde Preventiva

![Status do Projeto](https://img.shields.io/badge/Status-Em%20Desenvolvimento-0284c7)
![React](https://img.shields.io/badge/Frontend-React%2018%20%2B%20TypeScript-61dafb)
![Supabase](https://img.shields.io/badge/Backend-Supabase%20%28PostgreSQL%29-3ecf8e)
![TailwindCSS](https://img.shields.io/badge/UI-Tailwind%20CSS%20%2B%20shadcn%2Fui-38bdf8)

---

## 📌 1. Descrição do Projeto

O **VitalisAI** é uma aplicação web moderna e responsiva (*Mobile-First*) desenvolvida para simplificar a gestão de exames laboratoriais, o acompanhamento de protocolos de suplementação/medicação e a saúde preventiva familiar.

Através de processamento automatizado de documentos em PDF (OCR) e regras de validação biomédica, o sistema elimina a necessidade de digitar resultados manualmente ou decifrar jargões técnicos, apresentando o estado de saúde do usuário por meio de um painel visual claro, alertas semafóricos por cores e gráficos longitudinais de evolução.

---

## ⚠️ 2. Problema Abordado

Durante o acompanhamento médico de rotina ou tratamento de condições crônicas, pacientes e familiares enfrentam quatro grandes gargalos:

1. **Desorganização e perda de histórico:** Acúmulo de pastas físicas de papel ou arquivos PDF espalhados em diferentes dispositivos e portais de laboratórios.
2. **Complexidade dos termos técnicos:** Dificuldade de compreender o que significa cada biomarcador alterado (ex: LDL, Hemoglobina Glicada, Ferritina) sem recorrer a buscas confusas na internet.
3. **Dificuldade de comparação temporal:** Trabalho manual para cruzar resultados de exames antigos com exames novos e avaliar se uma dieta ou protocolo está funcionando ao longo dos meses.
4. **Gestão familiar fragmentada:** Cuidadores familiares (como filhos que administram a saúde de pais idosos) não possuem uma ferramenta simples para separar seus próprios exames dos exames de seus dependentes.

---

## 🎯 3. Objetivos do Projeto

### Objetivo Geral
Projetar e implementar uma plataforma centralizada, intuitiva e segura que automatize a extração de dados de exames laboratoriais em PDF e traduza resultados clínicos em indicadores visuais de fácil compreensão para pacientes e médicos.

### Objetivos Específicos
* **Extração Automatizada e Revisão (OCR):** Permitir o upload de exames em PDF com leitura automática dos marcadores e possibilidade de edição manual rápida pelo usuário.
* **Sistema Semáforo de Alertas:** Aplicar formatação condicional automática nos resultados (**Verde** = Ideal, **Amarelo** = Atenção, **Vermelho** = Crítico) com base nos valores de referência.
* **Visualização Longitudinal:** Gerar gráficos interativos que demonstrem a evolução dos marcadores nos últimos 12 meses ou mais.
* **Educação em Saúde:** Disponibilizar explicações curtas e em linguagem simples sobre o papel de cada marcador no organismo.
* **Gestão de Múltiplos Perfis:** Permitir a criação e o gerenciamento de perfis dependentes dentro de uma mesma conta raiz, mantendo total isolamento de dados.
* **Filtros Inteligentes e Exportação:** Viabilizar a busca de exames por data, laboratório ou categoria clínica (Perfil Lipídico, Hormonal, Vitaminas) e exportar um resumo visual em PDF para envio rápido ao médico.
* **Protocolos e Nutrição:** Monitorar suplementos/medicamentos ativos, calcular eficácia com base nos exames e fornecer insights nutricionais preventivos.

---

## 👨‍💻 4. Integrantes da Equipe

* **Carlos Henrique Queiroz Ramos Teixeira**
  * **Papel:** Desenvolvedor Full-Stack, Engenharia de Requisitos, Arquitetura de Banco de Dados e UI/UX Design.
  * **Curso:** Bacharelado em Sistemas de Informação (6º Período) — **Faculdade COTEMIG** (Belo Horizonte, MG).
  * **Links:** [Portfólio](https://qerozdev.netlify.app) | [GitHub](https://github.com/CarlosQrz) | [LinkedIn](https://acesse.one/perfil-linkedin-Carlos-Queiroz)

---

## 🚀 5. Principais Tecnologias Previstas para a Implementação

| Camada | Tecnologias Utilizadas | Justificativa Principal |
| :--- | :--- | :--- |
| **Frontend Core** | **React 18 + TypeScript + Vite** | Componentização modular, tipagem estática de ponta a ponta sincronizada com o banco de dados e alta velocidade de build. |
| **Estilização & UI** | **Tailwind CSS + shadcn/ui (Radix UI)** | Construção ágil de interfaces responsivas (*Mobile-First*), suporte a tema Claro/Escuro e componentes acessíveis (WAI-ARIA). |
| **Visualização de Dados** | **Plotly / Recharts (`LazyPlot`)** | Renderização sob demanda de gráficos temporais interativos para acompanhamento da evolução clínica. |
| **Backend & Banco de Dados** | **Supabase (PostgreSQL + Auth + Storage)** | Persistência relacional robusta, autenticação JWT segura, armazenamento de PDFs e isolamento de dados via *Row-Level Security (RLS)*. |
| **Serverless & Regras** | **Supabase Edge Functions (Deno)** | Execução segura em nuvem das funções de leitura de exames (`process-exam`), avaliação de risco (`evaluate-health-risk` e `analyze-substance-risk`), lembretes (`send-reminders`) e LGPD (`delete-user-account`). |
| **Internacionalização** | **i18next (`pt-br`, `en`, `es`)** | Arquitetura multi-idioma nativa para escalabilidade da aplicação. |

---

## 📂 6. Estrutura do Repositório

```text
vitalisai/
├── public/                   # Manifesto PWA, ícones e arquivos estáticos
├── src/
│   ├── components/           # Componentes visuais, modais de exames/protocolos e UI
│   ├── constants/            # Constantes clínicas (alergias, categorias)
│   ├── contexts/             # Contexto global de tema (Claro/Escuro)
│   ├── data/                 # Mapeamento de biomarcadores e substâncias
│   ├── hooks/                # Custom Hooks de domínio (useExams, useProtocols, useProfile)
│   ├── i18n/                 # Dicionários de tradução (PT-BR, EN, ES)
│   ├── integrations/supabase/# Configuração do cliente Supabase e tipos gerados
│   ├── lib/                  # Processador OCR, conversor de PDF e calculadora de eficácia
│   ├── pages/                # Páginas da aplicação (Dashboard, Exames, Analises, Nutricao, Perfil)
│   └── types/                # Interfaces TypeScript do sistema
├── supabase/
│   ├── functions/            # Microsserviços Serverless (Edge Functions)
│   └── migrations/           # Histórico de criação e evolução das tabelas SQL
└── README.md                 # Documentação principal do projeto
```

---

## ⚙️ 7. Como Executar o Projeto Localmente

```bash
# 1. Clone este repositório
git clone https://github.com/CarlosQrz/vitalisai.git

# 2. Acesse a pasta do projeto
cd vitalisai

# 3. Instale as dependências
npm install

# 4. Configure as variáveis de ambiente (.env) com suas credenciais do Supabase
# VITE_SUPABASE_URL=sua_url_do_supabase
# VITE_SUPABASE_PUBLISHABLE_KEY=sua_chave_anon_do_supabase

# 5. Inicie o servidor de desenvolvimento
npm run dev
```
