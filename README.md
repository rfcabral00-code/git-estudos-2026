# Git-estudos-2026
Estudos sobre Git

Curso para iniciantes aprederem a trabalhar com versionamento de código e repositórios remotos com github.
Além disso, também iremos trabalhar com gitflow ao final do curso e visual studio code.

Guia de Estudos de Git — Passo a Passo para Iniciantes

Este repositório reúne minhas anotações e prática inicial de Git.  
O objetivo é entender **o que cada comando faz**, quando usar e como funciona o fluxo de versionamento.

---
# Dia 1 e 2

## O que é o Git (em poucas palavras)

Git é um sistema de controle de versão que permite:

✔ salvar o histórico de mudanças  
✔ recuperar versões anteriores  
✔ trabalhar em mais de um computador  
✔ colaborar em projetos

---

# Navegando pelo terminal

| Comando | Explicação |
|--------|---------|
| `ls` | lista arquivos da pasta |
| `cd nome-da-pasta` | entra em uma pasta |
| `cd ..` | volta uma pasta |
| `pwd` | mostra onde você está |
| `mkdir nome-da-pasta` | cria uma pasta |
| `nano nome.txt` | cria/edita um arquivo |
| `cat nome.txt` | exibe o conteúdo do arquivo |

 Atenção

| Comando | O que faz |
|--------|---------|
| `rm -rf .git` | apaga todo o repositório Git |

---

# Iniciando um repositório Git

Criar repositório:

```
git init
```

Verificar status:

```
git status
```

Legenda:

🔴 arquivos não versionados  
🟡 arquivos preparados para commit  
🟢 arquivos versionados

---

# Ciclo básico do Git

Editar arquivos → adicionar ao stage → criar commit

Adicionar arquivo específico:

```
git add nome-arquivo
```

Adicionar tudo:

```
git add .
```

Criar commit:

```
git commit -m "Mensagem clara do que foi feito"
```

Boas mensagens de commit:

✔ curtas  
✔ objetivas  
✔ no presente

Exemplos:

```
Adiciona anotações de comandos Git
Atualiza README com fluxo de trabalho
Corrige explicação do git status
```

---

# Consultando histórico

Histórico completo:

```
git log
```

Versão resumida:

```
git log --oneline
```

---

# Conectando ao GitHub

Definir branch principal:

```
git branch -M main
```

Adicionar repositório remoto:

```
git remote add origin https://github.com/rfcabral00-code/git-estudos-2026.git
```

Enviar pela primeira vez:

```
git push -u origin main
```

Depois basta:

```
git push
```

---

# Usando o repositório em outro computador

Clonar:

```
git clone https://github.com/rfcabral00-code/git-estudos-2026.git
cd git-estudos-2026
```

Atualizar:

```
git pull
```

---

# Fluxo recomendado de trabalho

Sempre seguir:

```
git pull
editar arquivos
git status
git add .
git commit -m "mensagem"
git push
```

✔ reduz riscos de conflito  
✔ mantém histórico organizado

---

# Estudo Prático — Branches e Merge

Branches permitem trabalhar em novas funcionalidades sem alterar a `main`.

---

## O que é uma branch?

Uma branch é uma cópia de trabalho onde você pode:

✔ desenvolver uma nova funcionalidade  
✔ testar mudanças  
✔ evitar risco no código principal

Depois, o conteúdo pode ser integrado com **merge**.

---

## Criar uma nova branch e entrar nela

```
git checkout -b nome-da-branch
```

Exemplo:

```
git checkout -b feature-anotacoes
```

---

## Ver todas as branches

```
git branch
```

A branch com `*` é a atual.

---

## Voltar para a main

```
git checkout main
```

> Não usa `-b`, pois a branch já existe.

---

## Fazer merge (unir branches)

Ir para a branch que receberá as mudanças:

```
git checkout main
```

Aplicar o merge:

```
git merge nome-da-branch
```

Exemplo:

```
git merge feature-anotacoes
```

✔ merge = mistura os históricos

---

## Excluir branch após merge

Exclusão segura:

```
git branch -d nome-da-branch
```

Forçar exclusão (casos específicos):

```
git branch -D nome-da-branch
```

⚠️ use `-D` com cuidado

---

## Boas práticas com branches

✔ uma branch por tarefa  
✔ commits pequenos e claros  
✔ faça merge somente quando concluir  
✔ exclua branch após integrar

-------------

# Dia 3 — Branches, Conflitos, GitHub, VS Code e Git Flow

Neste dia, o estudo avançou para o uso prático de branches, resolução de conflitos, uso mais aprofundado do GitHub, forks, integração com o VS Code e introdução ao Git Flow, seguindo padrões utilizados no mercado.

---

## Branches — comandos essenciais

Criar uma nova branch e entrar nela:

git checkout -b nome-da-branch

Listar todas as branches do projeto:

git branch

