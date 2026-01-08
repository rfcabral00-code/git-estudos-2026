# Git-estudos-2026
Estudos sobre Git

Guia de Estudos de Git — Passo a Passo para Iniciantes

Este repositório reúne minhas anotações e prática inicial de Git.  
O objetivo é entender **o que cada comando faz**, quando usar e como funciona o fluxo de versionamento.

---

## O que é o Git (em poucas palavras)

Git é um sistema de controle de versão que permite:

✔ salvar o histórico de mudanças  
✔ recuperar versões anteriores  
✔ trabalhar em mais de um computador  
✔ colaborar em projetos

---

# 1) Navegando pelo terminal

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

# 2) Iniciando um repositório Git

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

# 3) Ciclo básico do Git

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

# 4) Consultando histórico

Histórico completo:

```
git log
```

Versão resumida:

```
git log --oneline
```

---

# 5) Conectando ao GitHub

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

# 6) Usando o repositório em outro computador

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

# 7) Fluxo recomendado de trabalho

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

Próximos tópicos planejados


- **Resolvendo conflitos**
- **Pull Request**
- **Criando Fork**
- **Integração com VS Code**
- **Git Flow**
- **Gitkeep e Gitignore**

---
 Objetivo do repositório:

✔ consolidar fundamentos do Git  
✔ registrar evolução dos estudos  
✔ servir como guia de consulta rápida