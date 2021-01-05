# Linux

## Dicas gerais
* Para saber qual é o diretório atual: `pwd`
* Para excluir um diretório criado: `rm -r nomeDoDiretorio`
* Para saber qual sistema operacional o compytador está usando: `grep ^NAME= /etc/os-release`
* Para criar arquivos na linha de comando: `touch arquivo.txt`
* Pra matar processo: ps aux | grep rhythmbox
kill 13881 ([número do processo](https://superuser.com/questions/117913/ps-aux-output-meaning) visto no resultado do comando anterior, segunda coluna)
* Para copiar em usr/share/applications abrir terminal na pasta e digitar:
`sudo cp [local de origem] [local de destino]`
* This command will find all occurrences of "word" in all the files under the current directory (or subdrectories): 
`grep -r word *`
* Para imprimir em um arquivo tudo o que está nos subdiretórios 
`ls -R > filename1`
* Ver arquivos ocultos em uma pasta: Ctrl + H
* Pra colocar ícones na área de trabalho copia e cola de Arquivos > Other Locations > Computer > usr > share > applications
* Ctrl L mostra o caminho do arquivo selecionado
* Instalar programas: `sudo apt-get install nome-do-programa`

## Scripts e programas
* Extrair áudio YT: youtube-dl -x --extract-audio --audio-format mp3 https://youtu.be/MDwvyRlVovg
* [Tradutor CTRL ALT E +  CTRL SHIFT C + ALT TAB](https://crow-translate.github.io/#installation)
* [Inverter cores da tela](https://itectec.com/ubuntu/ubuntu-how-to-reverse-colors-for-the-current-window-in-gnome-shell/)
* Para deixar janelas de programas pretas no ubuntu, mudar o programa ubuntu.json de Yaru pra Yaru-dark
* Criar atalho de programa em qualquer lugar e depois copiar em usr/share/appications:
    * Dropbox no Linux:
  ```
  [Desktop Entry]
  Name=Dropbox
  GenericName=File Synchronizer
  Comment=Sync your files across computers and to the web
  Exec=dropbox start -i
  Terminal=false
  Type=Application
  Icon=dropbox
  Categories=Network;FileTransfer;
  Keywords=file;synchronization;sharing;collaboration;cloud;storage;backup;
  StartupNotify=false
  ```
  * OmegaT no Linux:
  ```
  [Desktop Entry]
  Name=OmegaT
  GenericName=Ferramenta de tradução
  Comment=Ambiente de tradução
  Exec=java -jar /home/sheilagomes/OmegaT_5.3.0_Beta_Linux_64/OmegaT.jar
  Terminal=false
  Type=Application
  Icon=omegat
  Categories=Translation;
  Keywords=file;translation;
  StartupNotify=false
```
* ImageMagick transparent background:
`convert image.gif -transparent white result.gif (or use result.png)`
* ImageMagick transparent background if not perfectly white:
`convert image.gif -fuzz 10% -transparent white result.gif`
* [Postgre](https://www.hostinger.com.br/tutoriais/instalar-postgresql-ubuntu)
* [Wine](https://www.edivaldobrito.com.br/versao-mais-recente-do-wine-no-ubuntu/)
* [Inicialização do repositório no Github](https://kbroman.org/github_tutorial/pages/init.html)
* [Instalar Java JDK](https://linuxize.com/post/install-java-on-ubuntu-18-04/)
* [Instalar Paint no Linux](https://www.vivaolinux.com.br/dica/Instalar-MS-Paint-no-Linux)
* [Discord](https://www.edivaldobrito.com.br/discord-no-ubuntu-debian-mint/)
* [A Beginner’s Guide to Linux Kernel Development (LFD103)](https://training.linuxfoundation.org/training/a-beginners-guide-to-linux-kernel-development-lfd103/)
* Workpaces:
  - pra colocar em um: super+shift+pgdown
  - pra mover entre workspaces: super+pgdown, super+pgup
* BD: `mysql -h localhost -u maria -p (senha do computador)`
* BD não funcionava, [testei e deu certo](https://cursos.alura.com.br/forum/topico-java-sql-sqlexception-access-denied-for-user-root-localhost-52498):
(Criar um novo usuário e dar permissão pra ele)
  CREATE USER 'finley'@'localhost' IDENTIFIED BY 'password';
  mysql> GRANT ALL PRIVILEGES ON *.* TO 'finley'@'localhost' WITH GRANT OPTION;
* [Abrir atalho no desktop](https://linuxconfig.org/how-to-create-desktop-shortcut-launcher-on-ubuntu-18-10-cosmic-cuttlefish-linux)
* [Quebrar senha de root no mysql no ubuntu](https://www.youtube.com/watch?v=3EzREzfobUw)
* [Recuperar senha root](https://sempreupdate.com.br/recuperar-a-senha-do-root-no-mysql/)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)