# Comandos do Git
Inicializar um repositório: `git init`

Ver o status dos arquivos do repositório: `git status`

Configurar o git na máquina, estando dentro do repositório:
- `git config --local user.name "Nome aqui"`
- `git config --local user.email "Email aqui"`

Para configurar para todos os repositórios, basta trocar `local` por `global`.
  
Adicionar um arquivo ao monitoramento do git:
- Para adicionar todos os arquivos da pasta atual: `git add .`
- Para adicinar um único arquivo: `git add nome do arquivo`

Salvar as alterações: 
-`git commit -m "Uma mensagem descritiva"`
- A flag `-m` serve para adicionar uma mensagem em relação ao commit.
- Lembrar sempre de adicionar uma mensagem que descreva a modificação que está sendo salva, mas de maneira sucinta.

Alguns termos que podem aparacer nas mensagens do `git status`:
- **HEAD**: Estado atual do código, ou seja, onde o Git os colocou
- **Working tree**: Local onde os arquivos estão armazenados e editados
- **index**: Local onde o Git armazena o que será *commitado*, ou seja, o local entre a *working tree* e o repositório Git em si.

Possíveis estados para os arquivos do repositório Git:
- **Untracked**: São os arquivos que ainda não estão sendo monitorados pelo Git.
- **Unmodified**: São os arquivos que estão sendo monitorados, mas ainda não sofreram nenhuma alteração.
- **Modified**: São os arquivos que estão sendo monitorados e sofreram alterações.
- **Staged**: Área em que estão os arquivos que já foram *commitados*.

Visualizar histórico de alterações: 
- `git log`
- O `git log` nos fornece as seguintes informações:
  - O **hash** do commit ou seja sua identificação.
  - A **branch** em que foi salva.
  - O **autor** e o email.
  - A **data** e o hora.
  - A **mensagem** do commit.
- Visualizar as informações em apenas uma linha: `git log --oneline`
- Para ver todas as informações, inclusive o que foi modificado: `git log -p`
- link onde dá para ver vários formatos de log: <a>devhints.io/git-log-format</a>.

Marcar arquivos para serem ignorados pelo Git:
- basta adicionar o nome do arquivo, pasta ou caminho no arquivo `.gitignore`.

Algumas dicas de quando *commitar*:
- **Nunca** *commitar* código que não funciona.
- Se um bug foi corrigido, é recomendado *commitar*.
- Se uma pequena *feature* foi adicionada, é válido *commitar*.

Para criar um repositório que só controla as alterações: `git init --bare`. Este é um repositório que não tem a cópia dos arquivos, ele serve apena como servidor para que outros membros da equipe sincronizem seus trabalhos, assim poupando espaço de armazenamento.

Para adicionar um repositório remoto ao projeto:
`git remote add nome-repositorio caminho/para/o/repositorio`.

Para clonar um repositório: `git clone caminho/para/o/repositorio/a/ser/clonado nome-pasta`.

Para enviar as alterações para o repositório remoto:
`git push nome-repositorio-remoto branch-origem`.

Se eu quiser que em todas as outras vezes que eu for subir as alterações nesse repositório, só digitar `git push`. Na primeira vez que eu enviar preciso colocar a flag `-u`. 

Para trazer os dados de um repositório remoto:
`git pull nome-repositorio-remoto branch-destino`.

Para criar uma nova branch: `git branch nome-branch`.

Para criar e já ir direto para nova branch: `git checkout -b nome-branch`.

Para alternar entre as branchs: `git checkout nome-branch`.

Para unir as alterações das outras branchs com a branch principal e gerar um merge commit: `git merge nome-branch-que-eu-quero-enviar-para-main`.

Para atualizar a main com os commits de outras branchs sem poluir o log: `git rebase nome-branch`.

Para desfazer as últimas alterações antes de adicionar: `git checkout -- arquivo`.

Para desfazer alterações que foram adicionadas para commit: `git reset HEAD arquivo`.

Para desfazer alterações que foram commitadas: `git revert hash-do-commit`.

Para salvar alterações temporariamente: `git stash`. Com `git stash list` consigo ver tudo o que está salvo temporariamente.

Para pegar a ultima alteração que foi salva temporariamente: `git stash apply`.

Para apagar a alteração da memória temporaria: `git stash drop`.

Para pegar e já remover ao mesmo tempo: `git stash pop`.

Para ir até um commit específico: `git checkout <hash>`. Qualquer alteração feita nele é perdida, a menos que eu crie uma nova branch, então o fluxo de trabalho continua a partir dessa nova branch.

Para ver as diferenças entre dois commits: `git diff <hash-first-commit>..<hash-last-commit>`.

Para ver as diferenças entre duas branchs: `git diff <branch1>..<branch2>`.

Como fazer um marco na minha aplicação TAG, um ponto que não muda mais: `git tag -a nome -m "mesagem se quiser"`

`git tag` lista as tags existentes.

Para enviar a tag para o repositório remoto: `git push nome nome-tag`.