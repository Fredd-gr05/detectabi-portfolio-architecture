# ROADMAP: Guia de Uso do Repositório DetectaBI

Este repositório é o **Sistema Operacional de Arquitetura** da DetectaBI. Ele utiliza gradientes de profundidade e decomposição para transformar ideias brutas em produtos técnicos documentados e prontos para implementação.

## 🏗️ Resumo Explicativo

### O que é este repositório?
É um sistema estruturado que transforma ideias de produtos em especificações técnicas completas através de 5 etapas sequenciais (prompts).

### Estrutura Principal
- **`prompts/`**: Motor de execução com 5 prompts sequenciais (01-CONSOLIDAR → 05-DOCUMENTAR)
- **`produtos/`**: Catálogo de especificações finalizadas dos produtos
- **`portfolio-produtos-seed.md`**: Visão estratégica do funil com 9 produtos

### Gradientes Utilizados
1. **Profundidade**: CONSOLIDAR → ESTRUTURAR → ESPECIFICAR → DOCUMENTAR
2. **Decomposição**: PRODUTO → MÓDULO → COMPONENTE → ELEMENTO → ATRIBUTO

---

## 🗺️ ROADMAP 1: Criar Produto do Portfólio

**Objetivo:** Desenvolver um produto listado em `portfolio-produtos-seed.md` (ex: P02, P03)

### Passo a Passo
1. **Verificar Escopo** → Abra `produtos/README.md` e identifique o produto
2. **Prompt 01 (CONSOLIDAR)** → Use `prompts/01-prompt-consolidar.md`
   - Input: Ideia do produto + objetivos
   - Output: Visão consolidada + objetivos claros
   - ✅ Aguarde aprovação antes de prosseguir

3. **Prompt 02 (ESTRUTURAR)** → Use `prompts/02-prompt-estruturar.md`
   - Input: Output do Prompt 01
   - Output: 3-5 módulos principais + relações com outros produtos
   - ✅ Aguarde aprovação

4. **Prompt 03 (ESPECIFICAR Componentes)** → Use `prompts/03-prompt-especificar-componentes.md`
   - Input: Output do Prompt 02
   - Output: Componentes de cada módulo (máx 5 por módulo)
   - ✅ Aguarde aprovação

5. **Prompt 04 (ESPECIFICAR Elementos)** → Use `prompts/04-prompt-especificar-elementos.md`
   - Input: Output do Prompt 03
   - Output: Elementos individuais com tipos, validações e regras
   - ✅ Aguarde aprovação

6. **Prompt 05 (DOCUMENTAR)** → Use `prompts/05-prompt-documentar.md`
   - Input: Output do Prompt 04
   - Output: Schemas JSON, SQL, Código Python, Testes, API
   - ✅ Produto completo!

7. **Salvar** → Crie arquivo `produtos/PXX-nome.md` com toda especificação

---

## 🗺️ ROADMAP 2: Melhorar Produto Existente

**Objetivo:** Refinar ou adicionar funcionalidades a um produto já documentado

### Identificar Nível de Mudança
| Tipo de Mudança | Prompt Inicial | Exemplo |
|-----------------|----------------|---------|
| Arquitetura geral | Prompt 02 (Estruturar) | Adicionar novo módulo |
| Novo componente | Prompt 03 (Componentes) | Adicionar engine de cálculo |
| Novo campo/validação | Prompt 04 (Elementos) | Adicionar campo "ticket_medio" |
| Atualizar código | Prompt 05 (Documentar) | Mudar biblioteca PDF |

### Passo a Passo
1. **Localizar** → Abra o arquivo em `produtos/PXX-nome.md`
2. **Identificar Nível** → Use a tabela acima para escolher o prompt inicial
3. **Executar Prompts** → Execute do nível escolhido até o Prompt 05
4. **Atualizar Arquivo** → Faça commit das mudanças no arquivo original
5. **Validar** → Teste as mudanças em ambiente de desenvolvimento

---

## 🗺️ ROADMAP 3: Criar Novo Produto (Validação)

**Objetivo:** Adicionar produto completamente novo ao ecossistema

### Check de Enquadramento
Responda estas perguntas antes de criar:

1. **Onde se enquadra no funil?**
   - 🎯 Topo (R$ 0 - Lead Magnet)
   - 💰 Meio (R$ 19-497 - Entrada/SaaS Básico)
   - 💎 Fundo (R$ 1k+ - Premium/Enterprise)

2. **Por que adicionar?**
   - Resolve gap de conversão entre produtos?
   - Atende demanda não coberta?
   - Complementa produto existente?

3. **Quais integrações necessárias?**
   - Consome dados de qual produto anterior?
   - Gera dados para qual produto seguinte?

### Passo a Passo
1. **Validar Estratégia** → Responda as perguntas acima
2. **Atualizar Seed** → Adicione descrição em `portfolio-produtos-seed.md`
   ```markdown
   ### Produto X: Nome do Produto
   **Preço:** R$ XXX
   **Ideia Central:** [descrição]
   **Output:** spec_xxx.json
   **Objetivo:** [objetivo no funil]
   ```

