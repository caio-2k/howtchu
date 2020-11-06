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
