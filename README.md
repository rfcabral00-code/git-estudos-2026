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


# Dia 3 — Branches, Conflitos e GitHub 

Neste dia, o foco foi aprofundar o uso de branches, entender conflitos, trabalhar melhor com o GitHub e aprender sobre forks.

---

## 🌿 Branches (revisão e aprofundamento)

Branches permitem desenvolver funcionalidades de forma isolada, sem impactar diretamente a branch principal (`main`).

### Criar uma branch e entrar nela
```bash
git checkout -b nome-da-branch
Listar branches
git branch

Voltar para a branch principal
git checkout main

### Merge — unindo branches

O merge é usado para trazer o conteúdo de uma branch para outra.

Fluxo correto:

git checkout main
git merge nome-da-branch


✔ o conteúdo da branch secundária é integrado à main
✔ os históricos são combinados

### Resolvendo conflitos

Conflitos acontecem quando:

dois commits alteram a mesma linha de um arquivo

o Git não sabe qual versão manter

Fluxo para resolver conflitos

1️⃣ o Git sinaliza o conflito
2️⃣ o arquivo é marcado com indicadores (<<<<<<<, =======, >>>>>>>)
3️⃣ o desenvolvedor escolhe o conteúdo correto
4️⃣ o arquivo é salvo
5️⃣ o conflito é marcado como resolvido

git add arquivo-com-conflito
git commit -m "Resolve conflito de merge"


✔ conflitos são normais
✔ fazem parte do fluxo real de trabalho

## GitHub — uso mais aprofundado

Neste dia foi estudado:

✔ diferença entre repositório local e remoto
✔ sincronização com push e pull
✔ importância de sempre atualizar antes de enviar mudanças

## Fluxo recomendado:

git pull
git add .
git commit -m "mensagem"
git push

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

## Aprendizados importantes do Dia 3



## Integração do Git com o Visual Studio Code

Neste momento do estudo, foi explorada a integração nativa do Git dentro do VS Code, observando como o versionamento funciona diretamente pela interface.

### Funcionalidades observadas no VS Code

✔ visualização de arquivos modificados  
✔ identificação de alterações linha a linha no README  
✔ staging de arquivos pela interface gráfica  
✔ criação de commits sem usar o terminal  
✔ atualização da branch `main` diretamente pelo VS Code  

---

### Testes realizados

Durante o estudo foram feitos testes práticos:

- modificação do arquivo `README.md`
- verificação das mudanças no painel de Source Control
- criação de commit pelo VS Code
- envio das alterações para o GitHub (update da `main`)
- validação do histórico de commits

Esses testes ajudaram a entender melhor o fluxo visual do Git.

---

### Git Graph no VS Code

Foi analisado o uso do **Git Graph** para:

✔ visualizar branches  
✔ acompanhar merges  
✔ entender o histórico de commits  
✔ observar a linha do tempo do projeto  

O gráfico facilita a compreensão do fluxo do Git, principalmente para iniciantes.

---

### Terminal integrado (Bash)

Também foi utilizado o **terminal Bash integrado ao VS Code**, permitindo:

✔ executar comandos Git diretamente no editor  
✔ checar o status do repositório (`git status`)  
✔ realizar commits pelo terminal  
✔ alternar entre interface gráfica e linha de comando  

Isso mostrou que o VS Code não substitui o Git, mas facilita o uso.

---

## Aprendizados importante e adicionais do Dia 3

✔ trabalhar sempre em branches
✔ conflitos fazem parte do processo
✔ GitHub é mais que apenas um “backup”
✔ forks permitem colaboração sem acesso direto
✔ o VS Code integra Git de forma nativa  
✔ é possível commitar via interface ou terminal  
✔ o Git Graph ajuda a visualizar o histórico  
✔ a lógica do Git é a mesma dentro e fora do editor  

---

/## Próximos tópicos planejados

- **Git Flow**
- **Gitkeep e Gitignore**

---
 Objetivo do repositório:

✔ consolidar fundamentos do Git  
✔ registrar evolução dos estudos  
✔ servir como guia de consulta rápida


obrigado ttheomewhy