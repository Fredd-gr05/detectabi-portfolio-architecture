# detectabi-portfolio-architecture

Sistema estruturado de prompts para arquitetura de produtos DetectaBI.

## Gradientes de Trabalho

### Gradiente de Profundidade
1. **CONSOLIDAR**: Coleta e unificação de informações.
2. **ESTRUTURAR**: Organização lógica e hierárquica.
3. **ESPECIFICAR**: Detalhamento técnico e funcional.
4. **DOCUMENTAR**: Formalização e registro final.

### Gradiente de Decomposição
- PRODUTO → MÓDULO → COMPONENTE → ELEMENTO → ATRIBUTO

## Portfólio de Produtos (Funil de Vendas)

- **R$ 0 Diagnóstico**: Porta de entrada e análise inicial.
- **R$ 19,90 Validador**: Validação rápida de hipóteses.
- **R$ 497/mês Starter**: Dashboard e BI inicial.
- **R$ 1.497/mês Professional**: BI avançado e métricas complexas.
- **R$ 2.997-4.997/mês BI Agents**: Agentes inteligentes (Fase 2).

---
*Foco inicial em Dashboards (Produto Principal), Agentes em Fase 2.*


## Backlog de Frameworks

Este repositório contém um **sistema de backlog** para gerenciar frameworks candidatos à integração no portfólio DetectaBI.

### Estrutura

```
/backlog/
  ├── frameworks-candidates.md    # Lista de frameworks aguardando validação
  ├── frameworks-rejected.md      # Histórico de frameworks rejeitados
  └── templates/
      └── framework-analysis-template.md  # Template para análise completa
```

### Fluxo de Trabalho

1. **Sugestão**: Novos frameworks são adicionados em `frameworks-candidates.md` com status 🟡 PENDENTE
2. **Análise**: Framework é promovido para 🔵 EM ANÁLISE e avaliado usando o template
3. **Decisão**:
   - **Aprovado** (🟢): Movido para ROADMAP e entra em desenvolvimento
   - **Rejeitado** (🔴): Documentado em `frameworks-rejected.md` com justificativa

### FIT Score

Cada framework recebe uma pontuação de 0-100 baseada em 5 critérios:

| Critério | Peso |
|----------|------|
| Compatibilidade Científica/Acadêmica | 20% |
| Sinergia com Produtos Existentes | 20% |
| Complexidade de Implementação | 20% |
| Impacto no Modelo de Negócio | 20% |
| Alinhamento com Visão DetectaBI | 20% |

### Como Usar

1. **Adicionar novo framework**: Copie o template rápido em `frameworks-candidates.md`
2. **Análise detalhada**: Use `templates/framework-analysis-template.md` para avaliação completa
3. **Acompanhar status**: Consulte `frameworks-candidates.md` para ver frameworks em cada estágio

### Benefícios

- ✅ **Foco no produto atual**: Não interrompe desenvolvimento em andamento
- ✅ **Registro histórico**: Todas decisões documentadas no Git
- ✅ **Priorização clara**: FIT Score + prioridade de negócio
- ✅ **Transparência**: Equipe visualiza próximos frameworks a serem avaliados

---

**Frameworks atualmente no backlog**: 1 (Escala de Bem-estar Psicológico de Ryff)
