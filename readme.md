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

Para trazer os dados de um repositório remoto:
`git pull nome-repositorio-remoto branch-destino`.