# P01: Diagnóstico de Perfil Empreendedor

## Posição no Funil

🎯 **Tipo:** Lead Magnet (Porta de Entrada)
💰 **Preço:** R$ 0 (Gratuito)
📈 **Objetivo:** Captura de leads + personalização da jornada

## Ideia Central

Avaliar o perfil comportamental do empresário através de frameworks validados (CCE, Johari, Flow) em 15-20 minutos, capturando email e gerando relatório PDF personalizado com pontos fortes e cegos.

## Outputs Esperados

```json
{
  "spec_perfil_empresario": {
    "metadata": {
      "user_id": "uuid",
      "email": "email@exemplo.com",
      "completed_at": "2025-01-XX"
    },
    "frameworks": {
      "cce": {
        "score_realizacao": 0-100,
        "score_planejamento": 0-100,
        "score_poder": 0-100
      },
      "johari": {
        "arena_publica": [],
        "ponto_cego": [],
        "fachada": [],
        "desconhecido": []
      },
      "flow": {
        "nivel_desafio": 0-10,
        "nivel_habilidade": 0-10,
        "estado_flow": "ansiedade|tedio|flow"
      }
    },
    "relatorio": {
      "pontos_fortes": [],
      "pontos_cegos": [],
      "recomendacoes": []
    }
  }
}
```

## Fluxo do Usuário

1. **Landing Page** - Promessa: "Descubra seu perfil empreendedor em 15 minutos"
2. **Captura de Email** - Antes de iniciar o diagnóstico
3. **Questionário Interativo** - 15-20 perguntas baseadas nos frameworks
4. **Processamento IA** - Análise do perfil via CrewAI
5. **Entrega do Relatório** - PDF personalizado + email com insights
6. **CTA para P02** - "Quer estruturar seu negócio? Experimente o Validador por R$ 29,90"

## Integrações

### Consome (Inputs)
- Nenhum (primeira interação do usuário)

### Gera (Outputs)
- **spec_perfil_empresario.json** → P02 (Validador)
- **Email capturado** → CRM/Mailchimp
- **Relatório PDF** → Email + Download

## Gatilho de Conversão

**Condição:** Usuário completou o diagnóstico

**Ação:** 
- Email automático com relatório
- CTA para P02 (Validador) com cupom de 50% OFF (R$ 14,95)
- Remarketing via pixel

**Meta:** 15% de conversão para P02 em 7 dias

## Módulos Principais

### 1. Módulo: Landing Page
- Componente: Hero Section
- Componente: Formulário de Captura
- Componente: Proof (depoimentos)

### 2. Módulo: Questionário Interativo
- Componente: Engine de Perguntas (CCE)
- Componente: Engine de Perguntas (Johari)
- Componente: Engine de Perguntas (Flow)
- Componente: Progress Bar

### 3. Módulo: Processamento IA
- Componente: Agent Análise CCE
- Componente: Agent Análise Johari
- Componente: Agent Análise Flow
- Componente: Agent Gerador de Relatório

### 4. Módulo: Entrega de Resultado
- Componente: Gerador de PDF
- Componente: Email Service
- Componente: CTA para P02

### 5. Módulo: CRM Integration
- Componente: Webhook para Mailchimp
- Componente: Tag de Segmentação
- Componente: Pixel de Remarketing

## Frameworks Utilizados

### CCE (Características do Comportamento Empreendedor)
- **Realização:** busca de oportunidades, persistência, correr riscos
- **Planejamento:** estabelecimento de metas, busca de informações
- **Poder:** independência, autoconfiança

### Johari Window
- **Arena Pública:** O que eu sei e outros sabem
- **Ponto Cego:** O que eu não sei mas outros sabem
- **Fachada:** O que eu sei mas outros não sabem
- **Desconhecido:** O que nem eu nem outros sabem

### Flow State
- **Ansiedade:** Alto desafio, baixa habilidade
- **Tédio:** Baixo desafio, alta habilidade
- **Flow:** Equilíbrio entre desafio e habilidade

## Tecnologias Sugeridas

- **Frontend:** Next.js + Tailwind CSS
- **Backend:** Python FastAPI
- **IA:** CrewAI com OpenAI/Claude
- **Database:** Supabase (PostgreSQL)
- **PDF:** ReportLab ou WeasyPrint
- **Email:** SendGrid ou Resend
- **Analytics:** PostHog ou Mixpanel

## KPIs Críticos

1. **Taxa de Captura:** % de visitantes que fornecem email
2. **Taxa de Conclusão:** % de usuários que completam o diagnóstico
3. **Taxa de Conversão para P02:** % que compram o Validador em 7 dias
4. **NPS do Relatório:** Satisfação com o diagnóstico

## Próximos Passos

Para estruturar este produto, siga os prompts de gradiente na ordem:

1. **../prompts/01-prompt-consolidar.md**
2. **../prompts/02-prompt-estruturar.md**
3. **../prompts/03-prompt-especificar-componentes.md**
4. **../prompts/04-prompt-especificar-elementos.md**
5. **../prompts/05-prompt-documentar.md**
