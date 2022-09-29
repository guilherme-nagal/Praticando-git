# Praticando git com [7DaysOfCode da Alura](https://7daysofcode.io/)

## Nesse desafio foram dados 7 desefios pela alura e iremos resolve-los juntos, além de ter mais alguns desafios proposto por mim.

### 1° Desafio) Criar um repositório do zero.
- Para isso basta clicar em "New"
![1](https://user-images.githubusercontent.com/64446302/192875512-997f4d02-867c-4e97-a19a-3d713f4c15ed.png)
- Então será pedido o nome do repositório, colocaremos como "Praticando-git", deixaremos o repositório publico e já adicionando o README.

### 2° Desafio) Criar os arquivos HTML e CSS no próprio github, além da pasta de imagens.
- Para esse desafio foi utilizado o [repositório de fabriciocarro](https://github.com/fabriciocarraro/7DaysOfCode-GitHub?utm_source=ActiveCampaign&utm_medium=email&utm_content=%237DaysOfCode+-+GitHub+2%2F7%3A+%F0%9F%91%A9%F0%9F%8F%BD%E2%80%8D%F0%9F%92%BB+Adicionando+um+projeto+ao+reposit%C3%B3rio&utm_campaign=%5BAlura+%237Days+Of+Code%5D%28GitHub+-+1%C2%AA+Ed+%29+Dia+2%2F7) para pegar esses arquivos.
- Para se criar um arquivo no github basta clicar em "Add file" e em "Create new file"
![1](https://user-images.githubusercontent.com/64446302/192877468-e19c1e31-301c-4636-a2e8-2928d324e2ef.png)
- Então basta colocar o nome dos arquivos, "index.html" e "style.css", e adicionar o código copiado. Para as imagens ao invés de clicar em "Create new file" clicar em "Upload files" e upar as imagens baixadas em sua máquina.

### 3° Desafio) Clonar o seu repositório.
- Para fazer isso devemos copiar a url do repositório, pode ser pego em "Code".
![1](https://user-images.githubusercontent.com/64446302/192878168-f2e5648e-a9cc-4aeb-a09f-1d5d48a96852.png)
- Então basta entrar na pasta desejada pelo terminal e digitar o seguinte comando:
```
git clone <url_repositorio>
```

### 4° Desafio) Realizar um commit pelo VScode.
- Com o nosso repositório em nossa máquina podemos abri-lo no VScode e alterar o arquivo index.html, as alterações será adicionar o título de 3 filmes diferentes, sua sinopse e uma imagem.
- Após fazer isso aparecerá uma notificação em "Source Control", basta clicar nessa aba, adicionar um comentário e realizar o commit.
![2](https://user-images.githubusercontent.com/64446302/192879024-9b7c2ac8-bf34-4c8a-b97f-80709df124ad.png)

### 5° Desafio) Revertendo um commit.
- Para isso iremos realizar um commit com algum erro, tirando alguma tag de fechamento de "div".
- Após ser feita essa inserção de um erro iremos querer reverte-lo, para isso temos que pegar o histórico de commits feitos. Então iremos usar o seguinte comando:
```
git log --oneline
```
  - O parâmetro `--oneline` mostra os commits de uma forma simplificada.
- Como queremos reverter o último commit, pegaremos a hash desse último commit e então digitar o seguinte comando:
```
git revert <hash_commit>
```
- Dessa forma revertendo o commit informado.

### 6° Desafio) Resolvendo um conflito.
- Para isso simularemos um conflito no código, então pelo github iremos alterar o terceiro filme do arquivo index.html e será feito o commit, e pelo VScode iremos realizar uma alteração diferente no terceiro filme também e realizar o commit.
- Dessa forma terá um conflito no código, então daremos um pull no código para resolve-lo.
- Para fazer o pull podemos utilizar o "Source Control" do VScode ou pelo terminal.
  - VScode
  ![1](https://user-images.githubusercontent.com/64446302/192881161-a65da6c2-af3f-4728-933b-c0fa905aeccc.png)
  - Terminal
  ```
  git pull origin main
  ```
- Após ter dado um pull podemos olhar no arquivo index.html algo semelhante como a imagem a baixo.
![1](https://user-images.githubusercontent.com/64446302/192882113-e7c2f312-d615-48ee-8052-9ca875d84c6f.png)
- Mostrando qual parte do códgio apresentou conflito, então para resolver basta apagar o código que não se deseja e manter o que se deseja e então realizar o commit.

### 7° Desafio) Criar um gitignore.
- O arquivo `.gitignore` serve para não adicionar alguns arquivos no commit. Existem alguns arquivos que não queremos que sejam commitados, como por exemplo alguns arquivos de configurações.
- Então para esse desafio iremos criar um arquivo `config` e iremos adiciona-lo ao arquivo `.gitignore`, e também iremos modificar o arquivo `index.html`.
- Agora iremos dar um commit.
```
git add .
git commit -m "Atualizando o arquivo index.html sem adicionar o arquivo de configuração"
git push origin main
```
  - Dessa forma estaremos adicionando todos os arquivos ao commit e commitando com uma mensagem e depois enviando para o repositório remoto.
- Se olharmos o repositório no github iremos ver que não foi adicionado o arquivo de configuração e o arquivo `index.html` foi atualziado.

### 8° Desafio) Criar uma branch de desenvilvimento.
- Branchs serve para temos diferentes versões do código, dessa forma conseguimos trabalhar no código sem afetar o código em produção.
- Para cirar uma branch podemos digitar um dos seguintes códigos:
```
git branch desenvilvimento
```
  - Criando a bransh de desenvolvimento porém continuará na branch main
  - Para se mudar para ela devemos digitar o comando:
    ```
    git checkout desenvolvimento
    ```
```
git checkout -b desenvolvimento
```
  - Criando a branch de desenvolvimento e mudando para ela.
- Por fim iremos envia-la para o repositório remoto.
```
git push origin desenvolvimento
```

### 9° Desafio) Fazer um merge.
- Para fazer um merge primeiro iremos, na branch de desenvolvimento, modificar o arquivo de `index.html` adicionando um quarto filme. E então faremos um commit.
- Agora se mudarmos para a branch main veremos que essa alteração não está nessa bransh, pondo ver difernetes versões do código.
```
git checkout main
```
- Após isso faremos um merge. Para fazer o merge primeiro entraremos na branhch main e então fazer o merge.
```
git merge desenvolvimento
```
- Quando fizermos isso vermos que o código que o código da branch desenvolvimento está na branch main.
- Por fim basta dar um push.

### 10° Desafio) Fazer um stash.
- O `stash` serve para salvar o código para depois sem dar um commit, pois um commit só é recomendado dar quando o código está funcionando. Caso não tenha terminado seu código mas precisa parar de trabalhar nele, podemos usar o `stash` para salvar ele para depois.
- Para isso iremos alterar o arquivo index.html e digitar o comando:
```
git stash
```
- Dessa forma as modificações feitas serão salvas sem um commit. E caso se queira voltar a trabalhar nesse código podemos ver a lista de stash com o comando:
```
git stash list
```
- Com essa lista gerada pegaremos o index da stash desejada e digitaremos:
```
git stash pop <index_stash>
```
  - O `git stash pop` faz com que pegamos a stash informada e apagamos ela da lista de stashs.
- Caso queiramos apenas pega-la sem apaga-la podemos digitar:
```
git stash apply <index_stash>
```
- E caso apenas queiramos apaga-la da lista, sem pegar, digitaremos:
```
git stash drop <idex_stash>
```

### 11° Desafio) Criar uma tag.
- Uma tag serve para marcarmos versões do código.
- Iremos criar uma tag para a versão atual do projeto.
- Para isso iremos digitar o comando:
```
git tag -a v0.1.0 -m "Primeira versão do projeto"
```
  - O paramentro `-a` indica que estamos adicioando uma tag.
  - E o `v0.1.0` é o nome da tag.
- Poedmos vizualizar as tags criadas com o comando:
```
git tag
```
- Agora podemos enviar essa tag para o nosso repositório remoto.
```
git push origin v0.1.0
```

### 12° Desafio) Juntar commits.
- Para isso iremos fazer 3 commits qualquer.
- Após ter feito esses commits iremos junta-los em um só.
```
git rebase -i HEAD~3
```
  - O parâmetro `-i` indica que iremos fazer um rebase de forma interativa.
  - O `HEAD` indica que estamos no código atual, na branch atual.
  - E o `~3` indica que quremos os 3 últimos commits.
- Após fazer isso irá aparecer algo como:
```
pick <hash_commit1> <message_commit1>
pick <hash_commit2> <message_commit2>
pick <hash_commit3> <message_commit3>
```
- Para juntar iremos colocar.
```
pick <hash_commit1> <message_commit1>
s <hash_commit2> <message_commit2>
s <hash_commit3> <message_commit3>
```
