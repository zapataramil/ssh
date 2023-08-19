# SSH
### Configuracion de claves [SSH](https://es.wikipedia.org/wiki/Secure_Shell "Secure SHell") en servidores. En particular: servidor web github

<span style="color: blue"> SSH</span>:<span style="color: blue"> S</span>ecure <span style="color: blue"> SH</span>ell, es el nombre de un protocolo y programa de claves. Basado en Telnet, su configuración nos permite acceder de forma remota y mas segura a un servidor utilizando sistemas criptográficos para el cifrado de la informacion, tales como: RSA, DSA, ECDSA, EdDSA, Curvas elípticas.


### Caracteristicas

- Copia datos de forma segura
- Gestiona claves con el tipo de cifrado elegido

-     **completaaar**

### Funcionamiento

 El servidor envia clave publica, si coincide con la clave privada se abre un canal donde la informacion es encriptada

### [RSA](https://es.wikipedia.org/wiki/RSA "Rivest, Shamir y Adleman")

Es un tipo de cifrado que se utiliza para las claves publicas. Es la mas utilizada por su seguridad y soporte. Su seguridad se basa en la dificultad matematica para factorizar grandes numeros semiprimos. Su soporte se basa en su antiguedad y estar distribuido en muchos sistemas.

### Instalación de SSH por [Bash](https://es.wikipedia.org/wiki/Bash "Shell de Unix")

Se instala:

-     sudo apt-get install openssh-server

![](https://github.com/zapataramil/ssh/blob/main/src/img/instalacionSSH.png)

Se corrobora que este en funcionamiento:

-     sudo systemctl enable ssh

![](https://github.com/zapataramil/ssh/blob/main/src/img/instalacionSSH2.png)
