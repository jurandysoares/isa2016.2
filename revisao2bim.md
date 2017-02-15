## Gerenciamento de pacotes
Comandos:
  * dpkg e apt (Ubuntu, Debian e derivados)
  
O que é um pacote?

### Instalação
`sudo apt install nome-do-pacote`

### Remoção
`sudo apt remove nome-do-pacote`
ou `sudo apt purge nome-do-pacote`

### Atualização de catálogo
`sudo apt update`

### Atualização de pacotes
`sudo apt upgrade`  

## Curingas e metacaracteres
É exibido, para cada pergunta, a saída esperada do comando que a responde.

  * Como listar todos os arquivos que terminam com `.conf` e se encontram no diretório `/etc`?
```
/etc/adduser.conf          /etc/hdparm.conf      /etc/lshell.conf              /etc/resolv.conf
/etc/ca-certificates.conf  /etc/host.conf        /etc/ltrace.conf              /etc/rsyslog.conf
/etc/debconf.conf          /etc/insserv.conf     /etc/mke2fs.conf              /etc/sensors3.conf
/etc/deluser.conf          /etc/kernel-img.conf  /etc/nsswitch.conf            /etc/sos.conf
/etc/ffserver.conf         /etc/ld.so.conf       /etc/overlayroot.conf         /etc/sysctl.conf
/etc/fuse.conf             /etc/libaudit.conf    /etc/pam.conf                 /etc/ucf.conf
/etc/gai.conf              /etc/logrotate.conf   /etc/popularity-contest.conf  /etc/updatedb.conf
```
  * Como listar todos os diretórios que terminando com `.d` e se encontram no diretório `/etc`? 
```
/etc/apparmor.d         /etc/init.d          /etc/modules-load.d  /etc/rc3.d      /etc/sensors.d
/etc/bash_completion.d  /etc/insserv.conf.d  /etc/Muttrc.d        /etc/rc4.d      /etc/sudoers.d
/etc/binfmt.d           /etc/ld.so.conf.d    /etc/pam.d           /etc/rc5.d      /etc/sysctl.d
/etc/cron.d             /etc/libpaper.d      /etc/profile.d       /etc/rc6.d      /etc/tmpfiles.d
/etc/depmod.d           /etc/logrotate.d     /etc/rc0.d           /etc/rcS.d      /etc/update-motd.d
/etc/dnsmasq.d          /etc/lshell.d        /etc/rc1.d           /etc/rsyslog.d
/etc/grub.d             /etc/modprobe.d      /etc/rc2.d           /etc/sane.d
```  
  * Como listar todos os diretórios que começam com `apache2` e se encontram no diretório `/usr/share/doc/`?
```
/usr/share/doc/apache2      /usr/share/doc/apache2-data
/usr/share/doc/apache2-bin  /usr/share/doc/apache2-utils
```  
  * Como listar todos os diretórios que começam com `rc`+`um dígito`+`.d` e se encontram no diretório `/etc/`?
```
/etc/rc0.d
/etc/rc1.d
/etc/rc2.d
/etc/rc3.d
/etc/rc4.d
/etc/rc5.d
/etc/rc6.d
```
## Redirecionamento

### Redirecionamento de saída destrutivo
```
echo bla bla > vixe.txt
cat vixe.txt
echo kkk > vixe.txt
cat vixe.txt
```
### Redirecionamento de saída NÃO destrutivo
```
echo la la la >> vixe.txt
cat vixe.txt
echo lol >> vixe.txt
cat vixe.txt
```

## Identificadores
 * O que é UID? Exemplifique? Qual o UID do usuário `root`?
 * O que é GID? Exemplifique? Qual o UID do grupo `root`?
 * O que é PID? Exemplifique? Qual o PID do processo `init`?
  * O que é PPID? Exemplifique? Qual o PPID do seu interpretador de comandos?
 
## Propriedade de arquivos e diretórios
 * Para arquivos: `ls -l /caminho/do/arquivo` (sem o **-d**)
 * Para diretórios: `ls -ld /caminho/do/diretório` (com o **-d**)

Perguntas:
 * Qual o dono, o grupo proprietário e as permissões dos arquivos abaixos?
  * `/etc/passwd`
  * `/etc/shadow`
  * `/etc/at.deny`
  * `/etc/sudoers`
  * `/usr/bin/passwd`
 * Qual o dono, o grupo proprietário e as permissões dos diretórios abaixos?
  * `/root`
  * `/tmp`
  * `/home`

## Usuários e grupos
 * Crie 3 usuários: fulano, beltrano e sicrano;
 * Crie 3 grupos: pedra, papel, tesoura;
 * Insira cada um dos usuários em 2 grupos, de tal sorte que cada grupo não pode ter mais que 2 membros.
 * Verifique que os comandos acima foram executados com sucesso (Confira o conteúdo dos arquivos `/etc/passwd` e `/etc/group`)
 * Crie 3 diretórios: `/tmp/a`, `/tmp/b` e `/tmp/c` (Ex.: mkdir /tmp/{a,b,c})
 * Atribua os diretórios criados a cada um dos usuários e a cada um dos grupos. Exemplo:
  * /tmp/a para fulano e pedra
  * /tmp/b para beltrano e papel
  * /tmp/c para sicrano e tesoura
  
## Permissões no Linux
Comandos: 
 * Modificar as permissões: `chmod`
 * Listar as permissões em arquivos: `ls -l`
 * Listar as permissões em diretórios: `ls -ld`

Perguntas:


### Set UID
 * Quais são as permissões do comando `passwd`? R.: `ls -l $(which passwd)`
 * Para que serve o **Set UID**?
 
### Set GID 
 * Quais são as permissões do comando `mlocate`? R.: `ls -l $(which mlocate)`
 * Para que serve o **Set GID**?

### Stick bit
 * Quais são as permissões do diretório `/tmp`? R.: `ls -ld /tmp`
 * Para que serve o **Stick bit**?
