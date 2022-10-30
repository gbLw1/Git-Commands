# ![Git](https://blog-geek-midia.s3.amazonaws.com/wp-content/uploads/2020/08/06103546/comandos-git.png)

## Essa documentação foi feita com a intenção de introduzir os [Comandos básicos](https://comandosgit.github.io/) em Git

# Começando do zero
  [Blaw](#blaw)
  ### 1. Configurações de identificação do usuário
  ```
  git config --global user.name "Seu Nome"
  git config --global user.email "Seu Email"
  ```

 ---

  ### 2. Inicializando um novo repositório
  ```
  git init
  ```

  - #### Já tem o repositório criado? Clone
  ```
  git clone <URI>
  ```
  Obs.: Não é necessário fazer os Passos [6](#6.sincronizando-com-o-repositório-remoto) e [7](#7.alterando-o-nome-da-branch-(main)).

 ---

  ### 3. Criando o arquivo README.md
  ```
  echo "# README" >> README.md
  ```

 ---

  ### 4. Adicionando ao stage
  ```
  git add <nome_arquivo>
  ```
  ou
  ```
  git add .
  ```
  para adicionar todos os arquivos pendentes

 ---

  ### 5. Fazendo o commit
  ```
  git commit -m "msg"
  ```
  - #### Stage + commit em um único comando
      Esse é um outro modo de executar o commit, pulando a parte de adicionar para o stage,  
      basta adicionar o parâmetro : ``` -a ```
  ```
  git commit -a -m "msg"
  ```

 ---

  ### 6. Sincronizando com o repositório remoto
  ```
  git remote add origin <URI>
  ```

 ---

  ### 7. Alterando o nome da branch (main)
  ```
  git branch -M main
  ```

 ---

  ### 8. Subindo o repositório local para o GitHub
  ```
  git push -u origin main
  ```

 ---

# Trabalhando com Stash

  ### Criando um stash
  ```
  git stash
  ```
  Guarda as últimas alterações em um stash local e retorna o estado do ultimo commit

 ---

  ### Criando um stash com descrição
  ```
  git stash push -m "msg"
  ```

 ---

  ### Aplicando um stash criado para a branch atual
  ```
  git stash apply
  ```
  Obs.: Uma vez que foi aplicado o stash mais recente, não é possível ir para um stash antigo (stash checkout).  
    Sendo necessário criar mais um stash para que consiga aplicar um específico com o comando:
  ```
  git stash apply <stash_index>
  ```

 ---

  ### Listando stashes
  ```
  git stash list
  ```

 ---

  ### Deletando um stash específico
  ```
  git stash drop <stash_index>
  ```

 ---

  ### Aplicando stash na branch atual e deletando o stash
  ```
  git stash pop
  ```
  Ou também pode selecionar um stash específico com o comando:
  ```
  git stash pop <stash_index>
  ```

 ---

  ### Limpando os stashes
  ```
  git stash clear
  ```

 ---

# Comandos Adicionais

  ## Verificando se há commits pendentes
  ```
  git status
  ```
  Neste comando podemos verificar os estados da branch, que são:
  | :red_circle: Untracked  | :white_check_mark: Stage       |
  | ----------------------- | ------------------------------ |
  | arquivos não rastreados | arquivos prontos para o commit |

 ---

  ## Visualizar histórico de commits
  ```
  git log
  ```
  Caso queira ver uma listagem mais simplificada, utilize o parâmetro : ``` --oneline ```

 ---

  ## Navegar até um commit específico
    Para esse comando é necessário que **não haja modificações pendentes**, utilize o comando ``` git status ``` para verificar o stage.
    ```
    git checkout <código do commit>
    ```

 ---

  ## Voltar para o último commit
    ```
    git checkout <nome da branch>
    ```

 ---

## Parar de trackear um arquivo / pasta específica
  ```
  git rm --cached <nome do arquivo / pasta>
  ```

 ---

## Ignorando arquivos pendentes
  ```
  git restore .
  ```
  Use o parâmetro ``` --stage ``` para remover os itens adicionados ao stage (não será feito o commit).

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
  Necessário fazer um push para atualizar a branch → ```git push -f```

 ---

 ---

  ### Blaw
  ![xD](https://c.tenor.com/pcCWcPVLXqgAAAAM/tf2dance.gif)
