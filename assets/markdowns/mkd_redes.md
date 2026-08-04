### 🖥️ Visualizar por consola dirección IP propia

Ver mi IP en WINDOWS:
```
ipconfig
```

Ver mi IP en LINUX:
```
ifconfig
```

---------------------

### 🌐 Direcciones IPv4

Una dirección IP (Internet Protocol) es un identificador numérico único que se asigna a cada dispositivo conectado a una red para que pueda comunicarse.

En IPv4 (la más común) tiene 32 bits y se escribe en notación decimal con puntos, dividida en 4 octetos (ej: 192.168.1.10). Cada octeto va de 0 a 255.

Prueba con esta versión limpia en markdown estándar:

| Valores posicionales binario | (256) | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| ---------------------------- | ----- | --- | --- | --- | --- | --- | --- | --- | --- |
| Posiciones de un octeto      | (9)   | 8   | 7   | 6   | 5   | 4   | 3   | 2   | 1   |

Tabla correspondiente a CIDR /24 (256 hosts):

|             | Octeto 1 | Octeto 2 | Octeto 3 | Octeto 4 |
| ----------- | -------- | -------- | -------- | -------- |
| **IP**      | 192      | 168      | 1        | 1        |
| **Binario** | 11000000 | 10101000 | 00000001 | 00000001 |
| **Máscara** | 255      | 255      | 255      | 0        |


---

### 🌐 CLASES de direcciones IPv4 (A, B y C)

El sistema de clases [CLASSFULL] divide el espacio de direcciones según el valor del primer octeto:

| Clase | Rango del 1.er octeto | Máscara por defecto | Bits de red / Bits de host | Nº aproximado de redes | Nº aproximado de hosts por red | Uso típico                      |
| ----- | --------------------- | ------------------- | -------------------------- | ---------------------- | ------------------------------ | ------------------------------- |
| **A** | 1 – 126               | 255.0.0.0 (/8)      | 8 bits red / 24 bits host  | 126 redes              | ~16,7 millones                 | Redes muy grandes<br>(regiones) |
| **B** | 128 – 191             | 255.255.0.0 (/16)   | 16 bits red / 16 bits host | ~16.384 redes          | ~65.534                        | Redes medianas<br>(oficinas)    |
| **C** | 192 – 223             | 255.255.255.0 (/24) | 24 bits red / 8 bits host  | ~2,1 millones          | 254                            | Redes pequeñas<br>(hogares)     |

### Explicación clara de cada columna:

- **Clase A**: el primer octeto identifica la red, los tres restantes los hosts.
- **Clase B**: los dos primeros octetos identifican la red.
- **Clase C**: los tres primeros octetos identifican la red.

_(Nota: hoy en día el sistema de clases está prácticamente abandonado en favor de CIDR, que permite crear MÁSCARAS DE RED DE LONGITUD VARIABLE)._

---

### 🌐 TIPOS de direcciones IPv4 (Privadas - Públicas)

Direcciones IP PRIVADAS:

| Clase | Rango de direcciones          | CIDR           | Hosts aproximados | Uso más común               |
| ----- | ----------------------------- | -------------- | ----------------- | --------------------------- |
| A     | 10.0.0.0 – 10.255.255.255     | 10.0.0.0/8     | 16.7 millones     | Redes grandes / empresas    |
| B     | 172.16.0.0 – 172.31.255.255   | 172.16.0.0/12  | 1 millón          | Redes medianas              |
| C     | 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 | 65.536            | Redes domésticas y pequeñas |
|       |                               |                |                   |                             |


---------------

### 📟 DHCP (Dynamic Host Configuration Protocol)

Es el protocolo que permite a un ROUTER o SERVIDOR asignar automáticamente direcciones IP (y otros parámetros de red como máscara, puerta de enlace y DNS) a los dispositivos de la red.

Ventajas:

- Evita conflictos de IP.
- Facilita la administración (no hay que configurar manualmente cada equipo).
- Las direcciones se prestan por un tiempo limitado (lease time). Suelen cambiar si el equipo administrador de IPs es reiniciado.

