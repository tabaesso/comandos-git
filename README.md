# 📓 GIT COMMANDS

- [Como contribuir?](CONTRIBUTING.md)
- [Do you speak English?](README.eng.md)

## Tópicos

<table>
  <tr>
    <th>Comandos</th>
    <th>O que faz?</th>
  </tr>
  <tr>
    <td><a href="#add">git add</a></td>
    <td>Colocar arquivos na fase de stagging</td>
  </tr>
  <tr>
    <td><a href="#status-log">git status log</a></td>
    <td>Ver o status das suas alterações</td>
  </tr>
  <tr>
    <td><a href="#commit">git commit</a></td>
    <td>Manipular alterações pós stagging</td>
  </tr>
  <tr>
    <td><a href="#push">git push</a></td>
    <td>Enviar alterações para o repositório remoto</td>
  </tr>
  <tr>
    <td><a href="#pull">git pull</a></td>
    <td>Baixar informações do repositório remoto para o local</td>
  </tr>
  <tr>
    <td><a href="#fetch">git fetch</a></td>
    <td>Atualizar referências</td>
  </tr>
  <tr>
    <td><a href="#branch-checkout">git branch/checkout</a></td>
    <td>Manipulação de branches e navegação entre branches</td>
  </tr>
  <tr>
    <td><a href="#mv-rm">git mv/rm</a></td>
    <td>Trabalhando com arquivos e diretórios</td>
  </tr>
  <tr>
    <td><a href="#merge">git merge</a></td>
    <td>Fazendo merge entre branches</td>
  </tr>
  <tr>
    <td><a href="#rebase">git rebase</a></td>
    <td>Reaplica commits em cima de determinada branch ou commit</td>
  </tr>
  <tr>
    <td><a href="#revert">git revert</a></td>
    <td>Como desfazer alterações</td>
  </tr>
  <tr>
    <td><a href="#reset">git reset</a></td>
    <td>Reseta o HEAD atual para o estado especificado</td>
  </tr>
  <tr>
    <td><a href="#more">outros</a></td>
    <td>Mais comandos úteis</td>
  </tr>
</table>

<h2 id="nivel-de-perigo">Nível de Perigo de Comandos</h2>
<ul>
  <li>Inofensivo: Não faz nenhum tipo de alteração no seu projecto apenas entrega informações.</li>
  <li>Atenção: Preste atenção nestes comandos, porque devem ser executados com plena consciência do que eles farão na sua estrutura git.</li>
  <li>Perigoso: Estes comandos podem alterar a estrutura de ficheiros do seu projecto e isso pode causar a perda de ficheiros e diretórios.</li>
</ul>

## Outros conceitos:
- [Git flow](git-flow.md)
- [Patterns git](patterns-git.md)
- [Rebase interativo](rebase-interativo.md)

