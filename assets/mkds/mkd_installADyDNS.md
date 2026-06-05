------------------
- Tags:
--------------------
Para que **Windows Server 2016** funcione como [[05.01 🖥️ DC (Domain Controller - Controlador de dominio)]] (DC), es necesario instalar [[Active Directory Domain Services]] (AD DS). Este servicio permite la administración centralizada de **usuarios, equipos y políticas de seguridad** dentro de una red empresarial.

Además, se debe instalar el **Servidor DNS**, ya que [[Active Directory]] depende de [[01🚢DNS🌍]] para la resolución de nombres dentro del dominio. En este apartado, configuraremos ambos servicios y promocionaremos el servidor como [[05.01 🖥️ DC (Domain Controller - Controlador de dominio)]], creando un nuevo dominio para la red corporativa.

## 🔹 3.1 Agregar el rol de Active Directory y DNS

➢ Abriremos el **Administrador del Servidor** (si aún no está abierto).
➢ Hacemos clic en "**Administrar**" (arriba a la derecha) y seleccionamos "**Agregar roles y características**".

![[Pasted image 20250330233037.png]]

➢ Se abrirá el asistente. Hacemos clic en **Siguiente** hasta llegar a "**Seleccionar tipo de instalación**".

![[Pasted image 20250330233110.png]]

➢ Elegimos "**Instalación basada en características o roles**" y hacemos clic en Siguiente.

![[Pasted image 20250330233121.png]]

➢ Seleccionamos el servidor donde instalar el rol y hacemos clic en Siguiente.

![[Pasted image 20250330233144.png]]

➢ En la lista de roles, marcamos "**Servicios de dominio de Active Directory (AD DS)**".

![[Pasted image 20250330233202.png]]

➢ Aparecerá una ventana emergente. Hacemos clic en "**Agregar características**".
	○ Marcamos también "**Servidor DNS**", ya que Active Directory depende de DNS.

![[Pasted image 20250330233240.png]]
![[Pasted image 20250330233249.png]]

➢ De nuevo, hacemos clic en "**Agregar características**".
	○ Hacemos clic en **Siguiente** > **Siguiente** > **Instalar** y esperar a que termine la instalación.

![[Pasted image 20250330233324.png]]

![[Pasted image 20250330233333.png]]

![[Pasted image 20250330233342.png]]

![[Pasted image 20250330233357.png]]

![[Pasted image 20250330233410.png]]

➔ La instalación del Rol del Active Directory a terminado correctamente.

