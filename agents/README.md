# Pack de Agentes — "Empresa de Software" para Claude Code

Este pack contém 6 subagentes do Claude Code que simulam um time de software completo,
pensados especificamente para o seu projeto de **extração de relatórios do banco Oracle**:

| Agente | Arquivo | Papel |
|---|---|---|
| **PO** | `po.md` | Product Owner — requisitos, histórias de usuário, priorização e escopo |
| **Arquiteto de Soluções** | `arquiteto-solucoes.md` | Desenho técnico, ADRs, diagramas, trade-offs |
| **DBA Oracle** | `dba-oracle.md` | SQL/PL-SQL, performance, modelagem, dicionário de dados |
| **CyberSecurity** | `cybersecurity.md` | Credenciais, SQL injection, LGPD, revisão de segurança |
| **Infra** | `infra.md` | Conectividade Oracle, deploy, agendamento, monitoramento |
| **QA/Tester** | `qa-tester.md` | Testes, validação de dados e documentação com prints de tela |

## Como instalar no Claude Code

Os agentes já estão organizados na estrutura de pastas que o Claude Code espera:

```
.claude/
  agents/
    po.md
    arquiteto-solucoes.md
    dba-oracle.md
    cybersecurity.md
    infra.md
    qa-tester.md
```

Você tem duas opções:

**Opção A — Agentes só para este projeto (recomendado)**
Copie a pasta `.claude/agents/` inteira para a raiz do seu projeto (onde você roda o
`claude` no terminal). Se o projeto já tiver uma pasta `.claude/agents/`, apenas copie
os arquivos `.md` para dentro dela.

**Opção B — Agentes disponíveis em todos os seus projetos**
Copie os arquivos `.md` para `~/.claude/agents/` (pasta do seu usuário), assim eles ficam
disponíveis em qualquer projeto que você abrir com o Claude Code.

Depois de copiar os arquivos, abra o Claude Code normalmente (`claude`) na pasta do
projeto. Os agentes aparecerão automaticamente disponíveis para uso — você pode chamá-los
pelo nome (ex: *"use o agente dba-oracle para otimizar essa query"*) ou deixar o Claude
Code delegar sozinho quando a tarefa combinar com a descrição do agente.

## Fluxo de trabalho sugerido

Para uma nova funcionalidade do relatório, a ordem natural de trabalho é:

1. **po** — esclarece o pedido de negócio e escreve a história de usuário com critérios
   de aceitação.
2. **arquiteto-solucoes** — desenha como a extração/relatório vai funcionar tecnicamente.
3. **dba-oracle** — escreve/otimiza as queries Oracle necessárias e documenta as tabelas.
4. **cybersecurity** — revisa credenciais, SQL injection, privilégios e dados sensíveis
   antes de liberar.
5. **infra** — prepara o ambiente, a conectividade com o Oracle e o agendamento de
   execução.
6. **qa-tester** — testa de ponta a ponta, valida os números contra o banco e documenta
   com prints de tela.

Você não precisa seguir a ordem à risca — pode chamar qualquer agente diretamente quando
já souber exatamente qual etapa precisa. O Claude Code também pode escolher o agente certo
automaticamente com base na descrição de cada um, então descrever bem o que você precisa
já ajuda bastante (ex: "essa query Oracle está lenta" aciona o `dba-oracle`; "revisa a
segurança dessa credencial" aciona o `cybersecurity`).

## Documentação gerada pelo time

Os agentes foram instruídos a manter a documentação organizada em uma pasta `docs/` no
seu projeto, por exemplo:

```
docs/
  requisitos.md              # PO
  arquitetura.md              # Arquiteto
  adr/                         # Arquiteto (decisões técnicas)
  dicionario-dados.md         # DBA
  infra.md                     # Infra
  screenshots/                 # QA (prints de evidência)
  testes/                      # QA (relatórios de teste)
```

Isso mantém uma fonte única de verdade entre os agentes e facilita retomar o trabalho
depois, mesmo em uma sessão nova do Claude Code.

## Personalização

Cada arquivo `.md` tem um cabeçalho (frontmatter) no topo com `name`, `description`,
`tools` e `model`. Você pode:
- Ajustar `tools` para restringir ou liberar mais ferramentas para um agente.
- Trocar `model` (ex: `opus`, `sonnet`, `haiku`) se quiser mais ou menos "poder" de
  raciocínio em um agente específico — por exemplo, usar um modelo mais forte no
  `arquiteto-solucoes` e um mais leve no `qa-tester` para tarefas repetitivas.
- Editar o corpo do arquivo (o "system prompt" do agente) para refletir convenções
  específicas da sua empresa (nome de schemas Oracle, padrões de nomenclatura,
  ferramentas de BI usadas etc.).
