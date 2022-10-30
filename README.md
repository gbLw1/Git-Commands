# ![Git](https://blog-geek-midia.s3.amazonaws.com/wp-content/uploads/2020/08/06103546/comandos-git.png)

## Essa documentação foi feita com a intenção de introduzir os [Comandos básicos](https://comandosgit.github.io/) em Git

 ---

# Sumário

  - [Começando do zero](#começando-do-zero)
  - [Trabalhando com Stash](#trabalhando-com-stash)
  - [Manipulação de commits](#manipulação-de-commits)
  - [Rollback de commits](#rollback-de-commits)
  - [Outros comandos](#outros-comandos)

 ---

# Começando do zero

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
  :orange_circle: **Obs.:** Não é necessário fazer os Passos [6](#6-sincronizando-com-o-repositório-remoto) e [7](#7-alterando-o-nome-da-branch-main).

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
      Esse é um outro modo de executar o commit, pulando a parte de [adicionar para o stage](#4-adicionando-ao-stage),  
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
  **Obs.:** Uma vez que foi aplicado o stash mais recente, não é possível ir para um stash antigo (stash checkout).  
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

# Manipulação de commits

  ### Verificando se há alterações pendentes
  ```
  git status
  ```
  Neste comando podemos verificar os estados da branch, que são:
  | :x: Untracked           | :white_check_mark: Stage       |
  |-------------------------|--------------------------------|
  | arquivos não rastreados | arquivos prontos para o commit |

 ---

  ### Visualizar histórico de commits
  ```
  git log
  ```
  Caso queira ver uma listagem mais simplificada, utilize o parâmetro : ``` --oneline ```

 ---

  ### Navegar até um commit específico
  ```
  git checkout <código do commit>
  ```
  **Obs.:** Para esse comando é necessário que **não haja modificações pendentes**, utilize o comando ``` git status ``` para verificar o stage.

 ---

  ### Voltar para o último commit
  ```
  git checkout <nome da branch>
  ```

 ---

# Rollback de commits

  ### Deletando todas as alterações
  ```
  git reset --hard
  ```

 ---

  ### Deletando todas as alterações e os Commits
  ```
  git reset --hard HEAD~1
  ```
  :red_circle: **Obs.:** o número após o "~" é a quantiade de commits afetados, se omitido será apenas o último commit.  
  Necessário fazer um push para atualizar a branch: ```git push -f```

 ---

  ### Deletando apenas o commit e mantendo as alterações
  ```
  git reset --soft HEAD~1
  ```
  :yellow_circle: **Obs.:** Esse comando deleta e volta o número de commits informado após o "~", mantendo todas as alterações em stage.

 ---

# Outros comandos

  ### Parar de trackear um arquivo / pasta específica
  ```
  git rm --cached <nome do arquivo / pasta>
  ```

 ---

  ### Removendo arquivos com alterações do stage
  ```
  git restore . --stage
  ```

 ---

# Blaw

  |                                                              |
  |--------------------------------------------------------------|
  | : ![xD](https://c.tenor.com/pcCWcPVLXqgAAAAM/tf2dance.gif) : |
