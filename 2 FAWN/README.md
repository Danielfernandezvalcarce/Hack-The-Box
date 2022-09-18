# MAQUINA VIRTUAL FAWN **HACK THE BOX**

En este README veremos la manera de conseguir superar el nivel **FAWN** del programa de aprendizaje de hackeo y pentesting de *HACK THE BOX* (En adelante HTB)

- Para empezar comenzaremos con los mismos pasos que en la maquina MEOW, conectarse a la VPN y acceder a la maquina(visitar respositorio "01 meow"), tambien comprobamos el Ping.

- Lanzamos los comandos *NMAP* y *NMAP -sV* para escanear los puertos abiertos del servidor, dandonos cuenta que el puerto abierto es el 21 que es al que normalmente se conecta el protocolo FTP.

- El protocolo FTP o Protocolo de transferencia de archivos (en inglés File Transfer Protocol o FTP) es un protocolo de red para la transferencia de archivos entre sistemas conectados a una red TCP (Transmission Control Protocol), basado en la arquitectura cliente-servidor. Desde un equipo cliente se puede conectar a un servidor para descargar archivos desde él o para enviarle archivos, independientemente del sistema operativo utilizado en cada equipo. El servicio FTP es ofrecido por la capa de aplicación del modelo de capas de red TCP/IP al usuario, utilizando normalmente el puerto de red 20 y el 21. Un problema básico de FTP es que está pensado para ofrecer la máxima velocidad en la conexión, pero no la máxima seguridad, ya que todo el intercambio de información, desde el login y password del usuario en el servidor hasta la transferencia de cualquier archivo, se realiza en texto plano sin ningún tipo de cifrado, con lo que un posible atacante puede capturar este tráfico, acceder al servidor y/o apropiarse de los archivos transferidos. Para solucionar este problema son de gran utilidad aplicaciones como SCP y SFTP, incluidas en el paquete SSH, que permiten transferir archivos pero cifrando todo el tráfico.
<img src = "https://i.gyazo.com/ea09a9d3c9a68745d5271e6250b702d0.png">

- Nos conectamos al servidor a traves del protocolo FTP, introduciendo el comando ftp + la IP a la que nos queremos conectar, usando el comando *ls* o *dir*, veremos los archivos dentro de la maquina virtual, en el cual se ve que tenemos la bandera dentro del archivo **flag.txt**, cogemos el archivo y lo llevamos a nuestro equipo, usando el comando *get* + el nombre del archivo,
<img src = "https://gyazo.com/9fcf65b20a35f51eba1a6e09ee1c070c.png">


- Como vimos anteriormente con el comando *cat* accedemos al interior del archivo txt y vemos la bandera.
<img src="https://i.gyazo.com/2f1e2d936eccb2a855545ac0ea3af5ff.png">

## PREGUNTAS

1.  What does the 3-letter acronym FTP stand for?

- file transfer protocol

2. Which port does the FTP service listen on usually?

- 21

3. What acronym is used for the secure version of FTP?

- sftp

4. What is the command we can use to send an ICMP echo request to test our connection to the target?

- ping

5. From your scans, what version is FTP running on the target?

- vsftpd 3.0.3

6. From your scans, what OS type is running on the target?

- unix

7. What is the command we need to run in order to display the 'ftp' client help menu?

- ftp -h

8. What is username that is used over FTP when you want to log in without having an account?

- anonymous

9. What is the response code we get for the FTP message 'Login successful'?

- 230

10. There are a couple of commands we can use to list the files and directories available on the FTP server. One is dir. What is the other that is a common way to list files on a Linux system.

- ls

11. What is the command used to download the file we found on the FTP server?

- GET

12. Submit root flag

- 035db21c881520061c53e0536e44f815