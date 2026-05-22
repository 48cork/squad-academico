# Project Brief: squad-academico

> Gerado por Atlas (@analyst) via AIOX create-doc workflow
> Data: 2026-05-22

---

## Executive Summary

**squad-academico** é um sistema de agentes especializados orquestrados pelo AIOX que opera como **bancada intelectual virtual** do pesquisador. Cada agente tem uma função epistêmica distinta no ciclo de produção do artigo — nenhum deles escreve o texto final.

O projeto apoia o Prof. Sergio Farias (UFCG / pós-doc EHESS) na produção de artigos acadêmicos A1 em sociologia crítica dos algoritmos. Os agentes não substituem a autoria — eles amplificam a capacidade analítica do pesquisador: pesquisando referências bibliográficas em periódicos internacionais, formulando perguntas socráticas que tensionam o argumento teórico, analisando dados empíricos dos participantes e identificando lacunas e contradições no manuscrito.

O projeto-piloto ancora-se no artigo *"Does AI Have a Social Class?"* — um experimento empírico com ChatGPT e duas personas de classes sociais contrastantes no sertão da Paraíba, Brasil — investigando se e como sistemas de IA reproduzem, naturalizam ou amplificam desigualdades de classe no acesso ao conhecimento.

---

## Problem Statement

### Problema Central

Pesquisadores solitários em sociologia crítica enfrentam uma assimetria estrutural: produzir artigos A1 internacionais exige simultaneamente domínio bibliográfico denso (Bourdieu, Wacquant, Eubanks, Noble, Benjamin, van Dijk), rigor empírico, fluência em inglês acadêmico de alto nível e capacidade de antecipar as objeções dos revisores — tudo isso sem equipe de pesquisa, sem bolsista e sob pressão de produtividade institucional.

Ferramentas genéricas de IA (ChatGPT, Copilot) não resolvem esse problema: elas redigem, mas não **questionam**; sugerem referências, mas não **verificam relevância teórica**; e não conhecem o campo específico da sociologia digital crítica nem as convenções dos periódicos-alvo (ex: *New Media & Society*, *Big Data & Society*, *Information, Communication & Society*).

### Lacuna Específica

Não existe hoje um sistema de agentes especializados para o ciclo de produção de um artigo acadêmico de sociologia crítica — da revisão de literatura à coerência do argumento empírico — que opere como **parceiro intelectual** e não como ghostwriter.

### Urgência

O experimento empírico do artigo *"Does AI Have a Social Class?"* já foi realizado. Os dados estão disponíveis. O gap entre dado coletado e artigo submetido é exatamente onde o squad intervém.

---

## Proposed Solution

### Conceito Central

**squad-academico** é um sistema de agentes especializados orquestrados pelo AIOX que opera como **bancada intelectual virtual** do pesquisador. Cada agente tem uma função epistêmica distinta no ciclo de produção do artigo — nenhum deles escreve o texto final.

### Agentes Existentes — já implementados e commitados

**6 agentes operacionais**, desenvolvidos e validados no projeto `artigo-ia-classe-social`:

| Agente | Função Epistêmica | Status |
|--------|-------------------|--------|
| **researcher** | Rastreia literatura acadêmica em bases indexadas e entrega referências estruturadas com citação literal + relevância descritiva. Nunca argumenta — só localiza. | ✅ Produção |
| **interlocutor** | Parceiro de diálogo intelectual para exploração de ideias em desenvolvimento antes de formalização do argumento | ✅ Produção |
| **analyst** | Analisa dados empíricos do experimento (respostas das personas, padrões linguísticos, diferenças de classe) e identifica achados não óbvios | ✅ Produção |
| **reviewer** | Simula revisão cega de periódico A1 — identifica problemas estruturais do manuscrito com linguagem fria, sem elogios | ✅ Produção |
| **tensioner-class** | Tensionador teórico para o artigo *"Does AI Have a Social Class?"* — 3 modos de ataque ao argumento | ✅ Produção |
| **tensioner-race** | Tensionador teórico para o artigo *"Does AI Have a Race?"* — 3 modos especializados para raça no contexto brasileiro | ✅ Produção |

### Arquitetura de Modos: tensioner

O agente **tensioner** opera em 3 modos declarados explicitamente (`/tensioner-class mode-1/2/3`):

