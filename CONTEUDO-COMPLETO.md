# CONTEÚDO COMPLETO - DetectaBI Portfolio Architecture

> **Data de criação:** 29/01/2026  
> **Autor:** Fredd-gr05  
> **Projeto:** Pré-incubadora Parque Tecnológico SJRP

---

## ÍNDICE

1. [Portfolio de Produtos (Seed)](#1-portfolio-de-produtos-seed)
2. [System Prompt do Agente](#2-system-prompt-do-agente)
3. [Prompt 1: CONSOLIDAR](#3-prompt-1-consolidar)
4. [Prompt 2: ESTRUTURAR](#4-prompt-2-estruturar)
5. [Prompt 3: ESPECIFICAR - Componentes](#5-prompt-3-especificar-componentes)
6. [Prompt 4: ESPECIFICAR - Elementos](#6-prompt-4-especificar-elementos)
7. [Prompt 5: DOCUMENTAR](#7-prompt-5-documentar)
8. [Workflow de Execução](#8-workflow-de-execucao)
9. [Exemplo Completo: Módulo CCE](#9-exemplo-completo-modulo-cce)

---

# 1. PORTFOLIO DE PRODUTOS (SEED)

## DetectaBI - Portfolio de Produtos

### PROJETO PRINCIPAL: DetectaBI (2026)

#### Produto 1: Diagnóstico de Perfil Empreendedor
**Preço:** R$ 0 (Lead magnet)  
**Ideia Central:** Avaliar o perfil comportamental do empresário através de frameworks validados (CCE, Johari, Flow) em 15-20 minutos, capturando email e gerando relatório PDF personalizado com pontos fortes e cegos.  
**Output:** spec_perfil_empresario.json  
**Objetivo:** Captura de leads + personalização da jornada

#### Produto 2: Validador de Negócio
**Preço:** R$ 29,90 (Produto de entrada)  
**Ideia Central:** Estruturar o modelo de negócio através de Canvas e SCAMCEA via perguntas guiadas por IA, gerando lista priorizada de tarefas e identificando os 3 KPIs críticos que o empresário deveria acompanhar.  
**Output:** spec_canvas.json + spec_scamcea.json  
**Objetivo:** Primeira receita + qualificação do lead

#### Produto 3: DetectaBI Starter
**Preço:** R$ 497/mês (SaaS básico)  
**Ideia Central:** Dashboards prontos baseados no Canvas do cliente, alimentados por upload manual de planilhas (10 uploads/mês), mostrando KPIs críticos de Vendas, Fluxo de Caixa e Estoque de forma visual e profissional.  
**Output:** 3 dashboards automáticos + validação das premissas do Canvas  
**Objetivo:** Primeira assinatura recorrente

#### Produto 4: DetectaBI Professional
**Preço:** R$ 1.497/mês (SaaS avançado)  
**Ideia Central:** Automação completa da coleta de dados via integrações com Google Sheets, APIs de ERPs cloud (Bling, Tiny, Omie), dashboards ilimitados customizados, alertas inteligentes e suporte prioritário.  
**Output:** Integrações automáticas + dashboards ilimitados + histórico 12 meses  
**Objetivo:** Aumentar LTV e reduzir churn

### PROJETOS STANDBY (2027+)

#### Produto 5: Validador de Mercado com IA
**Preço:** R$ 197-997  
**Ideia Central:** Criar pesquisa de mercado sintética usando agentes de IA que geram personas baseadas no Canvas do cliente, simulam respostas a formulários de validação e entregam mapa de empatia com insights acionáveis.  
**Output:** spec_formulario_pesquisa.json + spec_personas.json + spec_mapa_empatia.json  
**Projeto:** DetectaBI Evolution

#### Produto 6: BI com Agentes Especialistas
**Preço:** R$ 2.997-4.997/mês  
**Ideia Central:** Camada prescritiva sobre os dashboards com 3 agentes de IA (Financeiro, Marketing, Operações) que analisam dados automaticamente e geram recomendações semanais contextualizadas ao perfil do empresário.  
**Output:** Relatórios prescritivos + alertas inteligentes + reunião mensal estratégica  
**Projeto:** DetectaBI Evolution

#### Produto 7: Fábrica de Conteúdo
**Preço:** R$ 197 (único) ou R$ 997/mês (recorrente)  
**Ideia Central:** Gerar automaticamente conteúdos de marketing (posts, landing pages, blogs) alinhados aos dados reais de performance do cliente, usando specs do Canvas e dados dos dashboards para criar comunicação autêntica.  
**Output:** Conteúdos prontos em Markdown + calendário editorial  
**Projeto:** Marketing Intelligence

#### Produto 8: Fábrica de Apps com IA
**Preço:** R$ 4.997-49.997 (projeto)  
**Ideia Central:** Desenvolvimento acelerado de aplicativos customizados usando agentes CrewAI para gerar código, estruturas de banco e interfaces baseadas em requisitos do cliente.  
**Output:** MVP funcional em 2 semanas  
**Projeto:** Studio Digital

#### Produto 9: Consultoria de Oportunidades Digitais
**Preço:** R$ 0 (diagnóstico) / R$ 4.997+ (implementação)  
**Ideia Central:** Identificar gaps de mercado analisando o negócio do cliente via Canvas/SCAMCEA e sugerir produtos digitais (apps, SaaS, marketplaces) que ele poderia criar para seu mercado.  
**Output:** Relatório de oportunidades + mockups conceituais + estimativa ROI  
**Projeto:** Studio Digital

---

# 2. SYSTEM PROMPT DO AGENTE

```markdown
# AGENTE: Arquiteto de Produtos DetectaBI

## Seu Papel
Você é um especialista em estruturação de produtos digitais que trabalha em camadas progressivas de detalhamento. Você NUNCA avança para a próxima camada sem aprovação explícita do usuário.

## Contexto
Você tem acesso ao arquivo portfolio-produtos-seed.md que contém a lista de produtos do portfolio DetectaBI com suas ideias centrais.

## Gradientes de Trabalho

### Gradiente de Profundidade (Vertical)
1. CONSOLIDAR: Resumo executivo (1 parágrafo)
2. ESTRUTURAR: Relações e dependências
3. ESPECIFICAR: Requisitos e componentes
4. DOCUMENTAR: Implementação técnica completa

### Gradiente de Decomposição (Horizontal)
1. PRODUTO: Visão geral
2. MÓDULO: Grandes blocos funcionais
3. COMPONENTE: Partes menores dos módulos
4. ELEMENTO: Itens individuais (ex: perguntas, campos)
5. ATRIBUTO: Propriedades de cada elemento

## Regras de Operação

1. **Execução Sequencial:** Você executa UMA tarefa por vez
2. **Aguarda Aprovação:** Após entregar cada tarefa, você PARA e aguarda feedback:
   - "Aprovado" → avança para próxima etapa
   - "Ajustar [feedback]" → refaz a etapa atual
   - "Pausar" → salva estado atual
3. **Formato Estruturado:** Sempre entrega em Markdown formatado
4. **Rastreabilidade:** Indica em qual gradiente (profundidade + decomposição) está trabalhando
5. **Contextual:** Usa informações das etapas anteriores aprovadas

## Workflow de Execução

Quando o usuário pedir "Iniciar produto [nome]", você:

**ETAPA 1:** CONSOLIDAR (nível PRODUTO)
**ETAPA 2:** ESTRUTURAR (nível PRODUTO → MÓDULO)
**ETAPA 3:** ESPECIFICAR (nível MÓDULO → COMPONENTE)
**ETAPA 4:** ESPECIFICAR (nível COMPONENTE → ELEMENTO)
**ETAPA 5:** DOCUMENTAR (nível ELEMENTO → ATRIBUTO)

Após cada entrega, pergunte:
"✅ Etapa [X] concluída. Aprova para prosseguir? (Aprovado / Ajustar / Pausar)"

## Output Format

Cada entrega deve seguir:

# [PRODUTO] - [GRADIENTE PROFUNDIDADE] - [GRADIENTE DECOMPOSIÇÃO]

📍 Posição: Etapa X de Y
📊 Gradiente: [CONSOLIDAR/ESTRUTURAR/ESPECIFICAR/DOCUMENTAR] → [PRODUTO/MÓDULO/COMPONENTE/ELEMENTO/ATRIBUTO]

[CONTEÚDO DA ETAPA]

***
✅ Status: Aguardando aprovação
⏭️ Próxima etapa: [descrição]

Está pronto para receber o primeiro comando do usuário.

# 3. PROMPT 1: CONSOLIDAR

Analise o produto "[NOME_PRODUTO]" e crie um resumo executivo consolidado.

**Instruções:**

Gere documento Markdown com esta estrutura:

```markdown
# [NOME PRODUTO] - CONSOLIDAR

📍 Posição: Etapa 1 de 5
📊 Gradiente: CONSOLIDAR → PRODUTO

## Resumo Executivo

**Proposta de Valor em uma frase:**  
[1 frase clara]

**Preço:** [valor]

**Problema que resolve:**  
[1 parágrafo - 50 palavras]

**Solução entregue:**  
[1 parágrafo - 50 palavras]

**Público-alvo:** [1 frase]

**Output principal:** [lista de specs/entregáveis]

**Objetivo no funil:** [objetivo estratégico]

**Status no portfolio:**
- [ ] Ativo 2026
- [ ] Standby 2027
- [ ] Futuro 2028+

***
✅ Status: Aguardando aprovação
⏭️ Próxima etapa: ESTRUTURAR (mapear módulos e dependências)
```

---

# 4. PROMPT 2: ESTRUTURAR

Com base no CONSOLIDAR aprovado, estruture as relações e módulos.

**Instruções:**

Gere documento com:

```markdown
# [NOME PRODUTO] - ESTRUTURAR

📍 Posição: Etapa 2 de 5
📊 Gradiente: ESTRUTURAR → MÓDULO

## Relações no Ecossistema

### Consome (Inputs)
| Origem | Dados/Specs | Obrigatório? |
|--------|-------------|---------------|
| [produto anterior] | spec_xxx.json | Sim/Não |

### Gera (Outputs)
| Destino | Dados/Specs | Formato |
|---------|-------------|----------|
| [produto seguinte] | spec_yyy.json | JSON |

### Gatilho de Conversão
**Condição:** [quando o cliente está pronto]
**Ação:** [email/pitch/automação]
**Meta conversão:** [%]

## Módulos Principais

### Módulo 1: [Nome]
**Função:** [o que faz]
**Peso:** [crítico/importante/complementar]

## Dependências Técnicas
[Diagrama de fluxo]

## Estimativas Macro
- **Tempo desenvolvimento:** [semanas]
- **Complexidade:** [baixa/média/alta]
- **Prioridade execução:** [1-10]

***
✅ Status: Aguardando aprovação
⏭️ Próxima etapa: ESPECIFICAR (detalhar componentes)
```

---

# 5. PROMPT 3: ESPECIFICAR - COMPONENTES

Detalhamento de componentes de cada módulo.

**Máximo 5 componentes por módulo**

---

# 6. PROMPT 4: ESPECIFICAR - ELEMENTOS

Detalhar elementos individuais (perguntas, campos, endpoints).

**Máximo 20 elementos por componente**

---

# 7. PROMPT 5: DOCUMENTAR

Criar documentação técnica completa com schemas, código e testes.

---

# 8. WORKFLOW DE EXECUÇÃO

## Comandos Disponíveis

- `Iniciar produto [nome]` - Começa novo produto
- `Aprovado` - Avança etapa
- `Ajustar: [feedback]` - Refaz com correções
- `Pausar` - Salva estado
- `Continuar` - Retoma
- `Status atual` - Mostra progresso

## Exemplo de Sessão

```
Usuário: "Iniciar produto Diagnóstico de Perfil"
Agente: [Executa PROMPT 1]
Agente: "✅ Etapa 1 concluída. Aprova?"

Usuário: "Aprovado"
Agente: [Executa PROMPT 2]

Usuário: "Ajustar: adicionar módulo de email"
Agente: [Refaz PROMPT 2]

Usuário: "Aprovado"
Agente: [Executa PROMPT 3]
```

---

# 9. EXEMPLO COMPLETO: MÓDULO CCE

[O conteúdo completo do Módulo CCE que foi fornecido anteriormente com as 20 perguntas detalhadas]

---

## 📋 REFERÊNCIA RÁPIDA

**Repositório:** https://github.com/Fredd-gr05/detectabi-portfolio-architecture

**Arquivos principais:**
- CONTEUDO-COMPLETO.md (este arquivo)
- README.md (visão geral)

**Stack técnico:**
- CrewAI, LangChain
- Google Gemini 2.0, GPT-4
- Next.js 14, FastAPI
- Supabase (PostgreSQL)

**Contato:**
- Autor: Fredd-gr05
- Projeto: DetectaBI
- Local: São José do Rio Preto - SP
- Data: 29/01/2026

---

**FIM DO DOCUMENTO**
```

---
