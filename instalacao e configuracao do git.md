# Passos para instalação e configuração do Git no Linux (Segundo o Estúdio Avante)

* Primeiramente abra o terminal (ctrl+alt+T) e digite o comando 'sudo apt-get install git' (e caso você esteja utilizando o Fedora utilize 'yum install git') e insira a senha do seu computador;

* Após isto, é hora de cadastrar usuário e senha executando os serguintes comando no terminal 'git config --global user.name "Seu nome"' e 'git config --global user.email "seuemail@example.com"';

* Para verificar se as informações anteriores foram inseridas corretamente, execute o comando  'git config -- list' ;

* Obtendo uma chave  Git: Digite o comando 'ls -al ~/.ssh' para verificar se existe alguma chave existente. Isso fará com que apareça uma lista de arquivos e caso não apareça nenhum arquivo do tipo;

(id_dsa.pub
id_ecdsa.pub
id_ed25519.pub
id_rsa.pub)
sua chave não existe. Para gerá-la digite o comando 'ssh-keygen -t rsa -C "seuemail@example.com"'' e logo após entre com sua senha e confirme-a. Isso gerará uma chave que será inserida nas configurações de seu perfil no GitHub. Basta acessar no menu da esquerda o link SSH Keys clicar adicionar uma nova chave. Na caixa de texto Title, coloque o nome da máquina a qual você está realizando o processo de instalação do Git, na caixa de baixo, insira a chave (Copie do terminal ctrl+shift+C) e cole (ctrl+V) e por fim clique no botão add key. Um E-mail de verificação será enviado para sua conta de E-mail, basta clicar no link para autenticar sua chave;

* Feito isso é hora de Obter Repositórios. Caso seja o seu primeiro projeto use o comando 'git init' que criará um novo repositório vazio, caso o seu projeto já exista no servidor, basta clonar o projeto no diretório de trabalho digite o comando git clone + (o link ssh ou http do repositório que deseja clonar)+ o nome do diretório do projeto. Por exemplo 'git clone git@github.com:repositorio.git teste' repare que a palavra "teste" é o nome do diretório;

* Vamos deixar o terminal colorido para melhor visualização do ambiente de códigos? Digite o seguinte comando no terminal 
'gedit ~/.bashrc'. Após digitar este comando, vá até o final do código que aparecer no documento detexto que abrirá automaticamente após a parte do código que está escrita (fi fi [lá no final do código]) dê dois Enters e cole os seguintes comandos: 

' # Colors and Git
color=$'\e[1;32m'
path_color=$'\e[1;33m'
git_color=$'\e[1;36m'
normal_color=$'\e[m'
export GIT_PS1_SHOWDIRTYSTATE=1
export PS1='\[$color\]\u@\h \[$path_color\]\w$(__git_ps1 " \[$git_color\][%s]") \[$normal_color\]' '

* Salve o documento, saia do terminal e o execute novamente;

//Introduzir analogia para explicar melhor o que são remotes//

* Para o próximo passo, é necessário acessar sua conta do GitHub.com e criar um fork (cópia) do remote que você está trabalhando;

* Hora de criar Remotes. Para criar remotes, basta executar o comando 'git remote add (nome do remote) + (link ssh do remote)'.
Existem dois tipos de remotes o remote principal (Upstream) e o remote que é uma cópia do principal(Origin). Necessariamente, deve-se adicionar estes dois respectivos remotes basta executar os comandos 'git remote add + (nome do remote[use o nome origin para criar o remote do seu fork]) + (o link ssh do seu remote fork)' por exemplo git@github.com:seunomenogithub/docs.git e 'git remote add + (nome do remote[use o nome upstream para criar o remote principal]) + (link ssh do seu remote principal)';

* Feito isso digite o comando  'git remote -v'  para verificar se seus remotes foram criados corretamente.

* Referências deste documento :

(http://git-scm.com/book/pt-br/v1/Primeiros-passos-Configura%C3%A7%C3%A3o-Inicial-do-Git "Primeiros passos -Configuração Inicial do Git") 

(https://github.com/avanteweb/pontoubalab "Avante web/Ponto Ubalab")

(https://github.com/settings/ssh)

(http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

(http://answers.ros.org/question/87866/how-to-edit-the-bashrc-file/)
 