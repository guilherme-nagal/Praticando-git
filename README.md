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

5° Desafio) Revertendo um commit.
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

6° Desafio) Resolvendo um conflito.
- Para isso simularemos um conflito no código, então pelo github iremos alterar o terceiro filme do arquivo index.html e será feito o commit, e pelo VScode iremos realizar uma alteração diferente no terceiro filme também e realizar o commit.
- Dessa forma terá um conflito no código, então daremos um pull no código para resolve-lo.
- Para fazer o pull podemos utilizar o "Source Control" do VScode ou pelo terminal.
  - VScode
  ![1](https://user-images.githubusercontent.com/64446302/192881161-a65da6c2-af3f-4728-933b-c0fa905aeccc.png)
  - Terminal
  ```
  git pull origin main
  ```
- Após ter dado um pull podemos olhar no arquivo index.html algo semelhante como a imagem a baixo