| Modo | Persona | Lógica de Ataque |
|------|---------|-----------------|
| **Mode 1 — Devil's Advocate** | Defensor: "IA não tem classe social. Habitus exige corpo." | Desafia a tese central pela raiz |
| **Mode 2 — Brutal Reviewer** | Sociólogo britânico/alemão, cético em relação à teoria francesa e aos estudos decoloniais | Mínimo 3 problemas críticos, 2 menores. Conclui: *"Major Revision."* |
| **Mode 3 — Classical Interlocutor** | Marx e Weber como alternativas a Bourdieu e Quijano | Questiona cada neologismo: *"O que seu conceito explica que Marx não explica? Seja preciso."* |

**tensioner-race Mode 3** é especializado para o contexto brasileiro: Lélia Gonzalez (*pretugues*) e Florestan Fernandes como interlocutores clássicos, questionando a importação de CRT norte-americano quando o arcabouço brasileiro é mais preciso.

### Princípio de Design Preservado

Nenhum agente escreve o artigo. O **researcher** entrega referências e pergunta *"Qual dessas conecta com o que você está pensando, professor?"*. O **tensioner** nunca sugere correções — apenas ataca e pergunta *"O que sobreviveu?"*. A autoria intelectual permanece integralmente com o pesquisador.

---

## Target Users

### Segmento Primário: Pesquisador Sênior Solo em Sociologia Crítica

**Perfil:** Prof. Sergio Farias — sociólogo, professor na UFCG (Universidade Federal de Campina Grande), pós-doutorando na EHESS (École des Hautes Études en Sciences Sociales, Paris). Pesquisador com formação teórica densa (Bourdieu, Marx, pensamento decolonial, sociologia digital crítica) e experiência empírica de campo no sertão da Paraíba.

**Contexto de trabalho:**
- Opera sem equipe de pesquisa ou bolsistas dedicados à produção de artigos
- Produz em dois idiomas (português e inglês acadêmico A1)
- Publica em periódicos internacionais de alto fator de impacto em ciências sociais
- Conduz experimentos empíricos originais (ex: experimento com personas e ChatGPT)

**Necessidades específicas:**
- Interlocução intelectual que questione o argumento — não que o valide
- Localização rápida de literatura pertinente sem perda de rigor teórico
- Simulação de revisão cega antes da submissão
- Tensionamento do arcabouço teórico para detectar fragilidades antes do revisor

**O que NÃO quer:**
- Que a IA escreva por ele
- Sugestões genéricas desconectadas do campo
- Validação fácil ("ótima ideia, professor!")
- Referências não verificadas ou inventadas

### Segmento Secundário: Pesquisadores em Sociologia Digital / Estudos Críticos de Algoritmos

*Condição: expansão futura após validação com o caso piloto.*

Pesquisadores em programas de pós-graduação em sociologia, comunicação ou ciências sociais computacionais que produzem artigos sobre plataformas digitais, viés algorítmico, desigualdade e tecnologia — e que compartilham o mesmo problema estrutural: produção solo, exigência A1, sem infraestrutura de pesquisa equivalente às universidades do Norte Global.

---

## Goals & Success Metrics

### Objetivos de Negócio (Pesquisa)

- **OBJ-1:** Submeter o artigo *"Does AI Have a Social Class?"* a um periódico A1 internacional (ex: *New Media & Society*, *Big Data & Society*) em até 90 dias após ativação completa do squad
- **OBJ-2:** Reduzir o tempo entre dado coletado e manuscrito submetível de estimados 6-12 meses (solo) para menos de 4 meses (com squad)
- **OBJ-3:** Validar o modelo squad-academico como infraestrutura replicável para o segundo artigo (*"Does AI Have a Race?"*) sem redesenho de agentes

### Métricas de Sucesso do Pesquisador

- Argumento do artigo sobrevive ao Mode 2 (Brutal Reviewer) do tensioner sem revisões estruturais de última hora
- Seção de revisão de literatura cobre os periódicos-alvo dos revisores esperados — zero lacunas bibliográficas apontadas na revisão cega
- O pesquisador identifica pelo menos 2 achados não óbvios nos dados empíricos via agent **analyst** que não havia percebido antes
- Nenhum agente produz texto que o pesquisador incorpora diretamente no manuscrito — autoria permanece 100% humana

### KPIs Operacionais

