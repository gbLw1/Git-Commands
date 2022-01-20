# ![Git](https://blog-geek-midia.s3.amazonaws.com/wp-content/uploads/2020/08/06103546/comandos-git.png)

## Essa documentação foi feita com a intenção de introduzir os [Comandos básicos](https://comandosgit.github.io/) em Git

# Começando do zero

## Configurações de identificação do usuário
```
git config --global user.name "Seu Nome"
git config --global user.email "Seu Email"
```

## Inicializando um novo repositório
```
git init
```

## Criando o arquivo README.md
```
echo "# README" >> README.md
```

## Adicionando ao stage
  ``` git add README.md ```

  ou

``` git add . ```

  Para adicionar todos os arquivos pendentes

## Fazendo o commit
```
git commit -m "msg"
```

## Commit direto
Esse é um outro modo de executar o commit, pulando a parte de adicionar para o stage, basta adicionar o parâmetro : ``` -a ```
```
git commit -a -m "msg"
```

## Subindo o repositório local para o GitHub
```
git push -u 
```


---


# Comandos Adicionais

## Verificando se há commits pendentes
```
git status
```
  Neste comando podemos verificar o estado da branch 
|:red_circle: Untracked|:white_check_mark: Stage|
|----------------------|------------------------|
|arquivos não rastreados|arquivos prontos para o commit|

---

## Visualizar commits anteriores
  Para esse comando é necessário que **não haja modificações pendentes**, utilize o comando ``` git status ``` para verificar o stage.
  #### Navegar até o commit, alterando os arquivos temporariamente ↓
```
git checkout <código do commit>
```

  #### Voltar para o último commit ↓
```
git checkout <nome da branch>
```

---

## Ignorando arquivos pendentes
```
git restore .
```
  Use o parâmetro ``` --stage ``` para remover os itens adicionados ao stage (não será feito o commit).

---

## Histórico de commits
```
git log
```
  Caso queira ver uma listagem mais simplificada, utilize o parâmetro : ``` --oneline ```

---

## Voltando o estado do último commit
```
git clean -df
git checkout -- .
```
  As modificações do arquivo serão alteradas para a versão do último commit, tudo será desfeito.

---

## Removendo o último commit
```
git reset --soft HEAD~1
```
  Esse comando remove **apenas o commit**, mantendo as alterações do arquivo em stage

---

## Removendo o commit e alterações do arquivo
```
git reset --hard HEAD~1
```
  Esse comando remove o **último commit e todas as alterações** feitas no arquivo.

---

# Clonando um repositório remoto
```
git clone <URI>
```

---

:thumbsup: