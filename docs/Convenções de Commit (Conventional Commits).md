# Convenções de Commit (Conventional Commits)

O padrão Conventional Commits é uma convenção leve sobre mensagens de commit. Ele fornece um conjunto fácil de regras para criar um histórico de commit explícito, o que facilita a criação de ferramentas automatizadas.

## Formato

O formato da mensagem de commit deve ser:

```
<tipo>[escopo opcional]: <descrição>

[corpo opcional]

[rodapé opcional]
```

## Tipos Comuns

| Tipo | Descrição | Exemplo |
| :--- | :--- | :--- |
| **feat** | Uma nova funcionalidade (corresponde a `MINOR` no versionamento semântico). | `feat: adiciona botão de login` |
| **fix** | Uma correção de bug (corresponde a `PATCH` no versionamento semântico). | `fix: corrige erro de acentuação no título` |
| **docs** | Mudanças apenas na documentação. | `docs: atualiza README com novos exercícios` |
| **style** | Mudanças que não afetam o significado do código (espaços em branco, formatação, ponto e vírgula ausente, etc.). | `style: formata código com Prettier` |
| **refactor** | Uma mudança de código que não corrige um bug nem adiciona um recurso. | `refactor: extrai lógica de autenticação para um hook` |
| **test** | Adicionando testes ausentes ou corrigindo testes existentes. | `test: adiciona teste unitário para função de soma` |
| **chore** | Outras mudanças que não modificam arquivos de produção ou de teste. | `chore: atualiza dependência do React` |

## Quebra de Mudança (BREAKING CHANGE)

Commits que introduzem uma quebra de mudança devem incluir `BREAKING CHANGE:` no corpo ou rodapé, ou adicionar um `!` após o tipo/escopo.

**Exemplo:**
```
feat!: remove suporte para Node 10

BREAKING CHANGE: O Node 10 não é mais suportado.
```