Voltar para a branch principal (main):

git checkout main

---

## Merge — unindo branches

O merge é utilizado para trazer o conteúdo de uma branch para outra.

Fluxo correto:

git checkout main  
git merge nome-da-branch  

✔ o conteúdo da branch secundária é integrado à main  
✔ os históricos são combinados  

---

## Resolvendo conflitos

Conflitos acontecem quando:

✔ dois commits alteram a mesma linha de um arquivo  
✔ o Git não sabe qual versão manter  

Fluxo para resolver conflitos:

1️⃣ o Git sinaliza o conflito  
2️⃣ o arquivo é marcado com indicadores (<<<<<<<, =======, >>>>>>>)  
3️⃣ o desenvolvedor escolhe o conteúdo correto  
4️⃣ o arquivo é salvo  
5️⃣ o conflito é marcado como resolvido  

Após resolver o conflito:

git add arquivo-com-conflito  
git commit -m "Resolve conflito de merge"  

✔ conflitos são normais  
✔ fazem parte do fluxo real de trabalho  

---

## GitHub — uso mais aprofundado

Neste dia foi estudado:

✔ diferença entre repositório local e remoto  
✔ sincronização correta com push e pull  
✔ importância de sempre atualizar antes de enviar mudanças  

Fluxo recomendado:

git pull  
git add .  
git commit -m "mensagem"  
git push  

---

## Forks — contribuindo em outros projetos

Fork é uma cópia de um repositório de outra pessoa para a sua conta no GitHub.

Fluxo básico:

1️⃣ criar um fork no GitHub  
2️⃣ clonar o fork para o computador  
3️⃣ criar uma branch para alterações  
4️⃣ enviar commits para o fork  
5️⃣ abrir um Pull Request  

✔ usado para contribuir em projetos open source  
✔ não altera o repositório original diretamente  

---

## Integração do Git com o Visual Studio Code

Foi explorada a integração nativa do Git dentro do VS Code, entendendo como o versionamento funciona diretamente pela interface.

Durante os testes foi possível:

✔ visualizar arquivos modificados  
✔ acompanhar alterações linha a linha no README  
✔ realizar staging pela interface gráfica  
✔ criar commits sem usar o terminal  
✔ atualizar a branch main diretamente pelo VS Code  

Também foi utilizado o terminal Bash integrado, permitindo:

✔ executar comandos Git  
✔ checar o status (git status)  
✔ realizar commits via terminal  
✔ alternar entre interface gráfica e linha de comando  

Foi analisado também o Git Graph, que facilita:

✔ visualização de branches  
✔ acompanhamento de merges  
✔ entendimento do histórico de commits  

---

## Git Flow — prática e padrões utilizados

Neste momento foi introduzido o Git Flow, seguindo padrões amplamente utilizados no mercado.

Estrutura básica utilizada:

✔ main → branch de produção  
✔ develop → branch de desenvolvimento  
✔ branches temporárias para funcionalidades e documentação  

Fluxo geral:

✔ tudo começa na main  
✔ o desenvolvimento acontece na develop  
✔ após finalização e testes, a develop é integrada à main  

Antes de iniciar qualquer alteração na develop:

git pull origin develop  

✔ garante que a branch esteja atualizada  
✔ evita conflitos futuros  

---

## Padrão de nomeação de branches

Foram utilizados padrões adotados pela comunidade:

git checkout -b docs/readme  

Prefixos utilizados:

✔ docs/ → documentação  
✔ feat/ → novas funcionalidades  

---

## Padrão de mensagens de commit

Foi seguido o padrão de commits semânticos:

✔ docs: mudanças em documentação  
✔ feat: novas funcionalidades  

Exemplos:

docs: teste  
feat: ola mundo em python  

---

## Pull Request e integração

Após os commits:

✔ a branch foi publicada no GitHub  
✔ foi criado um Pull Request  
✔ a base do PR foi alterada para develop  
✔ o merge foi realizado  
✔ a branch temporária foi excluída  

---

## Exemplo prático com Python

Criação de uma nova funcionalidade:

git checkout -b feat/ola-mundo  

Código criado:

print("ola mundo")  

Commit realizado pelo VS Code:

feat: ola mundo em python  

A branch foi publicada e integrada à develop.

Após todas as alterações:

git checkout main  
git merge develop  

✔ a main foi atualizada  
✔ o fluxo do Git Flow foi concluído corretamente  

---

## Aprendizados do Dia 3

✔ nunca trabalhar diretamente na main  
✔ sempre atualizar a develop antes de começar  
✔ conflitos fazem parte do processo  
✔ usar padrões de branch e commit  
✔ GitHub vai além de backup de código  
✔ forks permitem colaboração segura  
✔ VS Code facilita o uso do Git sem substituir seus conceitos  

---

## Próximos tópicos planejados

- Gitkeep  
- Gitignore  

