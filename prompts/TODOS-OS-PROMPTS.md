# Prompts Completos do Sistema DetectaBI

Este arquivo contém todos os prompts para estruturar produtos do portfólio DetectaBI.

---

## PROMPT 02: ESTRUTURAR

Com base no CONSOLIDAR aprovado, estruture as relações e módulos do produto.

### Template de Saída:
```markdown
# [PRODUTO] - ESTRUTURAR
📍 Posição: Etapa 2 de 5
📊 Gradiente: ESTRUTURAR → MÓDULO

## Relações no Ecossistema

### Consome (Inputs)
| Origem | Dados/Specs | Obrigatório? |
|--------|-------------|--------------|
| [produto anterior] | spec_xxx.json | Sim/Não |

### Gera (Outputs)
| Destino | Dados/Specs | Formato |
|---------|-------------|---------|  
| [produto seguinte] | spec_yyy.json | JSON |

### Gatilho de Conversão
**Condição:** [quando]
**Ação:** [email/pitch]
**Meta:** [%]

## Módulos Principais
[5 módulos max]

✅ Status: Aguardando aprovação
```

---

## PROMPT 03: ESPECIFICAR (Componentes)

Detalhe os componentes de cada módulo.

### Template de Saída:
```markdown
# [PRODUTO] - ESPECIFICAR (Componentes)
📍 Etapa 3 de 5
📊 ESPECIFICAR → COMPONENTE

## Módulo 1: [Nome]

### Componente 1.1: [Nome]
**Função:** [o que faz]
**Input:** [recebe]
**Output:** [produz]
**Requisitos:**
- RF01: [requisito]

[Max 5 componentes por módulo]

✅ Status: Aguardando aprovação
```

---

## PROMPT 04: ESPECIFICAR (Elementos)

Detalhe elementos individuais.

### Template de Saída:
```markdown
# [PRODUTO] - ESPECIFICAR (Elementos)
📍 Etapa 4 de 5
📊 ESPECIFICAR → ELEMENTO

## Componente: [Nome]

### Elemento 1: [Nome]
**Descrição:** [o que é]
**Tipo:** [texto/número/escala]
**Propriedades:**
- Obrigatório: Sim/Não

**Opções:**
| Valor | Label | Peso |
|-------|-------|------|

[Max 20 elementos]

✅ Status: Aguardando aprovação  
```

---

## PROMPT 05: DOCUMENTAR

Crie documentação técnica completa.

### Template de Saída:
```markdown
# [PRODUTO] - DOCUMENTAR
📍 Etapa 5 de 5
📊 DOCUMENTAR → ATRIBUTO

## Schema JSON
```json
{
  "spec_[nome]": {
    "elemento_1": {
      "valor": null,
      "tipo": "string"
    }
  }
}
```

## Schema Database (PostgreSQL)
```sql
CREATE TABLE [nome] (
  id UUID PRIMARY KEY,
  campo VARCHAR(100)
);
```

## Código Python
```python
class Agent:
    def processar(self, dados):
        pass
```

## Testes
```python
def test_funcao():
    assert resultado == esperado
```

✅ Status: Produto COMPLETO
```

---

## Uso dos Prompts

1. Use PROMPT 01 (arquivo 01-prompt-consolidar.md)
2. Aguarde aprovação
3. Use PROMPT 02 (acima)
4. Aguarde aprovação
5. Continue até PROMPT 05

**Importante:** NUNCA avançar sem aprovação!
