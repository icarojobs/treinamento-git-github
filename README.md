# Treinamento Prático: Git + GitHub para Times de Desenvolvimento

## Objetivo

Ao final deste treinamento, todos os participantes serão capazes de:

* Entender a diferença entre Git e GitHub
* Criar e versionar projetos localmente
* Trabalhar com Branches
* Realizar Commits de forma profissional
* Sincronizar código com GitHub
* Criar Pull Requests (PR)
* Fazer Code Review
* Resolver conflitos simples
* Entender como Git e GitHub potencializam o uso de IA no desenvolvimento moderno

---

# 1. O QUE É GIT?

Git é um Sistema de Controle de Versão Distribuído (DVCS).

Em termos simples:

> Git é uma máquina do tempo para código.

Ele permite:

* Salvar versões do projeto
* Voltar para versões anteriores
* Trabalhar em equipe
* Criar funcionalidades sem quebrar produção
* Auditar quem alterou o quê

---

## Exemplo

Imagine um arquivo:

```txt
sistema.php
```

Você altera o arquivo hoje.

Amanhã ele quebra.

Com Git você consegue voltar exatamente para o estado anterior.

---

# 2. O QUE É GITHUB?

GitHub é uma plataforma online que hospeda repositórios Git.

GitHub NÃO substitui Git.

GitHub utiliza Git.

---

## Analogia

Git:

```txt
Microsoft Word
```

GitHub:

```txt
OneDrive
```

ou

Git:

```txt
Banco de Dados
```

GitHub:

```txt
Servidor onde o banco está hospedado
```

---

# 3. DIFERENÇA ENTRE GIT VS GITHUB

| Git                    | GitHub                 |
| ---------------------- | ---------------------- |
| Ferramenta             | Plataforma             |
| Funciona offline       | Funciona online        |
| Controle de versão     | Compartilhamento       |
| Instalado na máquina   | Hospedado na nuvem     |
| Gratuito e Open Source | Serviço baseado em Git |

---

# 4. FLUXO PROFISSIONAL DE TRABALHO

```txt
Desenvolvedor
      ↓
Cria Branch
      ↓
Desenvolve
      ↓
Commit
      ↓
Push
      ↓
Pull Request
      ↓
Code Review
      ↓
Merge
      ↓
Produção
```

---

# 5. INSTALANDO O GIT

## Verificar instalação

```bash
git --version
```

Exemplo:

```bash
git version 2.52.0
```

---

# 6. PRIMEIROS PASSOS

## Configurar nome

```bash
git config --global user.name "Seu Nome"
```

Verificar:

```bash
git config user.name
```

---

## Configurar email

```bash
git config --global user.email "email@empresa.com"
```

Verificar:

```bash
git config user.email
```

---

## Listar configurações

```bash
git config --list
```

---

# 7. CRIANDO O PRIMEIRO REPOSITÓRIO

Criar pasta:

```bash
mkdir projeto-git
```

Entrar:

```bash
cd projeto-git
```

Inicializar Git:

```bash
git init
```

Resultado:

```txt
Initialized empty Git repository
```

---

# 8. ENTENDENDO O CICLO DO GIT

```txt
Working Directory
        ↓
git add
        ↓
Staging Area
        ↓
git commit
        ↓
Repository
```

---

# 9. PRIMEIRO COMMIT

Criar arquivo:

```bash
touch README.md
```

Verificar status:

```bash
git status
```

---

Adicionar arquivo:

```bash
git add README.md
```

---

Adicionar tudo:

```bash
git add .
```

---

Criar commit:

```bash
git commit -m "Primeiro commit"
```

---

# 10. PRINCIPAIS COMANDOS GIT

---

## git status

Mostra o estado atual.

```bash
git status
```

Uso diário.

---

## git add

Adiciona alterações.

```bash
git add .
```

ou

```bash
git add arquivo.php
```

---

## git commit

Cria um snapshot.

```bash
git commit -m "Cadastro de clientes"
```

---

## git log

Histórico.

```bash
git log
```

Modo resumido:

```bash
git log --oneline
```

---

## git diff

Mostra alterações.

```bash
git diff
```

---

## git restore

Desfaz alterações.

```bash
git restore arquivo.php
```

---

## git rm

Remove arquivo.

```bash
git rm arquivo.php
```

---

## git mv

Renomeia arquivo.

```bash
git mv antigo.php novo.php
```

---

# 11. BRANCHES

## O que é uma Branch?

Uma linha paralela de desenvolvimento.

---

Listar:

```bash
git branch
```

---

Criar:

```bash
git branch feature/login
```

---

Trocar:

```bash
git checkout feature/login
```

---

Criar e trocar:

```bash
git checkout -b feature/login
```

ou

```bash
git switch -c feature/login
```

---

Voltar para main:

```bash
git checkout main
```

---

# 12. MERGE

Unir duas branches.

```bash
git merge feature/login
```

Fluxo:

```txt
main
  \
   feature/login
          |
          Merge
          |
        main
```

---

# 13. CONFLITOS

Ocorrem quando duas pessoas alteram a mesma linha.

Exemplo:

```txt
<<<<<<< HEAD
Nome Atual
=======
Novo Nome
>>>>>>> feature
```

Resolver:

1. Editar manualmente
2. Salvar
3. Commitar

```bash
git add .
git commit
```

---

# 14. CONECTANDO AO GITHUB

Criar repositório no GitHub.

