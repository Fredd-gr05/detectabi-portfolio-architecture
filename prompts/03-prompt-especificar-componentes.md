# PROMPT 03: ESPECIFICAR (Componentes)

Detalhe os componentes de cada módulo definido no ESTRUTURAR.

## Contexto

📍 **Posição:** Etapa 3 de 4 no Gradiente de Profundidade
📊 **Gradiente:** ESPECIFICAR → COMPONENTE
👁️ **Entrada:** Output do ESTRUTURAR (02-prompt-estruturar.md)

## Objetivo

Detalhar tecnicamente cada módulo, especificando:
- Componentes que compõem cada módulo
- Funções e responsabilidades de cada componente
- Fluxo de dados (inputs/outputs)
- Requisitos funcionais

## Template de Saída

```markdown
# [PRODUTO] - ESPECIFICAR (Componentes)

📍 Posição: Etapa 3 de 4
📊 Gradiente: ESPECIFICAR → COMPONENTE

## Módulo 1: [Nome]

### Componente 1.1: [Nome]

**Função:** [o que faz]

**Input:** 
- [dados que recebe]

**Output:**
- [dados que produz]

**Requisitos Funcionais:**
- RF01: [requisito funcional 1]
- RF02: [requisito funcional 2]

**Dependências:**
- [outros componentes]

### Componente 1.2: [Nome]

[Repetir estrutura]

---

## Módulo 2: [Nome]

### Componente 2.1: [Nome]

[Repetir estrutura]

[Máximo 5 componentes por módulo]

✅ **Status:** Aguardando aprovação
```

## Regras

1. ❌ **NUNCA avançar sem aprovação**
2. Máximo de 5 componentes por módulo
3. Cada componente deve ter função única e bem definida
4. Especificar claramente inputs e outputs
5. Requisitos funcionais devem ser mensuráveis
6. Usar nomenclatura consistente (RF01, RF02, etc.)

## Exemplo Prático

### Módulo: Coleta de Dados

#### Componente 1.1: Conector API

**Função:** Extrair dados de APIs externas

**Input:**
- Credenciais de API
- Parâmetros de consulta

**Output:**
- JSON com dados brutos
- Log de execução

**Requisitos Funcionais:**
- RF01: Suportar autenticação OAuth 2.0
- RF02: Implementar retry automático em caso de falha
- RF03: Processar até 1000 registros por minuto

## Próximos Passos

Após aprovação, prosseguir para:
- **04-prompt-especificar-elementos.md**