<h2 id="add">git add - Colocar arquivos na fase de stagging - (Atenção)</h2>

  `git add . ` - adiciona todas alterações feitas na fase de stagging.<br>
  `git add file.txt` - adiciona file.txt na fase de stagging.<br>
  `git add *.js` - adiciona todos arquivos com a extensão .js para fase de stagging, para saber mais como selecionar vários arquivos de uma só vez de uma olhada em [wildcards](https://www.tecmint.com/use-wildcards-to-match-filenames-in-linux/).<br>
  `git add --patch` - vejo linha por linha da alteração e consigo selecionar o que quero adicionar ao commit.<br>

<h2 id="status-log">git status/log - Ver o estado das suas alterações - (Inofensivo)</h2>

  `git status` - vê estado dos commits.<br>
  `git status -s` - status resumido.<br>
  `git status --short` - status resumido.<br>
  `git log` - mostra lista de commits.<br>
  `git log --oneline` - mostra historico de commits em uma linha por commit.<br>
  `git log --abbrev-commit` - mostra historico de commits em uma linha por commit.<br>
  `git log --color` - mostra historico de commits e tenta colorir o output.<br>
  `git log --graph` - mostra historico em um grafico das branchs em modo texto.<br>
  `git log --pretty` - mostra historico e permite que sejam utilizados place holders para as informações dos commits.<br>
  `git log --pretty=oneline` - mostra o histórico de commits em uma linha por commit com o hash completo.<br>

<h2 id="commit">git commit - Manipular alterações pós stagging - (Atenção)</h2>

  `git commit -a` - commit direto, sem passar por stagging.<br>
  `git commit -m "Mensagem"` - commit passando pelo stagging com mensagem de alteração.<br>
  `git commit --amend` - adiciona alterações no commit anterior.<br>

<h2 id="push">git push - Enviar alterações para o repositório remoto - (Atenção)</h2>

  `git push origin master` - envia as alterações para o repositório na branch master.<br>
  `git push` - envia as alterações para o repositório na branch em que você está.<br>
  `git push --set-upstream origin new-branch` - faz push da nova branch e suas alterações.<br>
  `git push -u origin <nome_da_branch>` - faz push da branch (nova ou não) e suas alterações.<br>
  `git push --delete origin <nome_da_branch>` - remove do repositório online a branch desejada.<br>
  `git push origin --tags` - além do push normal eu preciso fazer push das tags também, para acrescentar uma tag no que foi commitado.<br>

<h2 id="pull">git pull - Baixar informações do repositório remoto para o local - (Atenção)</h2>

  `git pull origin` - baixa commits do repositório remoto.<br>
  `git pull` - baixa commits do repositório remoto (igual o de cima).<br>
  `git pull --rebase` - força rebase ao fazer pull.<br>
  `git pull origin master --allow-unrelated-histories` - Vai permitir que juntes dois repositórios com históricos de commits diferentes, exemplo: quando vc cria um novo repositório no Github e tem os arquivos README.md, LICENSE e no seu laptop existe já um repositório local com mais ficheiros e pretendes subir este repositório local para o Github, primeiro tens de juntar o repositório que está no Github com teu repositório local e sendo eles repositórios com históricos de commits diferentes vc precisa especificar a opção --allow-unrelated-histories quando fazer o git pull.<br>

<h2 id="fetch">git fetch - Atualizar referências - (Atenção)</h2>

  `git fetch origin` - atualiza as referências com um repositório remoto (busca branches etc).<br>
  `git fetch` atualiza as referências com um repositório remoto (busca branches etc) ||.<br>

<h2 id="branch-checkout">git branch/checkout - Manipulação de branches e navegação entre branches - (Atenção)</h2>

  `git branch <nome_da_branch>` - cria nova branch com o nome desejado.<br>
  `git branch` - lista as branches disponíveis no repositório local.<br>
  `git branch -d <nome_da_branch>` - remove branch do repositorio local.<br>
  `git checkout <nome_da_branch>` - navega para aquela branch.<br>
  `git checkout -b <nome_da_branch>` - cria nova branch e já faz checkout nela.<br>
  `git checkout -` - o git checkout - te leva a branch que você estava trabalhando antes de trocar de branch.<br>
  `git checkout HEAD~2` - move o HEAD para dois commits anteriores.<br>
  `git checkout -- <arquivo>` - recupera diretamente no working dir o arquivo desejado.<br>
  `git checkout --ours <arquivo_conflito>` - adiciona conteúdo sem modificação que conflitou.<br>
  `git checkout --theirs` <arquivo_conflito> - adiciona conteúdo em conflito na branch atual que estou.<br>
  `git checkout <versao>` - "travo" para usar aquele commit em específico.<br>

<h2 id="mv-rm">git mv/rm - Trabalhando com arquivos e diretórios - (Perigoso)</h2>

  `git mv <nome_atual_do_arquivo> <nome_novo_do_arquivo>` - renomeia um arquivo com um nome para um novo nome.<br>
  `git mv <arquivo_1> <arquivo_2> <arquivo_3> ... <diretorio_de_destino>` - move o arquivo_1, arquivo_2, arquivo_3 e mais outros para o diretório de destino. *Nota:* vc pode estudar sobre [wildcards](https://www.tecmint.com/use-wildcards-to-match-filenames-in-linux/) para conseguir selecionar um conjunto de arquivos sem a necessidade de escrever o nome de cada um deles. *Exemplo:* `git mv *.js SCRIPTS-JS/` esse comando vai copiar todos arquivos com a extensão **.js** para o diretório SCRIPTS-JS/.<br>
  `git rm <nome_do_arquivo>` - remove determinado arquivo do repositório local. *Nota:* vc pode eliminar mais do que um arquivo e podes também usar [wildcards](https://www.tecmint.com/use-wildcards-to-match-filenames-in-linux/) .<br>
  `git rm -r <nome_do_diretório>` - remove determinado todo diretório com seus arquivos e subdiretórios.<br>
  `git rm -r *` - Elimina todos os arquivos e subdiretórios apartir da sua localização actual quando executar este comando.<br> 

<h2 id="merge">git merge - Fazendo merge entre branches - (Atenção)</h2>

  `git merge <nome_da_branch>` - faz merge com a branch desejada.<br>
  `git merge <nome_da_branch> -no-ff` - faz merge com a branch deseja no modo 3-way.<br>
  `git merge -abort` - cancela um merge que eu havia feito.<br>

<h2 id="rebase">git rebase - Reaplica commits em cima de determinada branch ou commit - (Atenção)</h2>

  `git rebase <nome_da_branch>` - reaplica todos os commits na branch desejada.<br>
  `git rebase master -i` - mostra lista de commits e posso alterar ela para mudar o histórico e tudo, muito foda.<br>

<h2 id="revert">git revert - Como desfazer alterações  - (Perigoso)</h2>

  `git revert <hash>` - reverte as alterações de um commit específico e cria um novo commit.<br>
  `git revert` - não modifica histórico de commits, mas cria um novo commit com o inverso do commit desejado, ou seja, o resultado final é o commit anterior.<br>

<h2 id="reset">git reset - Reseta o HEAD atual para o estado especificado  - (Perigoso)</h2>

  `git reset HEAD~1 --hard` - descarta e elimina as alterações do último commit.<br>
  `git reset HEAD~2 <arquivo>` - restaura para o staging as alterações do arquivo desejado em dois commits atrás.<br>
  `git reset --mixed` - altera o staging e o repositório, mantém o working dir intacto. É o padrão e é útil nos casos que queremos desfazer partes das alterações e criar um novo commit em seguida.<br>
  `git reset --soft` - similar ao mixed, mas mantém o staging como está.<br>
  `git reset --hard` - desfaz tudo a partir de um commit específico.<br>

<h2 id="more">Outros - Mais comandos úteis do git</h2>

  `git tag <versao>` - cria uma tag com a versao desejada.<br>
  `git clone <repo> --depth` - quero o clone a partir de X commits.<br>
  `git clean -f` - remove untracked files<br>
  `git remote add origin <url_do_repositorio>` - Faz uma ligação com o seu repositório remoto e essa ligação será chamada *origin* note que o nome da ligação pode ser alterado e não ser necessariamente *origin*.<br>
  `git commit --author="Ms. Jane Codeldoe <Jane@Codeldoe.com>" -m "Jane wrote this I'm just committing"` - Muda o autor de um determinado commit