Copiar URL.

Exemplo:

```txt
https://github.com/empresa/projeto.git
```

Adicionar remoto:

```bash
git remote add origin URL
```

Verificar:

```bash
git remote -v
```

---

# 15. PUSH

Enviar para GitHub.

Primeira vez:

```bash
git push -u origin main
```

Próximas vezes:

```bash
git push
```

---

# 16. CLONE

Baixar projeto.

```bash
git clone URL
```

Exemplo:

```bash
git clone https://github.com/empresa/projeto.git
```

---

# 17. PULL

Baixar alterações.

```bash
git pull
```

Fluxo recomendado:

```bash
git pull origin main
```

---

# 18. FETCH

Buscar alterações sem aplicar.

```bash
git fetch
```

Muito utilizado antes de merge.

---

# 19. FLUXO PROFISSIONAL DE BRANCHES

Padrão recomendado:

```txt
main
develop
feature/*
hotfix/*
release/*
```

Exemplos:

```txt
feature/login
feature/cadastro-cliente

hotfix/correcao-pix

release/v1.3.0
```

---

# 20. PADRÃO DE COMMITS

Evite:

```txt
ajustes
correção
teste
update
```

Prefira:

```txt
feat: adiciona login por Google

fix: corrige cálculo de comissão

refactor: simplifica regra de descontos

docs: atualiza README

test: adiciona testes de integração
```

---

# 21. PULL REQUEST (PR)

O que é?

Solicitação de merge.

Permite:

* Revisão
* Discussão
* Auditoria
* Aprovação

---

# 22. FLUXO COMPLETO DE PR

## Passo 1

Atualizar main

```bash
git checkout main
git pull
```

---

## Passo 2

Criar branch

```bash
git checkout -b feature/login
```

---

## Passo 3

Desenvolver

---

## Passo 4

Commit

```bash
git add .
git commit -m "feat: adiciona autenticação"
```

---

## Passo 5

Push

```bash
git push origin feature/login
```

---

## Passo 6

Abrir Pull Request

GitHub:

```txt
Compare & Pull Request
```

---

## Passo 7

Code Review

Analisar:

* Código
* Performance
* Segurança
* Padrões

---

## Passo 8

Approve

```txt
Approve Changes
```

---

## Passo 9

Merge

```txt
Merge Pull Request
```

---

## Passo 10

Remover Branch

```txt
Delete Branch
```

---

# 23. BOAS PRÁTICAS DE PR

PR Pequena:

```txt
Até 300 linhas
```

Ideal:

```txt
Até 150 linhas
```

---

Sempre incluir:

* Objetivo
* Impacto
* Evidências
* Screenshots

---

# 24. GIT + IA

A IA aumentou a velocidade de geração de código.

Mas também aumentou:

* Bugs
* Código duplicado
* Dívida técnica

Git se tornou ainda mais importante.

---

## Cenário Moderno

```txt
IA gera código
↓
Desenvolvedor valida
↓
Commit
↓
PR
↓
Review
↓
Merge
```

---

# 25. COMO USAR IA COM GIT

Exemplos:

```txt
Copilot
ChatGPT
Claude
Gemini
Cursor
Windsurf
```

---

Fluxo ideal:

```txt
IA gera
↓
Você revisa
↓
Commit pequeno
↓
PR pequeno
↓
Merge seguro
```

---

# 26. GITHUB TRENDING

GitHub Trending mostra:

* Projetos populares
* Novas tecnologias
* Frameworks emergentes
* Ferramentas promissoras

---

## Acesso

https://github.com/trending

---

## Python

https://github.com/trending/python?since=daily

---

## PHP

https://github.com/trending/php?since=daily

---

# 27. POR QUE OLHAR O TRENDING?

Aprender:

* Arquitetura
* Padrões
* Open Source
* Novas tecnologias

---

Exemplo:

Você pode descobrir:

* Frameworks
* Bibliotecas
* Ferramentas DevOps
* Agentes IA
* MCP Servers
* SDKs

Meses antes de virarem padrão de mercado.

---

# 28. LABORATÓRIO PRÁTICO

## Exercício 1

Criar repositório local.

Objetivo:

```txt
git init
git add
git commit
```

---

## Exercício 2

Criar branch.

Objetivo:

```txt
git checkout -b feature/nome
```

---

## Exercício 3

Realizar merge.

Objetivo:

```txt
git merge
```

---

## Exercício 4

Criar conflito proposital.

Resolver manualmente.

---

## Exercício 5

Criar repositório GitHub.

Realizar:

```txt
push
pull
clone
```

---

## Exercício 6

Criar Pull Request real.

Fluxo completo:

```txt
Branch
Commit
Push
PR
Review
Approve
Merge
```

---

# 29. RESUMO FINAL

Todo desenvolvedor deve dominar:

✅ git init

✅ git status

✅ git add

✅ git commit

✅ git log

✅ git diff

✅ git branch

✅ git checkout

✅ git merge

✅ git clone

✅ git pull

✅ git push

✅ Pull Request

✅ Code Review

✅ Resolução de Conflitos

✅ GitHub Trending

---

# FRASE FINAL

"Amadores escrevem código.
Profissionais versionam código."

---

# Autor

**Autor do Treinamento:** Icaro William

**Especialidade:** Arquiteto de Software (há mais de 20 anos)

**Assunto:** Git vs GitHub

**Mais sobre:** https://youtube.com/@tiojobs
