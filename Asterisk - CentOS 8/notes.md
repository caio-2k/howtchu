<center><strong>Como recompilar o Asterisk?</strong></center>

A recompilação geralmente é utilizada quando queremos carregar algum módulo específico ou atualizar a versão do nosso Asterisk.
**Para isso:**

**1** - Navegue até o diretório com os arquivos do Asterisk, localizado em:
"**/etc/usr/src/asterisk***".

**2** - Digite "**./configure**" para realizar o procedimento de configuração de arquivos.

**3** - Digite "**make menuselect**" caso queira ativar ou desativar algum modulo do Asterisk, selecione "**Exit and Save**" ao terminar.

**4** - Digite "**make install**" para instalar as novas dependências.

**Obs:** **Não digite "make samples" ou seus arquivos de configuração serão sobrescritos.**

<hr>