| KPI | Definição | Meta |
|-----|-----------|------|
| **Artigos submetidos** | Número de submissões A1 produzidas com apoio do squad | ≥ 1 (piloto) |
| **Ciclo de tensionamento** | Rodadas de ataque/defesa do argumento antes da submissão | ≥ 3 rodadas por artigo |
| **Referências validadas** | Referências entregues pelo researcher com DOI verificável e relevância confirmada pelo autor | ≥ 30 por artigo |
| **Taxa de reuso de agentes** | % de agentes do artigo 1 reutilizados sem modificação no artigo 2 | ≥ 80% |
| **Integridade de autoria** | Parágrafos do manuscrito final rastreáveis a texto gerado por IA | 0% |

---

## MVP Scope

### Core Features — Must Have

O MVP é o squad operacional para o artigo *"Does AI Have a Social Class?"* — os 6 agentes já existentes, integrados no repositório `squad-academico`, com documentação de uso suficiente para o pesquisador operar de forma autônoma.

- **researcher:** busca e entrega referências estruturadas com DOI + citação literal + pergunta de ancoragem ao autor
- **interlocutor:** diálogo socrático para exploração de ideias em desenvolvimento
- **analyst:** análise dos dados empíricos do experimento (respostas de ChatGPT às duas personas de classe)
- **reviewer:** simulação de revisão cega A1 com linguagem fria e lista de problemas estruturais
- **tensioner-class:** 3 modos de tensionamento teórico para o argumento de classe
- **tensioner-race:** 3 modos de tensionamento teórico para o argumento de raça (Mode 3 com Lélia Gonzalez e Florestan Fernandes)
- **Documentação de uso:** guia de ativação de cada agente, quando usar cada modo, protocolo de sessão

### Out of Scope para MVP

- Interface gráfica ou frontend de qualquer tipo
- Integração automática com bases bibliográficas (Scopus, WoS) via API
- Geração automática de seções do manuscrito
- Agentes para outros campos além de sociologia crítica de algoritmos
- Sistema de versionamento do argumento ao longo das sessões
- Novos agentes antes da submissão do artigo 1

### MVP Success Criteria

O MVP está completo quando:
1. Os 6 agentes estão commitados, documentados e ativáveis via Claude Code no repositório `squad-academico`
2. O pesquisador consegue iniciar uma sessão de tensionamento com `tensioner-class mode-2` sem assistência técnica
3. Uma rodada completa de revisão de literatura + tensionamento + revisão simulada foi executada para pelo menos uma seção do artigo
4. O projeto `artigo-ia-classe-social` foi migrado ou referenciado corretamente como caso de uso do squad

---

## Post-MVP Vision

### Phase 2 — Artigo 2 e Consolidação

- Ativar **tensioner-race** como agente primário para *"Does AI Have a Race?"*
- Avaliar quais agentes precisaram de adaptação entre artigo 1 e 2 — documentar delta de reutilização
- Criar `docs/guides/protocol-session.md`: protocolo padrão de sessão de trabalho com o squad
- Adicionar agente **argument-mapper** para rastrear a evolução do argumento central

### Visão de Longo Prazo (1-2 anos)

O squad-academico como **infraestrutura de pesquisa** para o programa de sociologia crítica da UFCG — não um produto comercial, mas um modelo de trabalho intelectual mediado por IA que possa ser documentado, publicado como metodologia e replicado por outros pesquisadores do Sul Global com acesso limitado a equipes de pesquisa.

O próprio squad pode se tornar objeto de análise: um artigo sobre *como pesquisadores do Sul Global usam IA sem terceirizar o pensamento* — metodologia reflexiva, pesquisa sobre a pesquisa.

### Oportunidades de Expansão

- **Novos campos:** agentes especializados para sociologia urbana, educação crítica, antropologia digital
- **Novos tensionadores:** Paulo Freire para educação; Milton Santos para território
- **Publicação metodológica:** artigo descrevendo o squad como método (*Qualitative Inquiry*, *Social Science Computer Review*)
- **Compartilhamento:** template open-source para pesquisadores em pós-graduação

---

## Technical Considerations

### Platform Requirements

- **Plataforma:** Claude Code (CLI) — interface primária de interação com todos os agentes
- **Ambiente:** WSL2 / Ubuntu 24.04 (ambiente atual do pesquisador)
- **Performance:** Latência aceitável para diálogo socrático; sem requisitos de tempo real
- **Disponibilidade:** Uso assíncrono — sessões de trabalho discretas, não contínuas

