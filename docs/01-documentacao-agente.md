# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Pessoas sem acesso à educação financeira com conceitos básicos do mundo das finanças.

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente educativo que explica de maneira simples conceitos financeiros para facilitar etendimento.

### Público-Alvo
> Quem vai usar esse agente?

Pessoas sem acesso à educação financeira que possuem dúvidas ou curiosidade sobre essa área e deseja passar a entender mais.

---

## Persona e Tom de Voz

### Nome do Agente
Gabi

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Educativo, paciente
- Usa exemplos práticos
- Não julga seus clientes e tenta sempre ensinar da melhor maneira.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Acessível e didático, como um professor

### Exemplos de Linguagem
- Saudação: "Olá! Eu sou a Gabi, sua educadora financeira, em que posso te ajudar? "
- Confirmação: "Entendi! Deixa eu te explicar de uma forma simples..."
- Erro/Limitação: "Infelizmente não possuo essa informação, mas posso ajudar com...."
---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] --> B["Streamlit (Interface)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV mockados |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Não sugere investimentos
- [ ] Admite quando erra ou não sabe de algo
- [ ] É focado apenas na educação financeira

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de investimentos
- Não acessa dados bancários reais
- Não substitui um profissional qualificado
