# 🚀 Treinamento Prático de Git

[![Status do Treinamento](https://img.shields.io/badge/Status-Em%20Andamento-brightgreen)](https://github.com/sua-empresa/treinamento-git/issues)
[![Nível](https://img.shields.io/badge/Nível-Iniciante%20a%20Avançado-blue)](README.md#níveis)

Bem-vindo ao repositório de treinamento de Git! 🎯

Este repositório foi criado para ajudar todos a se familiarizarem com o Git de forma **prática e colaborativa**. A ideia é que você faça os exercícios passo a passo, trabalhando em branches, fazendo commits, abrindo Pull Requests e revisando o trabalho dos colegas.


## 🧭 Sumário

- [Por que Git?](#por-que-git)
- [Como Funciona Este Treinamento](#como-funciona-este-treinamento)
- [Pré-requisitos](#pré-requisitos)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [📋 Exercícios](#exercícios)
  - [Exercício 1: Seu Primeiro Commit 🆕](#exercício-1-seu-primeiro-commit-🆕)
  - [Exercício 2: Trabalhando com Branches 🌿](#exercício-2-trabalhando-com-branches-🌿)
  - [Exercício 3: Fazendo Code Review 👀](#exercício-3-fazendo-code-review-👀)
  - [Exercício 4: Resolvendo Conflitos 🔄](#exercício-4-resolvendo-conflitos-🔄)
  - [Exercício 5: Explorando o Histórico 📜](#exercício-5-explorando-o-histórico-📜)
  - [Exercício 6: Desfazendo Mudanças ⏪](#exercício-6-desfazendo-mudanças-⏪)
  - [Exercício 7: Padrão de Commit (Conventional Commits) 🏷️](#exercício-7-padrão-de-commit-conventional-commits-🏷️)
- [❓ Dúvidas Frequentes](#dúvidas-frequentes)
- [🚀 Próximos Passos](#próximos-passos)

---

## Por que Git?

O Git é a ferramenta essencial para o desenvolvimento moderno. Ele nos permite:

- **Controle de Versão:** Rastrear cada mudança em nossos projetos.
- **Colaboração Segura:** Trabalhar em paralelo sem sobrescrever o trabalho dos colegas.
- **Histórico Completo:** Saber exatamente quem fez o quê e quando.
- **Fluxo de Trabalho Eficiente:** Facilitar o trabalho remoto e a integração contínua.

## Como Funciona Este Treinamento

Siga estas diretrizes para um aprendizado eficaz:

1.  **Leia com Atenção:** Entenda o objetivo de cada exercício.
2.  **Pratique no Terminal:** Execute os comandos na sua máquina.
3.  **Use Branches Pessoais:** Crie branches com seu nome (`feature/seu-nome-ex1`) para evitar conflitos desnecessários.
4.  **Abra Pull Requests (PRs):** Compartilhe seu trabalho e peça revisão.
5.  **Revise Colegas:** A revisão de PRs é crucial para o aprendizado!
6.  **Confirme na Issue:** Comente na Issue correspondente quando finalizar o exercício.

## Pré-requisitos

Certifique-se de ter o seguinte configurado:

- **Git** instalado na sua máquina (versão 2.0+).
- **Conta no GitHub** (ou plataforma de hospedagem Git utilizada pela empresa).
- Um **editor de texto** de sua preferência (VS Code, Sublime, etc.).

## Estrutura do Repositório

```
treinamento-git/
├── README.md                 # Você está aqui!
├── exercicios/               # Arquivos para os exercícios
│   ├── lista-de-filmes.md    # Para exercício de conflito
│   └── seu-arquivo.md        # Você criará o seu
├── docs/                     # Documentação e dicas
│   ├── dicas-git.md          # Dicas práticas de Git
│   └── convencoes-commit.md  # Padrões para mensagens de commit
└── exemplos/                 # Exemplos de uso do Git
```

---

# 📋 Exercícios

## Exercício 1: Seu Primeiro Commit 🆕

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 10-15 minutos |
| **Objetivo** | Clonar, criar arquivo, commit e push. |

**Passos:**

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/sua-empresa/treinamento-git.git
    cd treinamento-git
    ```

2.  **Crie seu arquivo de apresentação:**
    - Vá para a pasta `exercicios/`.
    - Crie um arquivo com seu nome: `exercicios/seu-nome.md`.
    - Escreva o seguinte conteúdo (em Markdown):
    ```markdown
    # Apresentação - Seu Nome

    **Cargo:** Seu cargo na empresa/universidade

    **O que espero aprender com Git:**
    - Uma frase sobre suas expectativas

    **Data:** 25/11/2025
    ```

3.  **Faça o commit e push:**
    ```bash
    git add exercicios/seu-nome.md
    git commit -m "feat: adiciona apresentação de seu-nome"
    git push origin main
    ```

4.  **Confirme o exercício:**
    - Vá para a **Issue #1**.
    - Comente: `✅ Exercício 1 concluído - Meu arquivo: exercicios/seu-nome.md`

> **Dica:** Se o push falhar, configure seu nome e email no Git:
> ```bash
> git config --global user.name "Seu Nome"
> git config --global user.email "seu.email@empresa.com"
> ```

## Exercício 2: Trabalhando com Branches 🌿

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15-20 minutos |
| **Objetivo** | Criar branch, trabalhar nela e abrir Pull Request. |

**Passos:**

1.  **Atualize sua cópia local:**
    ```bash
    git pull origin main
    ```

2.  **Crie e mude para uma nova branch:**
    ```bash
    git checkout -b feature/bio-seu-nome
    # (Substitua "seu-nome" pelo seu nome real)
    ```

3.  **Crie sua bio:**
    - Na pasta `exercicios/`, crie `bio-seu-nome.md`.
    - Escreva uma bio curta (3-5 linhas):
    ```markdown
    # Bio - Seu Nome

    Olá! Sou estudante no Laboratório ------ da Universidade ------- .

    **Habilidades principais:**
    - Linguagem/framework que você usa
    - Ferramentas que domina

    **Projetos recentes:**
    - Um projeto que você trabalhou

    **Fun fact:** Algo interessante sobre você!
    ```

4.  **Commit e push da branch:**
    ```bash
    git add exercicios/bio-seu-nome.md
    git commit -m "feat: adiciona bio pessoal de seu-nome"
    git push -u origin feature/bio-seu-nome
    ```

5.  **Crie o Pull Request (PR):**
    - Vá para o GitHub.
    - Clique em **"Compare & pull request"** (aparecerá automaticamente).
    - Na descrição do PR, use o seguinte template:
    ```markdown
    ## O que foi feito
    Adicionei minha bio pessoal no arquivo `bio-seu-nome.md`

    ## Como testar
    1. Abra o arquivo `exercicios/bio-seu-nome.md`
    2. Leia minha apresentação :)

    ## Checklist
    - [x] Criei branch com meu nome
    - [x] Escrevi mensagem de commit clara
    - [x] Testei localmente
    ```

6.  **Confirme o exercício:**
    - Comente na **Issue #2**: `✅ Exercício 2 concluído - Link do meu PR: [link]`

> **Dica:** O `-u` no push cria a conexão entre sua branch local e remota, facilitando pushes futuros.

## Exercício 3: Fazendo Code Review 👀

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 10-15 minutos |
| **Objetivo** | Aprender a revisar o trabalho dos colegas. |

**Passos:**

1.  **Encontre um PR para revisar:**
    - Vá para a aba **Pull Requests** do repositório.
    - Escolha um PR **aberto** de um colega (não o seu!).
    - Clique no PR para abrir.

2.  **Faça a revisão:**
    - Leia os arquivos alterados.
    - **Comente pelo menos 1 linha:** Clique no `+` ao lado de uma linha e escreva um comentário (elogio, sugestão, pergunta).
    - **Exemplo de elogio:** "Boa explicação na bio! Ficou bem estruturado 👍"
    - **Exemplo de sugestão:** "Que tal adicionar um cargo novo que você obteve?"

3.  **Faça uma review geral:**
    - No final da página, escolha:
        - **Approve** (se estiver tudo ok)
        - **Request changes** (se precisar de ajustes)
        - **Comment** (se tiver sugestões mas não bloquear o merge)

4.  **Seja construtivo:**
    - Sempre comece com algo positivo.
    - Seja específico nas sugestões.
    - Marque a pessoa com `@nome-do-colega` se precisar de resposta.

5.  **Confirme o exercício:**
    - Comente na **Issue #3**:
    ```markdown
    ✅ Exercício 3 concluído

    Revisei o PR de: @nome-do-colega
    Uma coisa que aprendi: [escreva algo que você descobriu no processo]
    ```

> **Dica:** Code review é uma das partes mais importantes do Git! É onde garantimos qualidade e compartilhamos conhecimento.

## Exercício 4: Resolvendo Conflitos 🔄

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 20-25 minutos |
| **Objetivo** | Lidar com conflitos de merge de forma prática. |

**Preparação (Admin):**

Edite o arquivo `exercicios/lista-de-filmes.md` com alguns filmes iniciais:

```markdown
# Lista de Filmes Favoritos

## Filmes já adicionados:
- Matrix (1999) - Ficção Científica
- O Poderoso Chefão (1972) - Drama
- Lua de Cristal (1990) - Comédia
```

**Passos:**

1.  **Atualize a `main`:**
    ```bash
    git checkout main
    git pull origin main
    ```

2.  **Crie uma nova branch:**
    ```bash
    git checkout -b feature/filmes-seu-nome
    ```

3.  **Edite a lista de filmes:**
    - Abra `exercicios/lista-de-filmes.md`.
    - **Adicione 2 filmes seus** na seção "Filmes já adicionados", seguindo o padrão:
    ```markdown
    - Seu Filme 1 (ano) - Gênero
    - Seu Filme 2 (ano) - Gênero
    ```
    > **Importante:** Edite a mesma linha ou próximo dela onde outros colegas vão editar para **criar conflito de propósito**.

4.  **Tente fazer merge com a `main` (para simular conflito):**
    ```bash
    git add exercicios/lista-de-filmes.md
    git commit -m "feat: adiciona 2 filmes favoritos de seu-nome"

    # Agora simule o conflito tentando merge com main atualizada
    git checkout main
    git pull origin main  # (pode ter novos filmes de outros colegas)
    git checkout feature/filmes-seu-nome
    git merge main
    ```

5.  **Se der conflito (deveria dar!), resolva:**
    - O Git mostrará: `CONFLICT (content): Merge conflict in exercicios/lista-de-filmes.md`
    - Abra o arquivo `lista-de-filmes.md` no seu editor. Você verá marcadores de conflito:
    ```markdown
    <<<<<<< HEAD
    - Seu Filme 1 (ano) - Gênero
    =======
    - Filme Do Colega (ano) - Gênero
    >>>>>>> feature/filmes-colega
    ```
    - **Resolva o conflito:** Escolha o que manter ou combine. **Mantenha ambos** para este exercício:
    ```markdown
    - Seu Filme 1 (ano) - Gênero
    - Filme Do Colega (ano) - Gênero
    ```
    - **Remova TODOS os marcadores** `<<<<<<<`, `=======`, `>>>>>>>`.
    - Salve o arquivo.

6.  **Finalize o merge e faça o push:**
    ```bash
    git add exercicios/lista-de-filmes.md
    git commit -m "fix: resolve conflito na lista de filmes"
    git push -u origin feature/filmes-seu-nome
    ```

7.  **Abra o Pull Request** e na descrição mencione:
    ```markdown
    ## Conflito resolvido
    Tive que resolver conflito com os filmes do @colega. Mantive ambos!
    ```

8.  **Confirme o exercício:**
    - Na **Issue #4**, comente:
    ```markdown
    ✅ Exercício 4 concluído

    Tive conflito? Sim/Não
    Como resolvi: [descreva brevemente]
    Link do PR: [link]
    ```

> **Dica:** Conflitos são normais e esperados! O importante é saber resolvê-los sem pânico.

## Exercício 5: Explorando o Histórico 📜

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15 minutos |
| **Objetivo** | Aprender a usar `git log` e `git blame` para entender mudanças. |

**Preparação (Admin):**

Crie o arquivo `docs/dicas-git.md` com algumas dicas iniciais:

```markdown
# Dicas Práticas de Git

## Dicas básicas
- Sempre faça `git pull` antes de começar a trabalhar
- Use mensagens de commit descritivas
- Crie branches para cada funcionalidade

## Comandos úteis
- `git status`: Veja o estado atual
- `git diff`: Veja diferenças nos arquivos
```

**Passos:**

1.  **Explore o histórico:**
    ```bash
    # Veja o histórico completo do repositório
    git log --oneline

    # Veja histórico só do arquivo de dicas
    git log --oneline docs/dicas-git.md

    # Veja quem alterou cada linha (blame)
    git blame docs/dicas-git.md
    ```

2.  **Crie uma branch para adicionar sua dica:**
    ```bash
    git checkout -b feature/dica-seu-nome
    ```

3.  **Adicione UMA dica nova** no arquivo `docs/dicas-git.md`:
    - Escolha uma seção (ou crie uma nova).
    - Exemplo de dica que você pode adicionar:
    ```markdown
    ## Branches
    - Use nomes descritivos: `feature/nova-funcionalidade`
    - Delete branches após merge para manter limpo
    ```

4.  **Faça o commit com mensagem específica:**
    ```bash
    git add docs/dicas-git.md
    git commit -m "docs: adiciona dicas sobre boas práticas de branch"
    git push -u origin feature/dica-seu-nome
    ```

5.  **No Pull Request, mencione:**
    ```markdown
    ## O que mudou
    Adicionei uma dica sobre boas práticas de branch. Usei o `git log` para ver o histórico do arquivo antes de editar.
    ```

6.  **Confirme o exercício:**
    - Na **Issue #5**, comente: `✅ Exercício 5 concluído - Link do PR: [link]`

## Exercício 6: Desfazendo Mudanças ⏪

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15-20 minutos |
| **Objetivo** | Aprender a usar `git reset` e `git revert`. |

**Passos:**

1.  **Crie uma branch de teste:**
    ```bash
    git checkout -b feature/desfazer-seu-nome
    ```

2.  **Faça um commit "ruim" (simulado):**
    - Crie um arquivo temporário: `touch lixo.txt`
    - Faça o commit:
    ```bash
    git add lixo.txt
    git commit -m "feat: commit de teste que quero desfazer"
    ```

3.  **Desfaça o commit localmente (`git reset`):**
    - Use `git log --oneline` para pegar o ID do commit **anterior** ao "ruim".
    - Desfaça o último commit, mantendo as mudanças no seu diretório (soft):
    ```bash
    git reset HEAD~1
    # OU
    git reset --soft [ID do commit anterior]
    ```
    - O arquivo `lixo.txt` ainda estará lá, mas o commit sumiu.

4.  **Faça um commit "bom" e push:**
    - Remova o arquivo `lixo.txt`: `rm lixo.txt`
    - Faça o commit corrigido:
    ```bash
    git add .
    git commit -m "fix: remove arquivo de teste"
    git push -u origin feature/desfazer-seu-nome
    ```

5.  **Simule um commit que já foi para a `main` (`git revert`):**
    - **Atenção:** Nunca use `git reset` em commits que já foram para o repositório remoto (como a `main`).
    - Vamos simular que o commit "fix: remove arquivo de teste" já foi mergeado.
    - Faça uma nova mudança (ex: adicione uma linha no seu `seu-nome.md`).
    - Faça o commit: `git commit -m "feat: adicao de linha extra"`
    - Use `git log --oneline` para pegar o ID desse commit.
    - **Reverta o commit:**
    ```bash
    git revert [ID do commit]
    ```
    - O Git abrirá um editor para você confirmar a mensagem de commit de reversão. Salve e feche.

6.  **Push e PR:**
    ```bash
    git push
    ```
    - No PR, explique a diferença entre `git reset` (para commits locais) e `git revert` (para commits públicos).

7.  **Confirme o exercício:**
    - Na **Issue #6**, comente:
    ```markdown
    ✅ Exercício 6 concluído

    Usei `git reset --soft` para: [explique]
    Usei `git revert` para: [explique]
    Link do PR: [link]
    ```

## Exercício 7: Padrão de Commit (Conventional Commits) 🏷️

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 10-15 minutos |
| **Objetivo** | Praticar o padrão de mensagens de commit (Conventional Commits). |

**Passos:**

1.  **Leia as convenções:**
    - Consulte o arquivo `docs/convencoes-commit.md` (ou a documentação).
    - Tipos comuns: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

2.  **Crie uma branch:**
    ```bash
    git checkout -b feature/padrao-commit-seu-nome
    ```

3.  **Faça uma pequena melhoria:**
    - Exemplo: melhore uma frase no seu arquivo de bio (`exercicios/bio-seu-nome.md`).

4.  **Commit seguindo o padrão:**
    - Use o tipo `docs` ou `fix`:
    ```bash
    git add exercicios/bio-seu-nome.md
    git commit -m "docs: melhora redação na bio pessoal"
    # OU
    git commit -m "fix: corrige acentuação em apresentação"
    ```

5.  **Corpo do commit (opcional, mas bom praticar):**
    - Adicione detalhes no corpo do commit:
    ```bash
    git commit -m "docs: melhora redação na bio pessoal

    - Corrige frases incompletas
    - Adiciona pontuação faltante
    - Torna o texto mais fluido para leitura"
    ```

6.  **Push e PR:**
    ```bash
    git push -u origin feature/padrao-commit-seu-nome
    ```
    - No PR, mostre sua mensagem de commit como exemplo.

7.  **Confirme o exercício:**
    - Na **Issue #7**:
    ```markdown
    ✅ Exercício 7 concluído

    Tipo de commit usado: [ex: docs]
    Mensagem completa: [cole sua mensagem]
    Por que escolhi esse tipo: [explicação]
    Link do PR: [link]
    ```

> **Dica:** Ferramentas como Commitizen ou hooks do Husky podem forçar esse padrão automaticamente!

---

## ❓ Dúvidas Frequentes

| Pergunta | Resposta |
| :--- | :--- |
| **"Deu erro no push, o que faço?"** | 1. Verifique se está na branch certa: `git branch`. 2. Faça `git pull` antes: pode ter conflito. 3. Configure suas credenciais GitHub. |
| **"Como vejo todas as branches?"** | Use `git branch -a` (mostra locais e remotas). |
| **"Quero deletar uma branch local depois do merge?"** | Use `git branch -d nome-da-branch`. |
| **"Onde vejo o status de todos?"** | Aba Issues (comentários de conclusão), Aba Pull Requests (PRs abertos) e esta tabela no README. |

---

## 🚀 Próximos Passos

Depois de completar todos os exercícios, continue aprimorando suas habilidades:

- **Pratique no Dia a Dia:** Use Git nos projetos reais da universidade ou da empresa.
- **Participe de Code Reviews:** Revise pelo menos 1 PR por semana.
- **Ensine um Colega:** Explique o que aprendeu para alguém.
- **Contribua com Mais Exercícios:** Tem ideias? Abra uma issue!

### Recursos Extras:

- [Documentação oficial Git](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Try Git interativo](https://try.github.io/)
