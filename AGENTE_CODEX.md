# Equipe de agentes Codex do Habblaud

O projeto inclui seis perfis personalizados em `.codex/agents/`:

| Agente | Função | Modelo configurado |
|---|---|---|
| `dia_implementacao` | Marina Alves, Engenheira de Implementação | GPT-6 Luna, esforço médio |
| `dia_analise` | Rafael Costa, Analista de Diagnóstico | GPT-6 Luna, esforço alto |
| `noite_manutencao` | Camila Rocha, Engenheira de Manutenção | GPT-6 Luna, esforço médio |
| `noite_documentacao` | Bruno Lima, Especialista em Documentação | GPT-6 Luna, esforço médio |
| `gerente` | Helena Martins, Gerente de Operações | GPT-6.1 Sol, esforço médio |
| `supervisor` | Marcelo Duarte, Supervisor de Qualidade | GPT-6.1 Sol, esforço alto |

## Como usar

Abra a raiz do projeto no Codex. Os perfis ficam disponíveis conforme o suporte da versão/interface do Codex para agentes personalizados. Exemplos de pedido:

- “Gerente, investigue esse bug, escolha um executor e encaminhe a entrega para o supervisor revisar.”
- “Use `dia_implementacao` para corrigir este problema; depois peça ao `supervisor` uma revisão somente de leitura.”
- “Use `noite_documentacao` para alinhar a documentação e as traduções a esta mudança.”

A configuração `.codex/config.toml` permite até oito execuções paralelas e define Luna/esforço médio como padrão. O gerente começa com um executor e pode aumentar as instâncias por área quando o volume e a independência das tarefas justificarem. Deve reduzir a equipe quando o pico passar e evitar análises e revisões duplicadas.

## Turnos e execução

“Dia” e “noite” são nomes de perfis e divisão de responsabilidades. Eles **não iniciam agentes automaticamente por horário**, não mantêm processos acordados e não criam tarefas agendadas. Para executar um perfil, abra uma sessão Codex e solicite a tarefa. O Habblaud pode mostrar sessões que estiverem realmente abertas no Codex. As sessões do mesmo projeto aparecem na mesma sala; o Habblaud cria salas a partir dos diretórios de projeto ativos.

Os seis perfis são configurações, não seis processos ativos. Eles não gastam uso enquanto estão parados. Quando usados, as execuções dos agentes podem consumir a franquia/créditos compartilhados do seu plano. O Codex disponibiliza uso e saldo nas Configurações/painel de uso; confira esse painel para acompanhar a cota e a renovação atuais.

## Regras preservadas

Todos os agentes devem seguir `AGENTS.md` e `CONTRIBUTING.md`. Textos visíveis precisam de `tr(...)` e tradução em `shared/locales/`; mudanças funcionais/visíveis entram em “Não lançado” no `CHANGELOG.md`. Antes de alterar `shared/world/` ou `server/world/`, leia `shared/world/README.md` e preserve dados verdadeiros.