### Technology Stack

- **Runtime de agentes:** Claude Code com sub-agents (`.claude/agents/*.md`)
- **Orquestração:** AIOX Framework (`.aiox-core/`) — já instalado e operacional
- **Repositório:** Git + GitHub (`48cork/squad-academico`, privado)
- **Formato de agentes:** Markdown com instruções de persona, modos e regras de comportamento
- **Sem frontend:** interação 100% via CLI — decisão intencional

### Architecture Considerations

- **Repository Structure:** monorepo único — agentes do squad-academico + AIOX framework
- **Agent isolation:** cada agente é um arquivo `.md` independente em `.claude/agents/` — sem dependências entre agentes
- **Session state:** sem persistência automática de sessão — o pesquisador gerencia o contexto manualmente
- **Security/Compliance:** repositório privado; dados empíricos dos participantes NÃO commitados — gerenciados localmente, sujeitos às normas do CEP/UFCG
- **Integration:** sem APIs externas no MVP

### Decisão Técnica Central

O design de agentes como arquivos Markdown simples é uma escolha deliberada de **mínima complexidade técnica** que maximiza a longevidade e a autonomia do pesquisador.

---

## Constraints & Assumptions

### Constraints

- **Budget:** Zero — infraestrutura existente (Claude Code, AIOX, GitHub); custo real é token usage da API Anthropic
- **Timeline:** Submissão do artigo *"Does AI Have a Social Class?"* é o deadline implícito de validação do MVP
- **Resources:** Pesquisador solo como único usuário e operador; sem equipe técnica dedicada
- **Technical:** Dependência da API Anthropic — mudanças de pricing, rate limits ou descontinuação afetam diretamente o squad
- **Ética em pesquisa:** Dados empíricos sujeitos às normas do CEP/UFCG — agentes não têm acesso direto a dados identificáveis

### Key Assumptions

- O pesquisador continuará usando Claude Code como interface primária durante o ciclo do artigo
- Os 6 agentes existentes cobrem as necessidades do artigo 1 sem desenvolvimento adicional antes da submissão
- A qualidade das referências entregues pelo **researcher** é suficiente com busca manual orientada
- O tensionamento dos agentes é suficientemente sofisticado para simular revisão cega A1 — hipótese a validar na primeira rodada real
- O argumento de *"Does AI Have a Social Class?"* é suficientemente maduro para iniciar o ciclo com o squad

---

## Risks & Open Questions

### Key Risks

- **Alucinação bibliográfica:** researcher pode entregar DOIs incorretos — mitigação: verificação manual obrigatória antes de usar qualquer referência
- **Uso confirmatório:** se o pesquisador usar os agentes buscando validação, o squad perde sua função — mitigação: agentes têm recusa explícita a elogios
- **Dependência de plataforma:** mudanças na API Anthropic sem mitigação no MVP
- **Scope creep:** pressão para adicionar agentes antes da submissão — mitigação: MVP congelado nos 6 agentes existentes

### Open Questions

- Qual o protocolo ideal de uma sessão de trabalho? (sequência de agentes, duração, quando encerrar)
- O **tensioner** em Mode 2 é suficientemente rigoroso para simular revisores de *New Media & Society* especificamente?
- Como documentar as sessões de tensionamento para que o processo seja metodologicamente citável no artigo?
- O **analyst** tem contexto suficiente sobre os dados empíricos sem acesso direto aos arquivos brutos?

---

## Next Steps

### Immediate Actions

1. Migrar os 6 agentes de `artigo-ia-classe-social` para `squad-academico` e commitar
2. Criar `docs/guides/como-usar-o-squad.md` — guia de ativação e protocolo de sessão
3. Executar primeira rodada real: researcher → interlocutor → tensioner-class mode-2 com uma seção do artigo
4. Handoff para `@pm` para criação do PRD com base neste brief

### PM Handoff

Este Project Brief fornece o contexto completo do **squad-academico**. Para o `@pm`: iniciar em modo PRD Generation, revisar o brief e trabalhar seção por seção com o pesquisador, solicitando esclarecimentos onde necessário. Foco especial em: definição dos épicos por artigo, critérios de aceitação dos agentes, e roadmap de migração dos agentes do projeto `artigo-ia-classe-social`.

---

*— Atlas, investigando a verdade 🔎*
