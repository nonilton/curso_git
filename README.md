# curso_git

## 1. Inicio_Básico

A primeira coisa a fazer antes de começar a usar o git é configurar alguns parâmetros básicos que nos identificam como usuário, que são nosso email e nosso nome.

```
git config --global user.name "nome sobrenome"
```

```
git config --global user.email "mail@mail.com"
```

## 2. Clonando um repositório

Um repositório também pode ser iniciado copiando ( clonando ) um existente.

por exemplo:

```
git clone https://github.com/exemplo/repo-exemplo.git
```

## Criar uma Branch

```
git checkout -b nome-da-sua-nova-branch
```

###### OBS:. Verificar na Issue alguma informação sobre o nome que deve ser criado para essa branch.
---
Importante fazer o checkout para ter certeza de estar na sua branch

### A. Alternar para uma Branch Existente:
Para mudar para uma branch existente no seu repositório, use:
```
git checkout nome-da-branch
```

### B. Criar e Alternar para uma Nova Branch:
Para criar uma nova branch e mudar imediatamente para ela, use a opção -b:
```
git checkout -b nome-da-nova-branch
```

### B1 Deletar uma Branch Local
Para deletar uma branch local que já foi mesclada (merged) com a branch atual, use o seguinte comando:
```
git branch -d nome-da-branch
```
Isso irá deletar a branch nome-da-branch. 

### Para deletar uma branch chamada minha-feature, você faria:

```
git branch -d minha-feature
```

Se a branch contiver mudanças que ainda não foram mescladas (merged), o Git emitirá um aviso para garantir que você realmente deseja deletar a branch.

### Forçar a Deleção de uma Branch Local
Se você quiser deletar uma branch mesmo que ela contenha mudanças não mescladas, use o seguinte comando:
```
git branch -D nome-da-branch
```
Isso forçará a deleção da branch nome-da-branch independentemente das mudanças não mescladas.

### Deletar uma Branch Remota
Para deletar uma branch remota (no repositório remoto como GitHub, GitLab, etc.), use o comando git push com a opção --delete:
```
git push origin --delete nome-da-branch
```
Isso deletará a branch nome-da-branch do repositório remoto chamado origin. Certifique-se de substituir origin pelo nome correto do seu repositório remoto, se for diferente.

### Verificar Branches
Para verificar todas as branches locais e remotas, use:
```
git branch -a
```
Isso mostrará uma lista de todas as branches, indicando quais são locais (prefixo *) e quais são remotas (prefixo remotes/origin/ ou similar).
---
### C. Restaurar Arquivos:
Você pode usar git checkout para restaurar arquivos modificados para a versão mais recente no repositório:
```
git checkout -- nome-do-arquivo
```

## 3. Git Stage
Modificar os estado do git

### A. Status
verificar o status das mudanças no código:

```
git status
```

### B. Adicionar arquivos
O comando git add é usado no Git para adicionar mudanças feitas em arquivos ao índice (também conhecido como área de preparação) para prepará-las para o próximo commit 

#### B1. Mudanças especificas
```
git add nome-do-arquivo
```

#### B2. Todas as mudanças
```
git add .
```
### C. Git Commit
O comando git commit é utilizado no Git para criar um novo commit com as mudanças que foram adicionadas ao índice (staging area).
Para criar um commit com todas as mudanças adicionadas ao índice, você pode usar:
```
git commit -m "Mensagem do commit"
```
## 4. O comando git push é utilizado no Git para enviar (ou "empurrar") os commits locais de uma branch para um repositório remoto. Isso é útil para manter o repositório remoto atualizado com as alterações feitas localmente. Aqui está como você pode usar o git push:

### 4A. Enviar Commits para o Repositório Remoto
Para enviar os commits de uma branch local para o repositório remoto (por exemplo, no GitHub, GitLab, Bitbucket), use o seguinte comando:
```
git push origin nome-da-branch
```
Isso enviará os commits da branch nome-da-branch para o repositório remoto chamado origin. Certifique-se de substituir nome-da-branch pelo nome da sua branch local e origin pelo nome do seu repositório remoto, se for diferente.

### 4B. Enviar Todas as Branches para o Repositório Remoto
Se você deseja enviar todas as branches locais para o repositório remoto, incluindo commits que ainda não estão no repositório remoto, use:
```
git push --all origin
```
Isso enviará todas as branches locais para o repositório remoto origin.

### 4C. Forçar o Push
Às vezes, você pode precisar forçar o push para substituir o histórico remoto com o seu histórico local (cuidado ao usar isso, pois pode causar perda de commits não sincronizados). Para forçar o push, use a opção --force ou -f:
```
git push --force origin nome-da-branch
```
Isso forçará o push dos commits da branch nome-da-branch para o repositório remoto, substituindo o histórico remoto com o seu histórico local.

### 5. O comando git pull é usado para buscar e incorporar mudanças remotas de um repositório Git para o seu repositório local. Basicamente, ele combina dois comandos: git fetch para buscar as alterações remotas e git merge para incorporar essas alterações na sua branch local.

### 5A. Atualizar sua Branch Local
Para atualizar sua branch local com as mudanças mais recentes do repositório remoto (por exemplo, no GitHub, GitLab, Bitbucket), use o seguinte comando:
```
git pull origin nome-da-branch
```
Isso buscará as alterações da branch nome-da-branch do repositório remoto origin e tentará incorporá-las à sua branch local.

### 5B. Atualizar a Branch Atual
Se você está atualmente na branch que deseja atualizar e rastrear, você pode simplesmente usar:
```
git pull
```
Isso fará o git pull da branch atual configurada para rastrear seu equivalente remoto.
