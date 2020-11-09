<p align="center"><strong>Recompilação do Asterisk</strong></p>

A recompilação geralmente é utilizada quando queremos carregar algum módulo específico ou atualizar a versão do nosso Asterisk.
**Para isso:**

**1** - Navegue até o diretório com os arquivos do Asterisk, localizado em:
"**/etc/usr/src/asterisk***".

**2** - Digite "**./configure**" para realizar o procedimento de configuração de arquivos.

**3** - Digite "**make menuselect**" caso queira ativar ou desativar algum modulo do Asterisk, selecione "**Exit and Save**" ao terminar.

**4** - Digite "**make install**" para instalar as novas dependências.

**Obs:** **Não digite "make samples" ou seus arquivos de configuração serão sobrescritos.**

<hr>

<p align="center"><strong>Macro deprecated? E agora, Jubileu?</strong></p>

Recentemente, enquanto estudava Asterisk me deparei com um problema no momento de criação de uma funcionalidade de gravação de chamadas, na criação do código e no momento da ligação entre ramais recebi um aviso de que o macro estava deprecated. Macro ainda é bastante utilizado e apesar de o GoSub() ser indicado atualmente ainda não encontrei material que me auxiliasse na reprodução dessa funcionalidade utilizando-o.

A partir do Asterisk 16 o Macro não é mais carregado e para isso o usuário deve carrega-lo manualmente, para isso:

 1- Você deve carregar o módulo "app_macro.so" no menuselect do Asterisk e por fim recompila-lo (processo já detalhado aqui).

2 - Adicione o módulo em "/etc/asterisk/modules.conf":
 - Abra o arquivo .conf com seu editor favorito (vim, vi, nano, etc) e adicione a seguinte linha:  `load => app_macro.so`
 
 3 - Inicie a CLI do seu Asterisk e digite: **module load app_macro.so**

Pronto! Você já estará apto para utilizar a funcionalidade.

<hr>

<p align="center"><strong>Como manipular um servidor CentOS remotamente?</strong></p>

Por padrão quando vamos trabalhar com distribuições linux destinadas ao gerenciamento de servidores utilizamos clientes SSH (Secure Socket Shell).
Em ambientes Linux o cliente SSH mais popular é o PuTTY, é fácil na instalação e apenas uma linha de código no terminal nos permite estabelecer conexão com o nosso servidor remoto.
Porém, particularmente utilizo um software open-source chamado Remmina que apesar de desempenhar diversas funções é utilizado em ambientes Linux para realizar conexão via SSH, a seguir irei demonstrar como instala-lo e iniciar uma comunicação entre a máquina e um servidor.

1 - Clique no link abaixo e realize a instalação do Remmina de acordo com a distribuição Linux que você possuir:
https://remmina.org/how-to-install-remmina/ 

2 - Após instalado, inicie o Remmina, e clique no ícone de "+" onde você será levado a uma aba para registrar sua conexão.

3 - Na página de registro, segue a forma correta de preenchimento:
![Remmina](https://i.imgur.com/yGqWaMc.png)
**Grupo**: Nome ilustrativo da conexão.
**Protocolo**: SSH sempre (a menos que você deseje outro tipo de conexão).
**Servidor**: IP do seu servidor seguido da porta de conexão (por padrão a porta
utilizada é a 22).
**Nome do usuário**: Login da máquina que irá ser manipulada.
**Senha do usuário**: Senha da máquina que será manipulada.

Ao final, clique em Salvar e conectar e pronto, a conexão será estabelecida e você poderá manipular seu servidor a partir de qualquer ambiente Linux.


