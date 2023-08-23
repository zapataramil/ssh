# SSH
### Configuracion de claves [SSH](https://es.wikipedia.org/wiki/Secure_Shell "Secure SHell") en servidores. En particular: servidor web github

<span style="color: blue"> SSH</span>:<span style="color: blue"> S</span>ecure <span style="color: blue"> SH</span>ell, es el nombre de un protocolo y programa de claves. Basado en Telnet, su configuración nos permite acceder de forma remota y mas segura a un servidor utilizando sistemas criptográficos para el cifrado de la información, tales como: RSA, DSA, ECDSA, EdDSA, Curvas elípticas.


### Caracteristicas

- Copia datos de forma segura
- Gestiona claves con el tipo de cifrado elegido


### Funcionamiento

 El servidor envia clave pública, si coincide con la clave privada se abre un canal donde la información es encriptada

### [RSA](https://es.wikipedia.org/wiki/RSA "Rivest, Shamir y Adleman")

Es un tipo de cifrado que se utiliza para las claves públicas. Es la más utilizada por su seguridad y soporte. Su seguridad se basa en la dificultad matemática para factorizar grandes números semiprimos. Su soporte se basa en su antigüedad y estar distribuido en muchos sistemas.

### Instalación de SSH por [Bash](https://es.wikipedia.org/wiki/Bash "Shell de Unix")

Se instala:

-     sudo apt-get install openssh-server

![](https://github.com/zapataramil/ssh/blob/main/src/img/instalacionSSH.png)

Se corrobora que esté en funcionamiento:

-     sudo systemctl enable ssh

![](https://github.com/zapataramil/ssh/blob/main/src/img/instalacionSSH2.png)

[Ver video ](https://www.youtube.com/watch?v=bjFfyyzIE5Y )


### Uso de SSH para Github
##### Cliente: Mi pc
##### Servidor: Github

1) Creo las claves pública y privada. Me pide el nombre del archivo para guardar la llave, si presiono sólo "enter" el nombre del archivo queda por defecto: "id_rsa"

-              ssh-keygen

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub1.png)

2) Para reforzar la seguridad me pide una contraseña, en caso de omitirla sólo presiono "enter".

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub2.png)

3) Se repite la contraseña.

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub3.png)

4) Las llaves ya fueron creadas, la pública (id_rsa.pub) y la privada (id_rsa).

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub4.png)

5) Accedo a la carpeta .ssh y listo las llaves creadas.

-              cd .ssh
-              ls

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub5.png)

6) Con el comando cat abro y copio la llave pública

-              cat id_rsa.pub

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub6.png)

7) Ingreso a Github, en settings, en "SSH and GPG keys" y presiono en "New SSH key".

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub7.png)

8) Agrego un título a la llave haciendo referencia a la terminal que uso y pego la llave pública copiada anteriormente.

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub8.png)

9) Verificación de que la llave pública es agregada en Github.

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub9.png)

10) Se genera el agente que va almacenar la llave privada.

-              eval $(ssh-agent -s)

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub10.png)

11) Agrego la llave privada.

-              ssh-add ~/.ssh/id_rsa

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub11.png)

12) Creo un repositorio vacio en Github.

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub12.png)

13) Creo la carpeta pruebas, accedo a ella y creo un repositorio local.

-              mkdir pruebas
-              cd pruebas
-              git init

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub13.png)

14) Agrego el repositorio remoto al local.

-              git remote add origin git@github.com:url de repositorio remoto

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub14.png)

15) Creo un archivo de texto "archivotexto".

-              cat > archivotexto

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub15.png)

16) Hago un stage all y un commit, luego pusheo al remoto.

-              git add --all
-              git commit -m "primer commit"
-              git push origin master

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub16.png)

17) Se pueden ver los cambios del push realizado.

![](https://github.com/zapataramil/ssh/blob/main/src/img/sshGithub17.png)
