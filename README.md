# 🚀 Treinamento Prático de Git

[![Status do Treinamento](https://img.shields.io/badge/Status-Em%20Andamento-brightgreen)](https://github.com/sua-empresa/treinamento-git/issues)
[![Nível](https://img.shields.io/badge/Nível-Iniciante%20a%20Avançado-blue)](README.md#níveis)

Bem-vindo ao repositório de treinamento de Git! 🎯

Este repositório foi criado para ajudar todos a se familiarizarem com o Git de forma **prática e colaborativa**. A ideia é que você faça os exercícios passo a passo, trabalhando em branches, fazendo commits, abrindo Pull Requests e revisando o trabalho dos colegas.

---

## 🧭 Sumário

- [Por que Git?](#por-que-git)
- [Conceitos Fundamentais](#conceitos-fundamentais)
- [Como Funciona Este Treinamento](#como-funciona-este-treinamento)
- [Pré-requisitos](#pré-requisitos)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [📋 Exercícios](#-exercícios)
  - [Exercício 1: Seu Primeiro Commit 🆕](#exercício-1-seu-primeiro-commit-)
  - [Exercício 2: Trabalhando com Branches 🌿](#exercício-2-trabalhando-com-branches-)
  - [Exercício 3: Fazendo Code Review 👀](#exercício-3-fazendo-code-review-)
  - [Exercício 4: Resolvendo Conflitos 🔄](#exercício-4-resolvendo-conflitos-)
  - [Exercício 5: Explorando o Histórico 📜](#exercício-5-explorando-o-histórico-)
  - [Exercício 6: Desfazendo Mudanças ⏪](#exercício-6-desfazendo-mudanças-)
  - [Exercício 7: Padrão de Commit (Conventional Commits) 🏷️](#exercício-7-padrão-de-commit-conventional-commits-)
- [❓ Dúvidas Frequentes](#-dúvidas-frequentes)
- [🚀 Próximos Passos](#-próximos-passos)

---

## Por que Git?

Imagine que você está escrevendo um trabalho importante e decide guardar cópias a cada avanço: `trabalho_v1.docx`, `trabalho_v2.docx`, `trabalho_FINAL.docx`, `trabalho_FINAL_de_verdade.docx`... Soa familiar? O Git resolve exatamente esse problema, mas de forma inteligente.

O Git é a ferramenta de **controle de versão** mais usada no mundo. Com ele você consegue:

- **Rastrear mudanças:** Ver exatamente o que foi alterado, por quem e quando.
- **Trabalhar em paralelo:** Você e seus colegas podem mexer no mesmo projeto simultaneamente, sem sobrescrever o trabalho um do outro.
- **Voltar no tempo:** Se algo quebrar, é possível restaurar qualquer versão anterior do projeto com um único comando.
- **Experimentar com segurança:** Crie um ambiente isolado (uma *branch*) para testar novas ideias sem afetar o código principal.
- **Colaborar com eficiência:** Facilita revisões de código, integração contínua e fluxos de trabalho em equipe.

---

## Conceitos Fundamentais

Antes de colocar a mão na massa, entender esses conceitos vai fazer toda a diferença. Não pule essa seção!

### 📦 Repositório (repo)

É a "pasta inteligente" onde o Git armazena todo o histórico do projeto. Existe em dois lugares:

- **Local:** Na sua máquina (`git clone` cria uma cópia).
- **Remoto:** No servidor (GitHub, GitLab, etc.), acessível pela equipe.

### 🎭 Os três estados de um arquivo

Todo arquivo no Git pode estar em um destes três estados:

```
[Diretório de Trabalho]  →  git add  →  [Staging Area]  →  git commit  →  [Repositório]
  (você edita aqui)                    (área de preparo)                  (histórico salvo)
```

1. **Working Directory (Diretório de Trabalho):** Onde você edita os arquivos normalmente.
2. **Staging Area (Área de Preparo / Index):** Um "rascunho" do próximo commit. Com `git add` você escolhe quais mudanças vão entrar no próximo commit.
3. **Repository (Repositório):** O histórico permanente. `git commit` confirma o que estava na Staging Area.

> 💡 **Por que a Staging Area existe?** Ela dá controle granular. Você pode ter mudado 5 arquivos, mas fazer 2 commits separados, cada um com mudanças relacionadas, deixando o histórico organizado.

### 🌿 Branch (Ramo)

Uma branch é uma linha de desenvolvimento independente. Pense nela como uma cópia paralela do projeto onde você pode trabalhar livremente sem afetar o código principal.

```
main:      A --- B --- C --- D (código estável)
                  \
feature:           E --- F    (sua nova funcionalidade)
```

Quando a funcionalidade estiver pronta, você faz o **merge** (fusão) de volta para a `main`.

### 💾 Commit

Um commit é um "snapshot" (foto) do estado do projeto em um determinado momento. Cada commit tem:
- Um **ID único** (hash SHA-1, ex: `a3f9c2d`)
- Uma **mensagem** descrevendo o que mudou
- Um **autor** e uma **data/hora**
- Uma referência ao commit anterior (formando o histórico)

### 🔗 HEAD

`HEAD` é um ponteiro que indica em qual commit você está agora. Normalmente aponta para o último commit da branch atual. Quando você vê `HEAD~1`, significa "o commit anterior ao atual".

### 🔀 Merge e Pull Request (PR)

- **Merge:** Operação de unir duas branches. O Git tenta combinar as mudanças automaticamente.
- **Pull Request (PR):** No GitHub, é o pedido formal para fazer o merge de uma branch na outra. É onde acontece a revisão de código antes de integrar as mudanças.

### ⚡ Fluxo Básico do Git

O fluxo que você vai usar no dia a dia:

```bash
git pull origin main              # 1. Baixa as mudanças mais recentes
git checkout -b feature/minha-tarefa  # 2. Cria uma branch para trabalhar
# ... edita os arquivos ...
git status                        # 3. Verifica o que mudou
git add arquivo.txt               # 4. Prepara as mudanças
git commit -m "feat: descrição"   # 5. Salva um snapshot
git push origin feature/minha-tarefa  # 6. Envia para o servidor
# 7. Abre Pull Request no GitHub
```

---

## Como Funciona Este Treinamento

Siga estas diretrizes para um aprendizado eficaz:

1. **Leia os conceitos primeiro:** A seção acima vai tornar cada comando mais fácil de entender.
2. **Pratique no Terminal:** Execute os comandos na sua máquina — ler sem praticar não fixa o conteúdo.
3. **Use Branches Pessoais:** Crie branches com seu nome (`feature/seu-nome-ex1`) para evitar conflitos desnecessários.
4. **Abra Pull Requests (PRs):** Compartilhe seu trabalho e peça revisão.
5. **Revise Colegas:** A revisão de PRs é tão importante quanto escrever código!
6. **Confirme na Issue:** Comente na Issue correspondente quando finalizar cada exercício.

---

## Pré-requisitos

Certifique-se de ter o seguinte configurado **antes** de começar:

- **Git** instalado na sua máquina (versão 2.0+).
  - Verifique com: `git --version`
  - Download em: https://git-scm.com/downloads
- **Conta no GitHub** (ou na plataforma de hospedagem utilizada pela equipe).
- Um **editor de texto** de sua preferência (VS Code, Sublime, Vim, etc.).
- **Configuração inicial do Git** — execute uma única vez na sua máquina:
  ```bash
  git config --global user.name "Seu Nome Completo"
  git config --global user.email "seu.email@empresa.com"
  ```
  > Esses dados aparecerão em todos os seus commits. Use o mesmo e-mail da sua conta no GitHub.

---

## Estrutura do Repositório

```
treinamento-git/
├── README.md                 # Você está aqui!
├── exercicios/               # Arquivos para os exercícios
│   ├── lista-de-filmes.md    # Usado no exercício de conflito
│   └── seu-arquivo.md        # Você criará o seu
├── docs/                     # Documentação e dicas
│   ├── dicas-git.md          # Dicas práticas de Git
│   └── convencoes-commit.md  # Padrões para mensagens de commit
└── exemplos/                 # Exemplos de uso do Git
```

---

# 📋 Exercícios

> **Sobre os exercícios:** Cada exercício foca em um conceito. Leia o objetivo antes de começar e, ao final, reflita sobre o que aprendeu. O objetivo não é apenas "executar os comandos", mas entender o porquê de cada um.

---

## Exercício 1: Seu Primeiro Commit 🆕

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15-20 minutos |
| **Objetivo** | Clonar o repositório, criar uma branch pessoal, fazer seu primeiro commit e abrir um PR. |
| **Conceitos praticados** | `clone`, `checkout -b`, `add`, `commit`, `push`, Pull Request |

### O que você vai aprender

Neste exercício você vai percorrer o fluxo completo pela primeira vez: clonar o repositório remoto, criar sua branch, adicionar um arquivo, registrar as mudanças com um commit e enviar tudo para o servidor.

### Passos

**1. Clone o repositório:**

`git clone` cria uma cópia completa do repositório remoto na sua máquina, incluindo todo o histórico.

```bash
git clone https://github.com/Word-aid/Aprendendo-o-Git.git
cd Aprendendo-o-Git
```

**2. Verifique o estado inicial:**

Antes de qualquer coisa, veja em qual branch você está e o estado do repositório:

```bash
git status
git branch
```

**3. Crie sua branch pessoal:**

Nunca trabalhe diretamente na `main`! Crie sempre uma branch para seu trabalho:

```bash
git checkout -b feature/apresentacao-seu-nome
# Exemplo: git checkout -b feature/apresentacao-joao-silva
```

> 💡 O comando `git checkout -b` faz duas coisas de uma vez: **cria** a branch e já **muda** para ela. É equivalente a `git branch nome-da-branch` seguido de `git checkout nome-da-branch`.

**4. Crie seu arquivo de apresentação:**

- Vá para a pasta `exercicios/`
- Crie um arquivo com seu nome: `exercicios/seu-nome.md`
- Escreva o seguinte conteúdo:

```markdown
# Apresentação - Seu Nome

**Cargo:** Seu cargo na empresa/universidade

**O que espero aprender com Git:**
- Uma frase sobre suas expectativas

**Data:** (coloque a data de hoje)
```

**5. Verifique o que mudou:**

```bash
git status
```

Você verá o arquivo novo listado como *untracked* (não rastreado). O Git detectou o arquivo, mas ainda não está monitorando-o.

**6. Adicione o arquivo à Staging Area:**

```bash
git add exercicios/seu-nome.md
```

Execute `git status` novamente. Perceba que o arquivo mudou de cor/categoria — agora está em "*Changes to be committed*" (pronto para o commit).

**7. Faça o commit:**

```bash
git commit -m "feat: adiciona apresentação de seu-nome"
```

> 💡 A flag `-m` permite escrever a mensagem diretamente na linha de comando. Sem ela, o Git abriria um editor de texto.

**8. Envie para o servidor:**

```bash
git push origin feature/apresentacao-seu-nome
```

**9. Crie o Pull Request:**

- Vá para o GitHub. Aparecerá um banner amarelo sugerindo abrir um PR.
- Clique em **"Compare & pull request"**.
- Título sugerido: `feat: adiciona apresentação de seu-nome`
- Clique em **"Create pull request"**.

**10. Confirme o exercício:**

- Vá para a **Issue #1**.
- Comente: `✅ Exercício 1 concluído - Link do PR: [cole o link aqui]`

> ⚠️ **Por que não fazer push direto na `main`?** A branch `main` representa o código estável do projeto. Enviar mudanças diretamente nela sem revisão é uma má prática que pode introduzir erros. Branches + PRs existem justamente para proteger a `main`.

---

## Exercício 2: Trabalhando com Branches 🌿

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15-20 minutos |
| **Objetivo** | Entender o fluxo completo de branch: criar, trabalhar, publicar e abrir PR. |
| **Conceitos praticados** | `pull`, `checkout -b`, `push -u`, Pull Request com template |

### O que você vai aprender

Branches são o coração do trabalho em equipe com Git. Este exercício reforça o fluxo de trabalho padrão: sempre começar da `main` atualizada, criar uma branch, fazer suas mudanças e abrir um PR.

### Passos

**1. Atualize sua cópia local antes de começar:**

Seus colegas podem ter feito mudanças desde que você clonou o repositório. Sempre sincronize antes de começar a trabalhar:

```bash
git checkout main
git pull origin main
```

> 💡 `git pull` é, na prática, a combinação de `git fetch` (baixa as mudanças) + `git merge` (incorpora as mudanças na sua branch). Use-o sempre antes de criar uma nova branch.

**2. Crie sua branch:**

```bash
git checkout -b feature/bio-seu-nome
# Exemplo: git checkout -b feature/bio-maria-oliveira
```

**3. Crie sua bio:**

Na pasta `exercicios/`, crie o arquivo `bio-seu-nome.md`:

```markdown
# Bio - Seu Nome

Olá! Sou estudante no Laboratório ------ da Universidade -------.

**Habilidades principais:**
- Linguagem/framework que você usa
- Ferramentas que domina

**Projetos recentes:**
- Um projeto que você trabalhou ou está trabalhando

**Fun fact:** Algo interessante sobre você!
```

**4. Commit e push:**

```bash
git add exercicios/bio-seu-nome.md
git commit -m "feat: adiciona bio pessoal de seu-nome"
git push -u origin feature/bio-seu-nome
```

> 💡 O `-u` (ou `--set-upstream`) cria um vínculo entre sua branch local e a remota. Após isso, nos próximos pushes desta branch basta digitar `git push`, sem precisar especificar `origin feature/bio-seu-nome` novamente.

**5. Crie o Pull Request com template:**

No GitHub, abra o PR e use a seguinte descrição:

```markdown
## O que foi feito
Adicionei minha bio pessoal no arquivo `bio-seu-nome.md`.

## Como testar
1. Abra o arquivo `exercicios/bio-seu-nome.md`
2. Leia minha apresentação :)

## Checklist
- [x] Criei branch com meu nome
- [x] Escrevi mensagem de commit clara
- [x] Testei localmente
```

**6. Confirme o exercício:**

- Comente na **Issue #2**: `✅ Exercício 2 concluído - Link do meu PR: [link]`

---

## Exercício 3: Fazendo Code Review 👀

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 10-15 minutos |
| **Objetivo** | Aprender a revisar o trabalho dos colegas com qualidade e respeito. |
| **Conceitos praticados** | Pull Request review, comentários de linha, Approve / Request Changes |

### O que você vai aprender

Code Review não é só sobre encontrar bugs — é sobre **compartilhar conhecimento**, garantir qualidade e colaborar. Uma boa revisão inclui elogios, sugestões construtivas e perguntas que fazem o autor pensar.

### Passos

**1. Encontre um PR para revisar:**

- Vá para a aba **Pull Requests** do repositório.
- Escolha um PR **aberto** de um colega (não o seu próprio!).
- Dê preferência a PRs que ainda não têm review.

**2. Leia as mudanças:**

- Clique na aba **"Files changed"** para ver exatamente o que foi alterado.
- Leia com atenção antes de comentar.

**3. Faça pelo menos um comentário de linha:**

- Passe o mouse sobre uma linha e clique no ícone `+` azul que aparece.
- Escreva um comentário. Exemplos:

  - 👍 Elogio: *"Boa estrutura! O arquivo ficou bem organizado e fácil de ler."*
  - 💡 Sugestão: *"Que tal adicionar os anos de experiência com cada ferramenta?"*
  - ❓ Pergunta: *"Interessante esse projeto! Qual linguagem você usou nele?"*

**4. Envie a review geral:**

No final da página, clique em **"Review changes"** e escolha:
- ✅ **Approve** — tudo ok, pode mergear.
- 🔄 **Request changes** — há algo que precisa ser ajustado antes do merge.
- 💬 **Comment** — tem sugestões, mas não bloqueia o merge.

**5. Boas práticas de review:**

- Comece sempre com algo positivo antes de apontar problemas.
- Seja específico: em vez de *"isso está errado"*, diga *"sugiro mudar X por Y porque Z"*.
- Use `@nome-do-colega` se precisar de resposta direta.
- Lembre-se: você está revisando o **trabalho**, não a **pessoa**.

**6. Confirme o exercício:**

Comente na **Issue #3**:

```markdown
✅ Exercício 3 concluído

Revisei o PR de: @nome-do-colega
Link do PR revisado: [link]
Uma coisa que aprendi nesse processo: [escreva algo que você notou ou descobriu]
```

> 💡 **Code review é uma das partes mais valiosas do Git!** Grandes empresas de tecnologia levam a revisão de código tão a sério quanto o desenvolvimento. É onde garantimos qualidade e disseminamos conhecimento no time.

---

## Exercício 4: Resolvendo Conflitos 🔄

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 20-25 minutos |
| **Objetivo** | Entender o que são conflitos de merge e como resolvê-los com calma. |
| **Conceitos praticados** | `merge`, conflitos, marcadores `<<<<<<<`, resolução manual |

### O que você vai aprender

Conflitos acontecem quando duas pessoas editam **a mesma parte do mesmo arquivo** em branches diferentes. O Git não sabe qual versão manter, então sinaliza o conflito e pede que você decida. É uma situação normal — todo desenvolvedor enfrenta conflitos regularmente.

### Preparação (Admin)

O arquivo `exercicios/lista-de-filmes.md` deve existir com este conteúdo inicial:

```markdown
# Lista de Filmes Favoritos

## Filmes já adicionados:
- Matrix (1999) - Ficção Científica
- O Poderoso Chefão (1972) - Drama
- Lua de Cristal (1990) - Comédia
```

### Passos

**1. Atualize a `main` e crie sua branch:**

```bash
git checkout main
git pull origin main
git checkout -b feature/filmes-seu-nome
```

**2. Adicione seus filmes:**

Abra `exercicios/lista-de-filmes.md` e adicione 2 filmes **na seção "Filmes já adicionados"**, seguindo o padrão:

```markdown
- Seu Filme 1 (ano) - Gênero
- Seu Filme 2 (ano) - Gênero
```

> ⚠️ **Importante:** Adicione seus filmes **próximos à mesma linha** onde outros colegas vão adicionar os deles. O objetivo é **criar conflito de propósito** para praticar a resolução.

**3. Faça o commit:**

```bash
git add exercicios/lista-de-filmes.md
git commit -m "feat: adiciona 2 filmes favoritos de seu-nome"
```

**4. Simule o conflito:**

Enquanto você trabalhava, outros colegas também adicionaram filmes e já fizeram merge na `main`. Vamos simular isso:

```bash
git checkout main
git pull origin main        # Baixa os filmes dos colegas
git checkout feature/filmes-seu-nome
git merge main              # Tenta incorporar as mudanças da main na sua branch
```

**5. Entenda e resolva o conflito:**

Se o Git detectar conflito, você verá a mensagem:
```
CONFLICT (content): Merge conflict in exercicios/lista-de-filmes.md
Automatic merge failed; fix conflicts and then commit the result.
```

Abra o arquivo no editor. Você encontrará marcadores como este:

```
<<<<<<< HEAD
- Seu Filme 1 (ano) - Gênero
- Seu Filme 2 (ano) - Gênero
=======
- Filme Do Colega (ano) - Gênero
>>>>>>> main
```

**Como ler os marcadores:**
- `<<<<<<< HEAD` → início da sua versão (branch atual)
- `=======` → separador entre as duas versões
- `>>>>>>> main` → início da versão que veio da `main`

**Para resolver:** edite o arquivo manualmente, deixando o resultado que faz sentido. Para este exercício, **mantenha ambos os filmes**:

```markdown
- Seu Filme 1 (ano) - Gênero
- Seu Filme 2 (ano) - Gênero
- Filme Do Colega (ano) - Gênero
```

Depois, **remova todos os marcadores** (`<<<<<<<`, `=======`, `>>>>>>>`). Salve o arquivo.

**6. Finalize o merge:**

```bash
git add exercicios/lista-de-filmes.md
git commit -m "fix: resolve conflito na lista de filmes"
git push -u origin feature/filmes-seu-nome
```

**7. Abra o Pull Request** com a descrição:

```markdown
## Conflito resolvido
Tive que resolver conflito com os filmes do @colega. Mantive ambos os conjuntos de filmes!
```

**8. Confirme o exercício:**

Comente na **Issue #4**:

```markdown
✅ Exercício 4 concluído

Tive conflito? Sim/Não
Como resolvi: [descreva brevemente o que você fez]
Link do PR: [link]
```

> 💡 **Conflitos não são erros — são parte normal do trabalho em equipe!** O importante é entender o que cada versão representa antes de decidir o que manter. Nunca resolva um conflito sem entender o código das duas partes.

---

## Exercício 5: Explorando o Histórico 📜

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15 minutos |
| **Objetivo** | Aprender a navegar no histórico de commits para entender a evolução do projeto. |
| **Conceitos praticados** | `git log`, `git blame`, `git diff`, `git show` |

### O que você vai aprender

O histórico do Git é uma das suas ferramentas mais poderosas. Com ele você consegue responder perguntas como: *"Quem introduziu esse bug?"*, *"O que mudou entre a versão de ontem e hoje?"*, *"Por que essa decisão foi tomada?"*.

### Preparação (Admin)

O arquivo `docs/dicas-git.md` deve existir com este conteúdo inicial:

```markdown
# Dicas Práticas de Git

## Dicas básicas
- Sempre faça `git pull` antes de começar a trabalhar
- Use mensagens de commit descritivas
- Crie branches para cada funcionalidade

## Comandos úteis
- `git status`: Veja o estado atual do repositório
- `git diff`: Veja diferenças nos arquivos antes do commit
```

### Passos

**1. Explore o histórico:**

```bash
# Histórico resumido — um commit por linha
git log --oneline

# Histórico com visualização gráfica das branches
git log --oneline --graph --all

# Histórico de um arquivo específico
git log --oneline docs/dicas-git.md

# Veja quem alterou cada linha do arquivo (muito útil para investigar mudanças)
git blame docs/dicas-git.md
```

> 💡 `git blame` mostra, linha por linha, o último commit que alterou cada parte do arquivo. É útil para entender o contexto de uma mudança ou encontrar quem introduziu um bug.

**2. Inspecione um commit específico:**

Pegue um ID de commit do `git log --oneline` e use:

```bash
git show [ID do commit]
# Exemplo: git show a3f9c2d
```

Isso mostra exatamente o que mudou naquele commit.

**3. Crie sua branch e adicione uma dica:**

```bash
git checkout -b feature/dica-seu-nome
```

Abra `docs/dicas-git.md` e adicione **uma dica nova** (pode criar uma seção nova):

```markdown
## Branches
- Use nomes descritivos: `feature/nova-funcionalidade` ou `fix/corrige-bug-login`
- Delete branches locais após o merge para manter o repositório limpo: `git branch -d nome`
```

**4. Commit e push:**

```bash
git add docs/dicas-git.md
git commit -m "docs: adiciona dicas sobre boas práticas de branches"
git push -u origin feature/dica-seu-nome
```

**5. No Pull Request, mencione:**

```markdown
## O que mudou
Adicionei uma dica sobre boas práticas de branches.
Antes de editar, usei `git log docs/dicas-git.md` para ver o histórico do arquivo e `git blame` para ver as contribuições anteriores.
```

**6. Confirme o exercício:**

Na **Issue #5**, comente: `✅ Exercício 5 concluído - Link do PR: [link]`

---

## Exercício 6: Desfazendo Mudanças ⏪

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 15-20 minutos |
| **Objetivo** | Aprender a corrigir erros com `git reset` e `git revert`, entendendo quando usar cada um. |
| **Conceitos praticados** | `git reset`, `git revert`, diferença entre desfazer local e público |

### O que você vai aprender

Errar faz parte. O Git oferece formas seguras de desfazer mudanças, mas a escolha do comando correto depende de uma pergunta crucial: **o commit já foi compartilhado com outras pessoas?**

| Situação | Comando recomendado | Por quê? |
| :--- | :--- | :--- |
| Commit **local** (ainda não fez push) | `git reset` | Reescreve o histórico local sem problema |
| Commit **público** (já fez push / está na main) | `git revert` | Cria um novo commit de reversão, sem destruir o histórico |

> ⚠️ **Regra de ouro:** Nunca use `git reset` em commits que já foram enviados para o repositório remoto e compartilhados com a equipe. Isso reescreve o histórico e causa confusão para todos.

### Passos

**1. Crie uma branch de teste:**

```bash
git checkout main
git pull origin main
git checkout -b feature/desfazer-seu-nome
```

**2. Faça um commit "acidental" (simulado):**

```bash
touch lixo.txt
git add lixo.txt
git commit -m "feat: commit de teste que quero desfazer"
```

**3. Desfaça o commit localmente com `git reset`:**

Use `git log --oneline` para ver o histórico. Então desfaça o último commit, mas **mantendo as mudanças no diretório de trabalho**:

```bash
git reset HEAD~1
```

- `HEAD~1` significa "um commit antes do atual".
- Após esse comando, o arquivo `lixo.txt` ainda existe na sua pasta, mas o commit desapareceu do histórico.
- Confirme com `git log --oneline` — o commit sumiu.
- Confirme com `git status` — o arquivo voltou a ser *untracked*.

> 💡 **Variações do `git reset`:**
> - `git reset HEAD~1` ou `git reset --mixed HEAD~1` → desfaz o commit, mantém os arquivos no disco (padrão).
> - `git reset --soft HEAD~1` → desfaz o commit, mantém os arquivos já na Staging Area (prontos para novo commit).
> - `git reset --hard HEAD~1` → desfaz o commit e **apaga as mudanças do disco**. Use com cuidado!

**4. Faça um commit "bom" e push:**

```bash
rm lixo.txt
git add -A
git commit -m "fix: remove arquivo de teste desnecessário"
git push -u origin feature/desfazer-seu-nome
```

> 💡 `git add -A` adiciona todas as mudanças, incluindo arquivos **deletados**. `git add .` também funciona na maioria dos casos, mas pode não capturar deleções em versões mais antigas do Git.

**5. Simule a reversão de um commit público com `git revert`:**

Agora vamos simular o cenário onde o commit já foi para a `main` e não podemos reescrevê-lo. Faça uma nova mudança:

```bash
# Adicione uma linha no seu arquivo de apresentação
echo "## Linha extra de teste" >> exercicios/seu-nome.md

git add exercicios/seu-nome.md
git commit -m "feat: adiciona linha extra de teste"
```

Use `git log --oneline` para pegar o **ID** desse commit. Então reverta-o:

```bash
git revert [ID do commit]
```

O Git abrirá um editor com uma mensagem de commit de reversão gerada automaticamente. Salve e feche o editor (no Vim: `:wq`, no nano: `Ctrl+X → Y → Enter`).

Perceba: o `git revert` **criou um novo commit** que desfaz as mudanças do anterior. O histórico original permanece intacto.

**6. Push e PR:**

```bash
git push
```

Na descrição do PR, explique com suas palavras a diferença entre `git reset` e `git revert`.

**7. Confirme o exercício:**

Na **Issue #6**, comente:

```markdown
✅ Exercício 6 concluído

Usei `git reset` para: [explique em que situação]
Usei `git revert` para: [explique em que situação]
Diferença principal entre os dois: [sua explicação]
Link do PR: [link]
```

---

## Exercício 7: Padrão de Commit (Conventional Commits) 🏷️

| Detalhe | Valor |
| :--- | :--- |
| **Duração Estimada** | 10-15 minutos |
| **Objetivo** | Praticar o padrão de mensagens de commit para tornar o histórico mais legível e útil. |
| **Conceitos praticados** | Conventional Commits, mensagem de commit com corpo |

### O que você vai aprender

Uma mensagem de commit bem escrita transforma o histórico do Git em uma documentação viva do projeto. O padrão **Conventional Commits** define uma estrutura clara:

```
<tipo>[escopo opcional]: <descrição curta>

[corpo opcional — detalhes do que foi feito e por quê]

[rodapé opcional — referências a issues, breaking changes, etc.]
```

**Tipos mais comuns:**

| Tipo | Quando usar |
| :--- | :--- |
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `docs` | Mudanças apenas em documentação |
| `style` | Formatação, sem mudança de lógica (espaços, vírgulas) |
| `refactor` | Refatoração de código sem adicionar feature ou corrigir bug |
| `test` | Adição ou correção de testes |
| `chore` | Tarefas de manutenção (dependências, configurações) |

**Exemplos de mensagens ruins x boas:**

```bash
# ❌ Ruim — vago, sem contexto
git commit -m "mudanças"
git commit -m "update"
git commit -m "arrumei uns bug"

# ✅ Bom — claro e específico
git commit -m "fix: corrige cálculo de desconto para pedidos acima de R$500"
git commit -m "feat: adiciona filtro de busca por data na listagem de pedidos"
git commit -m "docs: atualiza instruções de instalação no README"
```

### Passos

**1. Leia as convenções do projeto:**

Consulte o arquivo `docs/convencoes-commit.md` para as convenções específicas do repositório.

**2. Crie sua branch:**

```bash
git checkout main
git pull origin main
git checkout -b feature/padrao-commit-seu-nome
```

**3. Faça uma pequena melhoria:**

Melhore alguma frase no seu arquivo de bio (`exercicios/bio-seu-nome.md`). Pode ser corrigir um texto, adicionar uma linha ou melhorar a formatação.

**4. Commit com tipo e descrição claros:**

```bash
git add exercicios/bio-seu-nome.md
git commit -m "docs: melhora redação e formatação da bio pessoal"
```

**5. Pratique o commit com corpo (mais detalhado):**

Faça uma segunda pequena mudança e desta vez escreva um commit com corpo:

```bash
git commit -m "docs: melhora redação na bio pessoal

- Corrige frases incompletas na seção de habilidades
- Adiciona pontuação faltante
- Torna o texto mais fluido para leitura"
```

> 💡 A linha em branco entre o título e o corpo é obrigatória — sem ela, o Git trata tudo como título.

**6. Push e PR:**

```bash
git push -u origin feature/padrao-commit-seu-nome
```

No PR, mostre sua mensagem de commit como exemplo e explique por que escolheu aquele tipo.

**7. Confirme o exercício:**

Na **Issue #7**:

```markdown
✅ Exercício 7 concluído

Tipo de commit usado: [ex: docs]
Mensagem completa: [cole sua mensagem aqui]
Por que escolhi esse tipo: [sua explicação]
Link do PR: [link]
```

> 💡 **Ferramentas que automatizam isso:** [Commitizen](https://github.com/commitizen/cz-cli) é uma CLI interativa que te guia na criação de mensagens no padrão. O [Husky](https://typicode.github.io/husky/) permite criar hooks que **impedem** commits com mensagens fora do padrão. Pergunte para o time se já usamos algum desses!

---

## ❓ Dúvidas Frequentes

| Pergunta | Resposta |
| :--- | :--- |
| **"Deu erro no push, o que faço?"** | 1. Verifique a branch: `git branch`. 2. Faça `git pull` — pode haver conflito. 3. Verifique suas credenciais GitHub. |
| **"Como vejo todas as branches (locais e remotas)?"** | `git branch -a` (locais e remotas) ou `git branch` (só locais). |
| **"Como deletar uma branch local após o merge?"** | `git branch -d nome-da-branch` (só deleta se já foi mergeada). Para forçar: `git branch -D nome-da-branch`. |
| **"Como deletar uma branch remota?"** | `git push origin --delete nome-da-branch` |
| **"Fiz `git add` por engano, como desfaço?"** | `git restore --staged nome-do-arquivo` (remove da Staging Area, mantém as mudanças no arquivo). |
| **"Como descartar mudanças não commitadas de um arquivo?"** | `git restore nome-do-arquivo` — atenção: isso apaga as mudanças permanentemente! |
| **"Esqueci de incluir um arquivo no último commit."** | Adicione o arquivo com `git add` e use `git commit --amend --no-edit`. Só funciona antes do push! |
| **"Como renomear a branch atual?"** | `git branch -m novo-nome` |
| **"Onde acompanho o progresso de todos?"** | Aba **Issues** (comentários de conclusão) e aba **Pull Requests** (PRs abertos/mergeados). |

---

## 🚀 Próximos Passos

Parabéns por completar os exercícios! 🎉 Mas o aprendizado não para por aqui:

- **Pratique no dia a dia:** Use Git nos projetos reais da universidade ou empresa. Quanto mais você usa, mais natural fica.
- **Participe de Code Reviews:** Revise pelo menos 1 PR por semana — você aprende tanto revisando quanto sendo revisado.
- **Ensine um colega:** Explicar o que você aprendeu é a melhor forma de fixar o conhecimento.
- **Explore recursos avançados:** `git stash`, `git cherry-pick`, `git rebase` e `git bisect` são os próximos passos naturais.
- **Contribua com este repositório:** Tem ideias para melhorar os exercícios? Abra uma Issue ou um PR!

### 📚 Recursos para continuar aprendendo

- [Documentação oficial do Git](https://git-scm.com/doc) — referência completa
- [Pro Git Book](https://git-scm.com/book/pt-br/v2) — livro gratuito em português
- [GitHub Guides](https://guides.github.com/) — tutoriais oficiais do GitHub
- [Learn Git Branching](https://learngitbranching.js.org/?locale=pt_BR) — ferramenta visual e interativa (altamente recomendada!)
- [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/) — especificação completa do padrão de commits