---

### 🧮 CIDR (Classless Inter-Domain Routing)

Es el sistema actual de asignación de direcciones que **sustituye a las clases A/B/C**.

En lugar de usar máscaras fijas, se indica el número de bits de red con una barra (/).

Aquí tienes la **tabla completa de CIDR** (de /0 a /32), con todos los tamaños de subred posibles en IPv4:

| CIDR | Máscara de subred | Direcciones totales | Hosts utilizables | Uso típico / Notas                      |
| ---- | ----------------- | ------------------- | ----------------- | --------------------------------------- |
| /0   | 0.0.0.0           | 4.294.967.296       | 4.294.967.294     | Toda Internet (casi nunca se usa)       |
| /1   | 128.0.0.0         | 2.147.483.648       | 2.147.483.646     | Muy raro                                |
| /2   | 192.0.0.0         | 1.073.741.824       | 1.073.741.822     | Muy raro                                |
| /3   | 224.0.0.0         | 536.870.912         | 536.870.910       | Muy raro                                |
| /4   | 240.0.0.0         | 268.435.456         | 268.435.454       | Muy raro                                |
| /5   | 248.0.0.0         | 134.217.728         | 134.217.726       | Muy raro                                |
| /6   | 252.0.0.0         | 67.108.864          | 67.108.862        | Muy raro                                |
| /7   | 254.0.0.0         | 33.554.432          | 33.554.430        | Muy raro                                |
| /8   | 255.0.0.0         | 16.777.216          | 16.777.214        | * (Clase A)                             |
| /9   | 255.128.0.0       | 8.388.608           | 8.388.606         |                                         |
| /10  | 255.192.0.0       | 4.194.304           | 4.194.302         |                                         |
| /11  | 255.224.0.0       | 2.097.152           | 2.097.150         |                                         |
| /12  | 255.240.0.0       | 1.048.576           | 1.048.574         | Rango privado 172.16.0.0/12             |
| /13  | 255.248.0.0       | 524.288             | 524.286           |                                         |
| /14  | 255.252.0.0       | 262.144             | 262.142           |                                         |
| /15  | 255.254.0.0       | 131.072             | 131.070           |                                         |
| /16  | 255.255.0.0       | 65.536              | 65.534            | * (Clase B)                             |
| /17  | 255.255.128.0     | 32.768              | 32.766            |                                         |
| /18  | 255.255.192.0     | 16.384              | 16.382            |                                         |
| /19  | 255.255.224.0     | 8.192               | 8.190             |                                         |
| /20  | 255.255.240.0     | 4.096               | 4.094             |                                         |
| /21  | 255.255.248.0     | 2.048               | 2.046             |                                         |
| /22  | 255.255.252.0     | 1.024               | 1.022             |                                         |
| /23  | 255.255.254.0     | 512                 | 510               |                                         |
| /24  | 255.255.255.0     | 256                 | 254               | * (Clase C)  **La más usada**           |
| /25  | 255.255.255.128   | 128                 | 126               |                                         |
| /26  | 255.255.255.192   | 64                  | 62                | Muy común en oficinas                   |
| /27  | 255.255.255.224   | 32                  | 30                |                                         |
| /28  | 255.255.255.240   | 16                  | 14                |                                         |
| /29  | 255.255.255.248   | 8                   | 6                 | Enlaces punto a punto pequeños          |
| /30  | 255.255.255.252   | 4                   | 2                 | Enlaces punto a punto <br>(muy usado)   |
| /31  | 255.255.255.254   | 2                   | 2*                | Enlaces punto a punto<br>(RFC 3021)     |
| /32  | 255.255.255.255   | 1                   | 1                 | Una sola dirección<br>(host específico) |

Ventajas de CIDR:

- Permite crear subredes del tamaño exacto que se necesita (subnetting).
- Ahorra direcciones IP.
- Es el estándar usado en Internet y en casi todas las redes actuales.