3. **Criar Draft** → Crie arquivo `produtos/PXX-nome.md` com contexto inicial
4. **Seguir ROADMAP 1** → Execute os 5 prompts sequencialmente

---

## 🗺️ ROADMAP 4: Adicionar Framework ou Função

**Objetivo:** Injetar nova metodologia (ex: Design Thinking) ou função técnica

### Tipos de Adição
- **Framework metodológico** (ex: CCE, Johari, Design Thinking)
- **Função técnica** (ex: novo cálculo, validação, integração)
- **Componente reutilizável** (ex: gerador de PDF, enviador de email)

### Passo a Passo

#### Para Framework Metodológico:
1. **Documentar Base** → Adicione teoria em `frameworks-metodologia.md`
   ```markdown
   ## Nome do Framework
   ### Origem
   ### Aplicação
   ### Elementos
   ```

2. **Definir Módulo** → Use Prompt 03 para transformar em componente funcional
3. **Definir Campos** → Use Prompt 04 para especificar inputs necessários
4. **Gerar Código** → Use Prompt 05 para criar implementação
5. **Integrar** → Adicione ao produto relevante em `produtos/`

#### Para Função Técnica:
1. **Identificar Produto** → Qual produto precisa da função?
2. **Nível de Adição**:
   - Novo módulo? → Prompt 02
   - Novo componente? → Prompt 03
   - Nova validação? → Prompt 04
3. **Executar Prompts** → Do nível escolhido até Prompt 05
4. **Atualizar** → Commit no arquivo do produto

---

## 📊 Diagrama de Fluxo Visual

```
┌─────────────────┐
│  Ideia/Demanda  │
└────────┬────────┘
         │
         ▼
    ┌────────┐
    │ Existe?│
    └───┬─┬──┘
        │ │
    Sim │ │ Não
        │ │
        │ └──────────────┐
        │                │
        ▼                ▼
   ┌─────────┐    ┌──────────────┐
   │ Abrir   │    │ Validar      │
   │ PXX.md  │    │ Enquadramento│
   └────┬────┘    └──────┬───────┘
        │                │
        │         ┌──────▼────────┐
        │         │ Adicionar em  │
        │         │ seed.md       │
        │         └──────┬────────┘
        │                │
        │         ┌──────▼────────┐
        │         │ Criar PXX.md  │
        │         └──────┬────────┘
        │                │
        └────────────────┘
                 │
                 ▼
        ┌────────────────┐
        │ Prompt 01:     │
        │ CONSOLIDAR     │
        └────────┬───────┘
                 │ ✅ Aprovado?
                 ▼
        ┌────────────────┐
        │ Prompt 02:     │
        │ ESTRUTURAR     │
        └────────┬───────┘
                 │ ✅ Aprovado?
                 ▼
        ┌────────────────┐
        │ Prompt 03:     │
        │ ESPECIFICAR    │
        │ Componentes    │
        └────────┬───────┘
                 │ ✅ Aprovado?
                 ▼
        ┌────────────────┐
        │ Prompt 04:     │
        │ ESPECIFICAR    │
        │ Elementos      │
        └────────┬───────┘
                 │ ✅ Aprovado?
                 ▼
        ┌────────────────┐
        │ Prompt 05:     │
        │ DOCUMENTAR     │
        └────────┬───────┘
                 │
                 ▼
        ┌────────────────┐
        │ Produto        │
        │ Completo       │
        └────────────────┘
```

---

## 🚦 Regras de Ouro

1. **❌ NÃO PULE ETAPAS**: Cada prompt depende do anterior
2. **✅ APROVAÇÃO OBRIGATÓRIA**: Valide cada saída antes de avançar
3. **📝 OUTPUT É ENTRADA**: Cada etapa gera input para a próxima
4. **🔄 PODE VOLTAR**: Se algo está errado, volte ao prompt anterior
5. **💾 SEMPRE SALVE**: Documente cada output em `produtos/`

---

## 🛠️ Troubleshooting

| Problema | Solução |
|----------|---------|
| "Não sei por onde começar" | Comece sempre pelo `README.md` principal |
| "Pulei uma etapa" | Volte 1 nível e execute o prompt pulado |
| "Output não faz sentido" | Verifique se o input anterior foi aprovado |
| "Quero mudar algo pequeno" | Identifique o nível (ver ROADMAP 2) e comece por lá |

---

## ✅ Checklist de Produto Completo

Antes de considerar finalizado:

- [ ] Produto em `portfolio-produtos-seed.md`
- [ ] Arquivo criado em `produtos/PXX-nome.md`
- [ ] Todos os 5 prompts executados
- [ ] Aprovações em cada etapa
- [ ] Schema JSON validado
- [ ] Schema SQL testado
- [ ] Código Python gerado
- [ ] Testes unitários escritos
- [ ] API documentada
- [ ] Integrações mapeadas

---

**Última atualização:** 30/01/2026  
**Versão:** 1.0  
**Mantenedor:** DetectaBI Architecture Team
