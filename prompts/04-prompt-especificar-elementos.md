# PROMPT 04: ESPECIFICAR (Elementos)

Detalhe elementos individuais de cada componente.

## Contexto

📍 **Posição:** Etapa 4 de 4 no Gradiente de Profundidade (antes do DOCUMENTAR)
📊 **Gradiente:** ESPECIFICAR → ELEMENTO
👁️ **Entrada:** Output do ESPECIFICAR Componentes (03-prompt-especificar-componentes.md)

## Objetivo

Detalhar granularmente cada componente, especificando:
- Elementos que compõem cada componente
- Tipos de dados e propriedades
- Validações e regras de negócio
- Opções e valores possíveis

## Template de Saída

```markdown
# [PRODUTO] - ESPECIFICAR (Elementos)

📍 Posição: Etapa 4 de 4
📊 Gradiente: ESPECIFICAR → ELEMENTO

## Componente: [Nome]

### Elemento 1: [Nome]

**Descrição:** [o que é]

**Tipo:** [texto/número/escala/boolean/data/lista]

**Propriedades:**
- Obrigatório: Sim/Não
- Valor padrão: [se aplicável]
- Validação: [regras]

**Opções** (se aplicável):

| Valor | Label | Peso/Score |
|-------|-------|------------|
| 1 | [opção 1] | [peso] |
| 2 | [opção 2] | [peso] |

**Regras de Negócio:**
- RN01: [regra 1]
- RN02: [regra 2]

---

### Elemento 2: [Nome]

[Repetir estrutura]

[Máximo 20 elementos por componente]

✅ **Status:** Aguardando aprovação
```

## Tipos de Dados Possíveis

1. **Texto (string):**
   - Texto livre
   - Texto com validação (email, URL, etc.)
   - Texto limitado (max caracteres)

2. **Número (number):**
   - Inteiro
   - Decimal
   - Monetário

3. **Escala (scale):**
   - Likert (1-5, 1-7, etc.)
   - Percentual (0-100)
   - Customizado

4. **Boolean:**
   - Sim/Não
   - Verdadeiro/Falso

5. **Data (date):**
   - Data completa
   - Data e hora
   - Período

6. **Lista (array):**
   - Múltipla escolha
   - Tags

## Regras

1. ❌ **NUNCA avançar sem aprovação**
2. Máximo de 20 elementos por componente
3. Cada elemento deve ter tipo claramente definido
4. Especificar obrigatoriedade e validações
5. Para escalas e opções, definir pesos quando aplicável
6. Regras de negócio devem ser claras e testáveis

## Exemplo Prático

### Componente: Formulário de Diagnóstico

#### Elemento 1: Faturamento Mensal

**Descrição:** Faturamento médio mensal da empresa

**Tipo:** Escala (faixas)

**Propriedades:**
- Obrigatório: Sim
- Valor padrão: Não informado

**Opções:**

| Valor | Label | Score |
|-------|-------|-------|
| 1 | Até R$ 10k | 1 |
| 2 | R$ 10k - R$ 50k | 2 |
| 3 | R$ 50k - R$ 100k | 3 |
| 4 | R$ 100k - R$ 500k | 4 |
| 5 | Acima de R$ 500k | 5 |

**Regras de Negócio:**
- RN01: Faturamento < R$ 10k qualifica para Diagnóstico gratuito apenas
- RN02: Faturamento > R$ 100k qualifica para Professional

## Próximos Passos

Após aprovação, prosseguir para:
- **05-prompt-documentar.md**
