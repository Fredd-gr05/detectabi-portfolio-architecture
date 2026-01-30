# PROMPT 05: DOCUMENTAR

Crie documentação técnica completa e artefatos implementáveis.

## Contexto

📍 **Posição:** Etapa Final do Gradiente de Profundidade
📊 **Gradiente:** DOCUMENTAR → ATRIBUTO
👁️ **Entrada:** Output do ESPECIFICAR Elementos (04-prompt-especificar-elementos.md)

## Objetivo

Formalizar toda a especificação em documentação técnica e código pronto para implementação:
- Schemas JSON
- Estrutura de banco de dados
- Código Python (agentes/processadores)
- Testes unitários
- Documentação de API

## Template de Saída

```markdown
# [PRODUTO] - DOCUMENTAR

📍 Posição: Etapa Final
📊 Gradiente: DOCUMENTAR → ATRIBUTO

## 1. Schema JSON

```json
{
  "spec_[nome]": {
    "metadata": {
      "version": "1.0.0",
      "created_at": "2025-01-XX",
      "product": "[PRODUTO]"
    },
    "elements": {
      "elemento_1": {
        "type": "string",
        "required": true,
        "validation": {
          "min_length": 1,
          "max_length": 255
        },
        "default": null
      },
      "elemento_2": {
        "type": "number",
        "required": false,
        "validation": {
          "min": 0,
          "max": 100
        },
        "default": 0
      }
    }
  }
}
```

## 2. Schema Database (PostgreSQL)

```sql
-- Tabela principal
CREATE TABLE [nome_produto] (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES auth.users(id),
  elemento_1 VARCHAR(255) NOT NULL,
  elemento_2 INTEGER DEFAULT 0,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Índices
CREATE INDEX idx_[nome]_user_id ON [nome_produto](user_id);
CREATE INDEX idx_[nome]_created_at ON [nome_produto](created_at);

-- Row Level Security (RLS)
ALTER TABLE [nome_produto] ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Users can view own records"
  ON [nome_produto]
  FOR SELECT
  USING (auth.uid() = user_id);

CREATE POLICY "Users can insert own records"
  ON [nome_produto]
  FOR INSERT
  WITH CHECK (auth.uid() = user_id);
```

## 3. Código Python (CrewAI Agent)

```python
from crewai import Agent, Task
from typing import Dict, Any
import json

class [Nome]Agent:
    """Agent responsável por [descrição]."""
    
    def __init__(self, llm):
        self.llm = llm
        self.agent = Agent(
            role="[Role]",
            goal="[Goal]",
            backstory="[Backstory]",
            llm=self.llm,
            verbose=True
        )
    
    def processar(self, dados: Dict[str, Any]) -> Dict[str, Any]:
        """
        Processa os dados de entrada e retorna resultado.
        
        Args:
            dados: Dicionário com dados de entrada
            
        Returns:
            Dicionário com resultado processado
        """
        task = Task(
            description=f"Processar dados: {json.dumps(dados)}",
            agent=self.agent,
            expected_output="JSON estruturado com resultado"
        )
        
        resultado = task.execute()
        return self._validar_output(resultado)
    
    def _validar_output(self, resultado: Any) -> Dict[str, Any]:
        """Valida o output do agente."""
        # Implementar validação
        return resultado
```

## 4. Testes Unitários

```python
import pytest
from unittest.mock import Mock
from [modulo] import [Nome]Agent

@pytest.fixture
def agent():
    """Fixture para criar agent de teste."""
    mock_llm = Mock()
    return [Nome]Agent(mock_llm)

def test_processar_dados_validos(agent):
    """Testa processamento com dados válidos."""
    dados = {
        "elemento_1": "valor_teste",
        "elemento_2": 50
    }
    
    resultado = agent.processar(dados)
    
    assert resultado is not None
    assert "status" in resultado
    assert resultado["status"] == "success"

def test_processar_dados_invalidos(agent):
    """Testa processamento com dados inválidos."""
    dados = {}
    
    with pytest.raises(ValueError):
        agent.processar(dados)
```

## 5. Documentação de API (FastAPI)

```python
from fastapi import APIRouter, HTTPException, Depends
from pydantic import BaseModel
from typing import Optional

router = APIRouter(prefix="/api/[produto]", tags=["[PRODUTO]"])

class [Nome]Request(BaseModel):
    """Modelo de request para [produto]."""
    elemento_1: str
    elemento_2: Optional[int] = 0

class [Nome]Response(BaseModel):
    """Modelo de response para [produto]."""
    id: str
    status: str
    resultado: dict

@router.post("/processar", response_model=[Nome]Response)
async def processar_[nome](
    request: [Nome]Request,
    user_id: str = Depends(get_current_user_id)
):
    """
    Processa dados de [produto].
    
    - **elemento_1**: Descrição do elemento 1
    - **elemento_2**: Descrição do elemento 2
    """
    try:
        # Implementar lógica
        return [Nome]Response(
            id="uuid",
            status="success",
            resultado={}
        )
    except Exception as e:
        raise HTTPException(status_code=500, detail=str(e))
```

## 6. Documentação README do Produto

```markdown
# [PRODUTO]

## Visão Geral
[Descrição do produto]

## Funcionalidades
- [Feature 1]
- [Feature 2]

## Requisitos
- Python 3.11+
- PostgreSQL 15+
- Supabase (opcional)

## Instalação

```bash
pip install -r requirements.txt
```

## Uso

```python
from [modulo] import [Nome]Agent

agent = [Nome]Agent(llm)
resultado = agent.processar(dados)
```

## Variáveis de Ambiente

```env
DATABASE_URL=postgresql://...
SUPABASE_URL=https://...
SUPABASE_KEY=...
```

## Testes

```bash
pytest tests/
```
```

✅ **Status:** PRODUTO COMPLETO E PRONTO PARA IMPLEMENTAÇÃO
```

## Regras

1. ✅ **Este é o prompt FINAL** - após este, o produto está completo
2. Todos os schemas devem ser válidos e testáveis
3. Código Python deve seguir PEP 8
4. Testes devem cobrir cenários principais
5. Documentação deve ser clara e completa
6. Incluir variáveis de ambiente necessárias

## Checklist Final

- [ ] Schema JSON validado
- [ ] Database schema criado e testado
- [ ] Código Python implementado
- [ ] Testes unitários passando
- [ ] API documentada
- [ ] README completo
- [ ] Variáveis de ambiente documentadas

## Próximos Passos

Após aprovação:
1. Deploy em ambiente de desenvolvimento
2. Testes de integração
3. Review de código
4. Deploy em produção
