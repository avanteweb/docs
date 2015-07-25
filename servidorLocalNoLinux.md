#Como instalar LAMP (acrônimo de Linux+Apache+MySQL+PHP) no Ubuntu

##Instalando o Apache:

Primeiro devemos fazer um update no sistema, para isso abrimos o terminal e digitamos: 
`sudo apt-get update`

Feito isso instalamos então o Apache com o seguinte comando:
`sudo apt-get install apache2` 
	
Para saber se seu Apache foi instalado com sucesso abra o seu navegador e digite: `http://localhost/` caso abra uma pagina escrito “Apache2 Ubuntu Default Page”, parabéns seu Apache foi instalado com sucesso.

##Instalando o MySQL

Para instalar o MySQL abra o terminal e digite:
`sudo apt-get install mysql-server libapache2-mod-auth-mysql php5-mysql`

Durante a instalação do MySQL irá pedir para definir uma senha de root(nossa sugestão 
é que sempre coloque uma senha que você irá lembrar). 
Após instalado o MySQL, devemos  ativá-lo com o seguinte comando:
`sudo mysql_install_db`

Em seguida o terminal irá pedir sua senha atual de root, é só digitar a sua senha que você definiu na 
instalação do MySQL.
Após isso, irá aparecer uma mensagem perguntando se você deseja alterar a sua senha  de root. escolha `N`.
No final, o MySQL irá recarregar e implementar as novas alterações.

Aparecerão 4 perguntas seguidas na tela do seu terminal, escolha `Y` para todas.
Seu MySQL está instalado!

##Instalando o PHP

Para instalar o PHP abra o terminal e digite:
`sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt`

Aparecerão 2 perguntas, responda `Y` para todas e o PHP será instalado.

Após isso digitamos o seguinte comando:
`sudo nano /etc/apache2/mods-enabled/dir.conf`
	
Feito este commando irá aparecer uma tela no seu terminal na qual você devera adicionar o index.php para o inicio de arquivos no índice, fazemos isso da seguinte maneira adicionando o index.php em primeiro como no exempĺo:
<IfModule mod_dir.c>
	DirectoryIndex `index.php` index.html index.cgi index.pl index.php index.xhtml index.htm
</IfModule>

###Módulos PHP

O PHP  tem uma variedade de bibliotecas e módulos úteis que você pode adicionar em seu servidor virtual. Você pode ver as bibliotecas que estão disponíveis com este seguinte comando:  
`apt-cache search php5`

O terminal exibirá a lista de módulos que podem ser adicionados:
- `php5-cgi` - do lado do servidor, a linguagem de script embutida no HTML (binário CGI)
- `php5-cli` - de linha de comando intérprete para a linguagem de script php5
- `php5-common` - arquivos comuns para pacotes construídos a partir da fonte php5
- `php5-curl` - módulo CURL para php5
- `php5-dbg` - símbolos de depuração para PHP5
- `php5-dev` - Arquivos para PHP5 desenvolvimento do módulo
- `php5-gd` - módulo GD para PHP5
- `php5-gmp` - módulo GMP para php5
- `php5-ldap` - módulo para php5 LDAP
- `php5-mysql` - módulo MySQL para php5
- `php5-ODBC` - módulo ODBC para php5
- `php5-pgsql` - módulo PostgreSQL para php5
- `php5-pspell` - módulo pspell para php5
- `php5-recode` - módulo recode para php5
- `php5-snmp` - módulo SNMP para php5
- `php5-sqlite` - módulo SQLite para php5
- `php5-tidy` - módulo tidy para php5
- `php5-xmlrpc` - módulo XML-RPC para php5
- `php5-xsl` - módulo XSL para php5
- `php5-adodb` - Extensão otimizar a biblioteca de abstração de banco de dados ADOdb
- `php5-auth-pam` - A extensão PHP5 para autenticação PAM
[...]

Uma vez que você decidir instalar o módulo, digite:
`sudo apt-get install nome-do-módulo`
Você pode instalar várias bibliotecas de uma vez separando o nome de cada módulo com um espaço.

Reinicie o Apache para que todas as alterações entrem em vigor:
`sudo apache2 serviço restart`

###Como instalar o phpMyAdmin no Ubuntu

Para instalar o phpmyadmin é só digitar o comando: 
`sudo apt-get install apache2-utils phpMyAdmin`

Durante a instalação, phpMyAdmin o guiará através de uma configuração básica. Siga estes passos:
-Selecione Apache2 para o servidor
-Escolha YES quando perguntado sobre a possibilidade de configurar o banco de dados para phpmyadmin com dbconfig-comum
-Digite sua senha MySQL quando solicitado
-Digite a senha que você deseja usar para entrar no phpmyadmin

Depois de concluída a instalação, adicione o phpMyAdmin para a configuração do apache:
`sudo nano /etc/apache2/apache2.conf`

cole o seguinte comando:
`Include /etc/phpmyadmin/apache.conf`

Depois disso reinicie o seu servidor com o comando:
`sudo service apache2 restart`

Adicione a configuração do phpMyAdmin para o arquivo:
`Include /etc/phpmyadmin/apache.conf`

Reinicie o Apache:
`sudo service apache2 restart`
