# 🎯 Assistente de Planejamento com IA

> **Projeto Final — Trilha "IA para Criadores de Conteúdo"**  
> _Cenário fictício de demonstração · Dados não reais_

Um assistente que transforma **qualquer objetivo em um plano executável** e acompanha o progresso com você. Combina um **Planner no Notion** com **habilidades reutilizáveis** que ensinam a IA cada etapa do método de planejamento.

---

## 📋 Índice

- [Problema e Diferencial](#-problema-e-diferencial)
- [Recursos Utilizados](#-recursos-utilizados)
- [Estrutura do Planner](#-estrutura-do-planner)
- [Habilidades do Assistente](#-habilidades-do-assistente)
- [Demonstração Prática](#-demonstração-prática)
- [Como Usar](#-como-usar)
- [Evoluções Futuras](#-evoluções-futuras)
- [Autora](#-autora)

---

## 🧠 Problema e Diferencial

### Problema

A maioria das pessoas tem objetivos, mas poucas conseguem transformá-los em planos acionáveis. O motivo não é falta de vontade — é falta de **método**. Sem um processo estruturado, o objetivo vira uma lista mental vaga que nunca sai do papel.

### Diferencial

Este assistente não é um template de planner genérico. Ele é um **sistema de duas camadas**:

1. **Planner no Notion** — o registro visual do plano, com as 4 áreas essenciais: plano de ação, rotina, obstáculos e acompanhamento
2. **Habilidades reutilizáveis** — instruções que a IA segue em cada etapa, eliminando a necessidade de repetir prompts a cada conversa

O método funciona para **qualquer objetivo** — estudo, carreira ou negócio. Uma vez configurado, o próximo objetivo já começa com o planejamento pronto.

---

## 🛠 Recursos Utilizados

| Recurso | Função | Por que escolhi |
|---------|--------|-----------------|
| **Notion** | Planner visual com banco de dados | Gratuito, permite criar páginas com markdown, tabelas e callouts. A IA do Notion pode ler as habilidades diretamente. |
| **Notion API** | Criação programática do Planner e habilidades | Automatiza a configuração inicial — o assistente se instala sozinho. |
| **ChatGPT / Claude / DeepSeek** | Execução das habilidades | Qualquer LLM consegue seguir as instruções das habilidades. O método é agnóstico de ferramenta. |
| **GitHub** | Publicação da documentação | README.md público, acessível sem login, ideal para portfólio. |

### Instruções aplicadas

1. **Prompt único por habilidade** — cada habilidade tem um prompt template que a IA segue do início ao fim. Não são mensagens curtas, são comandos completos.
2. **Contexto acumulado** — as habilidades são executadas em ordem. Cada uma constrói sobre o resultado da anterior (objetivo → plano → rotina → obstáculos → revisão).
3. **Exemplos embutidos** — cada habilidade mostra um exemplo com o objetivo fictício, para a IA entender o formato esperado da resposta.

---

## 🗂 Estrutura do Planner

O Planner é uma página no Notion com **um banco de dados** que registra o objetivo e seu progresso. Cada objetivo vira uma linha na tabela.

### Propriedades do banco

| Propriedade | Tipo | Descrição |
|-------------|------|-----------|
| **Nome do Objetivo** | Título | O objetivo registrado (ex.: "Curso IA na Prática (90 dias)") |
| **Plano de Ação** | Texto | Etapas, prazos e entregáveis de cada fase |
| **Rotina** | Texto | Distribuição das tarefas nos dias e horários disponíveis |
| **Obstáculos** | Texto | Riscos mapeados e planos B para cada um |
| **Acompanhamento** | Texto | Revisões semanais: o que foi feito, o que travou, ajustes |

### Relações

O Planner se conecta a dois níveis de organização:

- **Página raiz** — contém a tabela do Planner + índice das habilidades
- **Child pages** — cada habilidade é uma página filha, com instruções completas e exemplos

```
Planner IA — Assistente de Planejamento
├── 🎯 Habilidade 1 — Esclarecer e Registrar o Objetivo
├── 📋 Habilidade 2 — Transformar Objetivo em Plano de Ação
├── ⏰ Habilidade 3 — Adaptar o Plano à Rotina
├── ⚠️ Habilidade 4 — Antecipar Obstáculos e Definir Alternativas
├── 📊 Habilidade 5 — Revisar o Progresso
└── 🔗 Habilidade 6 — Analisar Riscos e Dependências (Extra)
```

### 📸 Planner no Notion

![Planner IA - Visão geral](https://everferreira.github.io/assistente-planejamento-ia/planner-overview.png)

_Link público do Planner:_ [Planner IA — Assistente de Planejamento](https://www.notion.so/Planner-IA-Assistente-de-Planejamento-4236bd5dbb7881adbfc3d01de6a21488)

---

## 🎯 Habilidades do Assistente

### Habilidade 1 — Esclarecer e Registrar o Objetivo

**Quando usar:** No início de qualquer projeto, quando o objetivo ainda é vago.

**O que faz:** Transforma um desejo vago em um objetivo claro, mensurável e com prazo. A IA pergunta: o quê, por quê, prazo, critério de sucesso e escopo.

**Prompt resumido:**
```
Quero definir um objetivo de [categoria]. Meu desejo inicial é: [descrição].
Ajude-me a esclarecer: versão específica? motivação? prazo? critério de sucesso? escopo?
```

**Exemplo de saída:**
> "Até 25/02/2027 (90 dias), quero criar e lançar o curso online 'IA na Prática' com 8 módulos e 24 aulas, vendendo pelo menos 10 inscrições no primeiro mês, porque profissionais não-tech estão perdendo oportunidades por não saber usar IA. Sucesso = curso no ar com checkout funcionando e 10+ alunos pagantes."

📎 [Página completa no Notion](https://www.notion.so/Habilidade-1-Esclarecer-e-Registrar-o-Objetivo-4236bd5dbb7881c0a84efd3ed0558ede)

---

### Habilidade 2 — Transformar Objetivo em Plano de Ação

**Quando usar:** Logo após definir o objetivo (Habilidade 1).

**O que faz:** Decompõe o objetivo em etapas sequenciais, marcos e entregáveis concretos. Inclui dependências entre etapas.

**Exemplo de saída (tabela):**

| Etapa | Prazo | Entregáveis |
|-------|-------|-------------|
| Pesquisa e Definição | Semana 1-2 | ICP, concorrência, proposta de valor |
| Estrutura do Curso | Semana 3-4 | 8 módulos, 24 aulas esboçadas |
| Produção de Conteúdo | Semana 5-6 | Slides, roteiros, exercícios |
| Gravação e Edição | Semana 7-8 | 24 aulas gravadas e editadas |
| Plataforma e Checkout | Semana 9-10 | Página de vendas, checkout |
| Pré-lançamento | Semana 11-12 | Grupo beta, feedback |
| Lançamento | Semana 13 | Campanha, 10+ inscrições |

📎 [Página completa no Notion](https://www.notion.so/Habilidade-2-Transformar-Objetivo-em-Plano-de-A-o-4236bd5dbb7881b1b659f34ea4d855eb)

---

### Habilidade 3 — Adaptar o Plano à Rotina

**Quando usar:** Depois de ter o plano de ação (Habilidade 2).

**O que faz:** Ajusta o plano à realidade de tempo, energia e compromissos existentes. Distribui tarefas nos blocos de tempo disponíveis.

**Exemplo de saída:**
| Dia | Horário | Atividade | Duração |
|-----|---------|-----------|---------|
| Seg | 19h-21h | Produção de conteúdo | 2h |
| Ter | 19h-21h | Gravação de aulas | 2h |
| Qua | 19h-21h | Edição e pós-produção | 2h |
| Qui | 19h-21h | Plataforma e estrutura | 2h |
| Sex | 19h-21h | Pesquisa e planejamento | 2h |
| Sáb | 14h-18h | Revisão e ajustes | 4h |

📎 [Página completa no Notion](https://www.notion.so/Habilidade-3-Adaptar-o-Plano-Rotina-4236bd5dbb78815d90c9dd478a0ef629)

---

### Habilidade 4 — Antecipar Obstáculos e Definir Alternativas

**Quando usar:** Depois de adaptar o plano à rotina (Habilidade 3).

**O que faz:** Mapeia os principais riscos e cria planos B acionáveis com gatilhos objetivos ("se X, então Y").

**Exemplo de saída:**

| Obstáculo | Prob. | Plano B |
|-----------|-------|---------|
| Falta de tempo consistente | Alta | Reduzir para 1h/dia; compensar sábado |
| Perfeccionismo no conteúdo | Alta | Regra dos 80%: publica e ajusta depois |
| Curva de aprendizado de edição | Média | Template pronto; pedir ajuda se travar |
| Medo de lançar | Média | Grupo beta gratuito primeiro |
| Doença ou imprevisto | Baixa | Pausa de 1 semana (folga no cronograma) |

📎 [Página completa no Notion](https://www.notion.so/Habilidade-4-Antecipar-Obst-culos-e-Definir-Alternativas-4236bd5dbb7881d29812d5bd466bfa10)

---

### Habilidade 5 — Revisar o Progresso

**Quando usar:** Semanalmente (domingo ou no dia combinado).

**O que faz:** Avalia o que foi feito vs. o planejado, identifica o que travou e ajusta o plano da semana seguinte.

**Exemplo de saída:**
| Aspecto | Resposta |
|---------|----------|
| Funcionou | Bloco de 2h à noite funcionou bem |
| Travou | Roteiro Módulo 3 — conteúdo denso demais |
| Ajuste | Dividir Módulo 3 em 2 submódulos |
| Top 3 semana 4 | Finalizar roteiro M3, iniciar slides M4, pesquisar plataforma |

📎 [Página completa no Notion](https://www.notion.so/Habilidade-5-Revisar-o-Progresso-4236bd5dbb7881269db1c7964cc678c8)

---

### Habilidade 6 — Analisar Riscos e Dependências (Extra)

**Quando usar:** Junto com a Habilidade 2 (Plano de Ação).

**O que faz:** Identifica dependências críticas entre etapas, gargalos e o caminho crítico do projeto.

**Exemplo de saída:**
```
Diagrama: Pesquisa → Estrutura → Produção → Gravação → Plataforma → Pré-lançamento → Lançamento
                                          ↘ Edição ↗
Caminho crítico: 13 semanas (sem folga)
Gargalo principal: Estrutura do Curso (bloqueia Produção + Gravação + Edição)
```

📎 [Página completa no Notion](https://www.notion.so/Habilidade-6-Analisar-Riscos-e-Depend-ncias-Extra-4236bd5dbb7881d79ac4d69e52ccb5c8)

---

## 🧪 Demonstração Prática

### Objetivo escolhido

**Criar e lançar o curso online "IA na Prática" em 90 dias**

_Persona:_ Ever Codes (Ever Ferreira) — Ensino de IA Generativa para profissionais em transição de carreira  
_Arquétipo:_ Sábio-Tradutor (traduz tecnologia complexa para iniciantes)  
_ICP fictício:_ Profissionais não-tech (adm, marketing, vendas, RH) que querem dominar IA para produtividade

### Ciclo completo executado

| Etapa | Habilidade | Resultado |
|-------|------------|-----------|
| 1 | Esclarecer objetivo | "Até 25/02/2027, quero criar e lançar o curso 'IA na Prática' com 8 módulos e 24 aulas, vendendo 10+ inscrições no primeiro mês" |
| 2 | Plano de ação | 7 etapas em 13 semanas, com entregáveis e dependências |
| 3 | Adaptar à rotina | 14h/semana (2h/dia seg-sex + 4h sábado), 182h totais |
| 4 | Obstáculos e planos B | 5 riscos mapeados com gatilhos e alternativas |
| 5 | Revisão semanal | Check-in ao final de cada semana com ajustes |
| 6 | Dependências (extra) | Caminho crítico de 13 semanas, gargalo identificado |

### 📸 Habilidade respondendo

![Habilidade 1 respondendo](https://everferreira.github.io/assistente-planejamento-ia/skill1-demo.png)

_Link da habilidade no Notion:_ [Habilidade 1 — Esclarecer e Registrar o Objetivo](https://www.notion.so/Habilidade-1-Esclarecer-e-Registrar-o-Objetivo-4236bd5dbb7881c0a84efd3ed0558ede)

---

## 🚀 Como Usar

1. **Acesse o Planner** no Notion ([link aqui](https://www.notion.so/Planner-IA-Assistente-de-Planejamento-4236bd5dbb7881adbfc3d01de6a21488))
2. **Escolha um objetivo** — real ou fictício. O assistente funciona para qualquer um
3. **Abra a Habilidade 1** e peça para a IA esclarecer e registrar o objetivo
4. **Siga as habilidades em ordem** — cada uma constrói sobre a anterior
5. **Use a Habilidade 5 semanalmente** — revisão é o que mantém o plano vivo

As habilidades podem ser usadas em **qualquer LLM** (ChatGPT, Claude, DeepSeek, Gemini). O prompt template está em cada página de habilidade — é só copiar e colar com seu objetivo.

---

## 💡 Evoluções Futuras

- [ ] **Revisão semanal agendada** — um cron job que lê o objetivo ativo e prepara a semana seguinte automaticamente
- [ ] **Planner conectado ao ChatGPT** — via plugin do Notion, sem copiar e colar
- [ ] **Integração com Google Agenda** — os blocos de rotina viram eventos no calendário
- [ ] **Habilidades exportadas para outras IAs** — levar o método para Claude, Gemini ou qualquer LLM
- [ ] **Dashboard de progresso** — gráfico mostrando evolução semanal dos marcos

---

## 👩‍💻 Autora

**Ever Maria Tobias Ferreira**  
Instrutora Sênior de Tecnologia | Ctrl+Play

[![GitHub](https://img.shields.io/badge/GitHub-everferreira-1A365D?style=flat&logo=github)](https://github.com/everferreira)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-evermaria-1A365D?style=flat&logo=linkedin)](https://linkedin.com/in/evermaria)
[![YouTube](https://img.shields.io/badge/YouTube-Ever%20Codes-1A365D?style=flat&logo=youtube)](https://youtube.com/@evercodes)

---

> _Este é um projeto de demonstração com dados fictícios. Nenhum objetivo pessoal ou informação confidencial foi utilizado._  
> ⌨️ com 💜 por Ever Ferreira · Projeto Final DIO · 2026