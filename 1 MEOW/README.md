# MAQUINA VIRTUAL MEOW **HACK THE BOX**

En este README veremos la manera de conseguir superar el nivel **MEOW** del programa de aprendizaje de hackeo y pentesting de *HACK THE BOX* (En adelante HTB)

- Para empezar lo que tenemos que hacer es conectarnos a la maquina virtual que proporciona la plataforma, a través de su VPN, para lo cual abriremos la conexion y selecionaremos la ubicación del servidor al que queremos conectarnos y descargamos un archivo *(nombre)*.ovpn el cual guardaremos en nuestra carpeta de descargas

<img src="https://i.gyazo.com/6a71a0b2d0cbd54d60c74a78aab31654.png">

- A continuación abrimos un terminal integrado, y nos vamos a nuestra carpeta de descargas. en la cual encontraremos el archivo descargado anteriormente

<img src="https://i.gyazo.com/c991a00d1ef8ffb45868908a0df79bc0.png">

- Usando el comando *sudo openvpn (nombre del archivo).ovpn* iniciamos la conexion a traves de la VPN, en este paso hay que hacer incapié que no se debe cerrar el terminal, y debemos de abrir otro para seguir lanzando comandos.

<img src="https://i.gyazo.com/bc6e69002d38dce9bde529d503ccf948.png">
<img src="https://i.gyazo.com/d3657c66ca892cb27b4ed138844ee863.png"> 

- Una vez conectados a través de VPN iniciamos la maquina virtual y se nos mostrará una dirección IP, en nuestro caso será **10.129.22.61**
<img src="https://i.gyazo.com/ec9daff131063014a88f918a9a84cec0.png">

- Para comprobar si tenemos conexión con el servidor, lanzamos el comando *ping* + la IP a la que queremos acceder, en caso de tener conexión, nos saldrá algo así (Presionar Ctrl + C para terminar el comando).

<img src="https://i.gyazo.com/a35b52ec6de4b4b33d73c461aac26cf5.png">

- A continuación usaremos NMAP para lanzar un escaneo de los puertos.
- Lanzando el comando -sV que Interroga al conjunto de puertos abiertos detectados
para tratar de descubrir servicios y versiones en puertos
abiertos, nos devolverá que tiene un puerto abierto, el 23/tcp
<img src="https://i.gyazo.com/312bd777fe973381e6f5a693e5e8743b.png">

- A traves del protocolo **TELNET** (Teletype Network1​) es el nombre de un protocolo de red que nos permite acceder a otra máquina para manejarla remotamente como si estuviéramos sentados delante de ella. También es el nombre del programa informático que implementa el cliente. Para que la conexión funcione, como en todos los servicios de Internet, la máquina a la que se acceda debe tener un programa especial que reciba y gestione las conexiones. El puerto que se utiliza generalmente es el 23. Lanzando el comando telnet seguido de la ip nos conectaremos a el servidor.
<img src="https://i.gyazo.com/5e835cc79f1a8cad5ed99a37e7562228.png">

- Probamos varias contraseñas para el login, resultando que al final la correcta para la entrada es "root"

- Ahora mismo nos encontramos dentro de la maquina en la cual si lanzamos el comando *ls* encontraremos el archivo Flag.txt y el directorio snap, lanzando el comando *cat* + el nombre del archivo,podremos acceder a el interior del TXT coger la bandera e introducirla en la ultima pregunta.

<img src="https://i.gyazo.com/a675092239afc4ebe5c171d3be379100.png">

## PREGUNTAS

1. What does the acronym VM stand for? 

- Virtual Machine

2. What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell. 

- Terminal

3. What service do we use to form our VPN connection into HTB labs? 

- openvpn

4. What is the abbreviated name for a 'tunnel interface' in the output of your VPN boot-up sequence output? 

- tun

5. What tool do we use to test our connection to the target with an ICMP echo request? 

- ping

6. What is the name of the most common tool for finding open ports on a target? 

- nmap

7. What service do we identify on port 23/tcp during our scans?

- telnet

8. What username is able to log into the target over telnet with a blank password? 

- root

9. Submit root flag 

- b40abdfe23665f766f9c61ecba8a4c19