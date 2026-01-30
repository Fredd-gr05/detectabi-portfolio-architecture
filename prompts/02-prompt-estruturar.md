# PROMPT 02: ESTRUTURAR

Com base no CONSOLIDAR aprovado, estruture as relações e módulos do produto.

## Contexto

📍 **Posição:** Etapa 2 de 4 no Gradiente de Profundidade
📊 **Gradiente:** ESTRUTURAR → MÓDULO
👁️ **Entrada:** Output do CONSOLIDAR (01-prompt-consolidar.md)

## Objetivo

Organizar logicamente a arquitetura do produto, definindo:
- Relações com outros produtos do ecossistema
- Módulos principais e suas responsabilidades
- Gatilhos de conversão no funil de vendas

## Template de Saída

```markdown
# [PRODUTO] - ESTRUTURAR

📍 Posição: Etapa 2 de 4
📊 Gradiente: ESTRUTURAR → MÓDULO

## Relações no Ecossistema

### Consume (Inputs)

| Origem | Dados/Specs | Obrigatório? |
|--------|-------------|----------------|
| [produto anterior] | spec_xxx.json | Sim/Não |

### Gera (Outputs)

| Destino | Dados/Specs | Formato |
|---------|-------------|----------|
| [produto seguinte] | spec_yyy.json | JSON |

### Gatilho de Conversão

**Condição:** [quando]
**Ação:** [email/pitch]
**Meta:** [%]

## Módulos Principais

1. **Módulo 1:** [Nome]
   - Responsabilidade: [descrição]
   - Dependências: [outros módulos]

2. **Módulo 2:** [Nome]
   - Responsabilidade: [descrição]
   - Dependências: [outros módulos]

[Máximo 5 módulos]

✅ **Status:** Aguardando aprovação
```

## Regras

1. ❌ **NUNCA avançar sem aprovação**
2. Máximo de 5 módulos por produto
3. Cada módulo deve ter responsabilidade clara
4. Definir claramente inputs e outputs
5. Especificar gatilhos de conversão para produtos pagos

## Próximos Passos

Após aprovação, prosseguir para:
- **03-prompt-especificar-componentes.md**