- Cuando calculamos los **hosts utilizables**, restamos estas dos direcciones que no pueden ser usadas por los hosts de la red:

1. **Dirección de red** (Network Address) → Es la primera dirección de la subred.
   Identifica a la propia red.
   Ejemplo: en 192.168.1.0/24 → 192.168.1.0
   
2. **Dirección de Difusión** (Broadcast) → Es la última dirección de la subred.
   Se usa para enviar paquetes a **todos** los dispositivos de esa red.
   Ejemplo: en 192.168.1.0/24 → 192.168.1.255
   
   Por lo tanto, una red por ejemplo de tipo 192.168.1.1/24, de 256 direcciones IP, tiene 254 utilizables.
   
#### ¿Cómo calcular el tamaño de una red por su valor CIDR /# ?

Fácil, solo hay que saber que la red más pequeña empieza por /32, y de ahí para abajo se van creando subredes más grandes con /31, /30, /29, etc.

Sabemos que la más pequeña (/32) tiene solo 1 dirección IP. Pues de ahí en adelante, se van duplicando exponencialmente como si se tratara de los valores del sistema binario:

| Hosts | 1   | 2   | 4   | 8   | 16  | 32  | 64  | 128 | 256 | 512 | 1024 |
|-------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|------|
| CIDR  | /32 | /31 | /30 | /29 | /28 | /27 | /26 | /25 | /24 | /23 | /22  |

_(Nota: los hosts utilizables es siempre el número total de hosts menos 2)._

_______________________

### 📬 ENVÍO DE PAQUETES EN UNA RED

Hay **varios tipos** según el destino del paquete. Los principales son estos:

|Tipo|Nombre en español|¿A quién llega?|Ejemplo|
|---|---|---|---|
|**Unicast**|Unidifusión|A **un solo** dispositivo|192.168.1.10|
|**Broadcast**|Difusión|A **todos** los dispositivos de la red|192.168.1.255|
|**Multicast**|Multidifusión|A un **grupo** de dispositivos|224.0.0.1 (todos los routers)|
|**Anycast**|Anycast|Al dispositivo **más cercano** del grupo|Se usa en DNS y CDNs|

---------------

### 🖥️ AJUSTES DE RED EN VIRTUAL BOX

Hay **varios

| Tipo de conexión                  | ¿Internet? | ¿Habla con el Host? | ¿Habla entre VMs? | Explicación breve                                                                            | Uso recomendado                              |
| --------------------------------- | ---------- | ------------------- | ----------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **NAT**                           | Sí         | Limitada            | No                | La VM sale a Internet usando la IP del host. El host no puede conectarse fácilmente a la VM. | Uso diario, navegar, actualizar paquetes     |
| **Adaptador puente**              | Sí         | Sí                  | Sí                | La VM se conecta directamente a la red física (como un PC más). Obtiene IP del router.       | Servidores, pentesting, pruebas de red real  |
| **Red interna**                   | No         | No                  | Sí                | Solo las VMs que están en la misma red interna se ven entre sí. El host no participa.        | Aislar VMs (ej. cliente ↔ servidor)          |
| **Adaptador sólo anfitrión**      | No         | Sí                  | Sí                | Crea una red privada entre el host y las VMs. Sin salida a Internet.                         | Laboratorio interno, desarrollo              |
| **Controlador genérico**          | Depende    | Depende             | Depende           | Permite usar controladores de red especiales (UDP Tunnel, VDE, etc.). Poco usado.            | Casos muy específicos / avanzados            |
| **Red NAT**                       | Sí         | Limitada            | Sí                | Igual que NAT pero permite que varias VMs se comuniquen entre ellas.                         | Varias VMs que necesitan Internet + hablarse |
| **Red en la nube (EXPERIMENTAL)** | Sí         | Depende             | Depende           | Conecta la VM a redes cloud (aún en fase experimental).                                      | Pruebas con nubes (poco estable)             |



