# ```Git```

## Configurações de identificação do usuário
```
git config --global user.name "Seu Nome"
git config --global user.email "Seu Email"
```

---

## Inicializando um novo repositório
```
git init
```

---

## Verificando se há commits pendentes (estado da branch)
```
git status
```
Neste comando ele irá mostrar os arquivos com os seguintes status :
  - :red_circle: Vermelho : arquivos não rastreados (untracked)❌
  - :white_check_mark: Verde : arquivos prontos para o commit (stage)✅

---

## Adicionando ao stage
```
git add .
```
Adiciona os arquivos para a área de stage (o ponto significa todos os arquivos)

---

## Ignorando arquivos pendentes
```
git restore .
```
Caso queira ignorar arquivos em seu commit

---

## Fazendo um commit
```
git commit -m "msg"
```

---

## Histórico de commits
```
git log
```
Caso queira ver uma listagem mais simplificada, utilize o parâmetro : ``` --oneline ```

---

## Voltar o estado do último commit
```
git clean -df
git checkout -- .
```

---

## Remover o último commit
```
git reset --soft HEAD~1
```
Esse comando remove apenas o commit, mantendo as alterações do arquivo em stage

---

## Remover o commit e alterações do arquivo
```
git reset --hard HEAD~1
```
Esse comando remove o último commit e todas as alterações feitas no arquivo.

---

## Visualizar commits anteriores
**Para esse comando é necessário que não haja modificações pendentes, utilize o comando ``` git status ``` para verificar.**
```
git checkout <código do commit>
```
↑ Navega até o commit, alterando os arquivos temporariamente

```
git checkout <nome da branch>
```
↑ Volta para o último commit

---

## Associação de um repositório remoto a um repositório local
```
git remote add origin <URI>
```
"origin" sendo o apelido do repositório e URI é o link para o repositório

---

## Subindo o repositório local para o GitHub
```
```


:thumbsup: 👍