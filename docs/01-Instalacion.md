# Instalación de Nessus Expert

---

## Descarga
https://www.tenable.com/downloads/nessus?loginAttempted=true

## Documentación para Instalar en Linux
https://docs.tenable.com/nessus/Content/InstallNessusLinux.htm

**Descarga del paquete:**
```text
curl --request GET \
  --url 'https://www.tenable.com/downloads/api/v2/pages/nessus/files/Nessus-10.12.1-el9.x86_64.rpm' \
  --output 'Nessus-10.12.1-el9.x86_64.rpm'
```

## Requisitos necesario para la instalación

| Componente | Linux | Windows |
|---|---|---|
| **Sistema operativo** | Kali Linux / Ubuntu 20.04+ / Debian 11+ | Windows 10 / 11 / Server 2016+ |
| **RAM** | 4 GB (8 GB recomendado) | 4 GB (8 GB recomendado) |
| **Almacenamiento** | 30 GB libres | 30 GB libres |
| **CPU** | 4 núcleos | 4 núcleos |
| **Navegador** | Chrome / Firefox | Chrome / Firefox / Edge |
| **Permisos** | Usuario con `sudo` | Administrador local |
| **Conectividad** | Internet para activación y plugins | Internet para activación y plugins |

---



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

---
  
## Pasos para la instalación en Rocky Linux 9 (o cualquier RHEL)

**Instalar el paquete descargado:**
```text
dnf install Nessus-<version number>-el8.x86_64.rpm
```

**Levantar el demonio nessusd:**
```text
systemctl start nessusd
```

**Acceder a la web de Tenable Nessus de forma remota:**
```text
https://<remote IP address>:8834
```

**Acceder a la web de Tenable Nessus de forma local:**
```text
https://localhost:8834
```

Configurar Tenable Nessus
---

Ingresamos en la web.

Nos pregunta que tipo de Nessus vamos a instalar, si queremos purchased una instancia qeu compramos, probar un trial del Expert o del Professional o si qeuremos el Essentials (gratis).

Si no tenemos un correo corporativo:
https://10minutemail.com/

Recibimos un codigo de activacion.

Creamos un usuario y contraseña.

Cuando inicializa actualiza los plugins, cada plugin sirve para hacer una prueba puntual. Hay que esperar que temine de instalarlos antes de continuar.


::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

Podemos crear un escaneo para cada uno de los targets que quieramos evaluar.

Vamos a "My Scans-->New Scan"
		Vamos a escanear la web de OWASP Juice Shop
		$sudo juice-shop
		http://127.0.0.1:42000
		
Dentro de targets coloco: 127.0.0.1
Luego damos: "Submit"
Luego seleccionamos el host que encontro y damos: "Run Scan"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

Politicas
Se utilizan para crear templates customizados, definiendo que acciones ejecutar durante el escaneo (tipo de escaneo que va a realizar).
Con el "Advanced Scan" podemos escanear incluyendo credenciales de usuario y contraseña del servidor.
	Settings/Credentials/Plugins
	
Servidor de prueba en la web:
https://juice-shop.herokuapp.com/#/



---










































---

Nessus Expert puede instalarse tanto en **Linux** como en **Windows**. El proceso de activación y configuración desde el navegador es idéntico en ambos sistemas — lo que cambia es la instalación del paquete y la gestión del servicio.
[nessus](https://www.tenable.com/products/nessus)
---

## Tabla de Contenidos

- [Requisitos previos](#requisitos-previos)
- [Obtener la licencia](#paso-1--obtener-la-licencia-de-activación)
- [Instalación en Windows](#-instalación-en-windows)
- [Paso común — Activación desde el navegador](#paso-común--activación-y-configuración-desde-el-navegador)
- [Verificar la instalación](#verificar-la-instalación)
- [Solución de problemas comunes](#solución-de-problemas-comunes)

---


## Paso 1 — Obtener la licencia de activación

Este paso es el mismo independientemente del sistema operativo.

### Opción A — Prueba gratuita de 7 días (recomendada para laboratorio)

Tenable ofrece una **trial gratuita de 7 días completos** de Nessus Expert sin necesidad de introducir datos de pago. Es la opción ideal para un entorno académico o para evaluar la herramienta:

1. Ir a [tenable.com/products/nessus](https://www.tenable.com/products/nessus).
2. Seleccionar **Nessus Expert** y hacer clic en **Try for free**.
3. Crear una cuenta con nombre, apellido y email.
4. Se recibirá un **Activation Code** por email en pocos minutos.
5. Anotar el código — se usará en el paso de activación desde el navegador.

A continuación se muestran las capturas realizadas:

![Instalacion Nessus](/assets/1_nesus.png)
![Instalacion Nessus](/assets/2_nessus.png)
![Instalacion Nessus](/assets/3_nessus.png)


> [!NOTE]
> Los 7 días comienzan a contar desde el momento en que se activa la licencia en Nessus, no desde el registro en la web. Una vez expirada la trial, Nessus pasa a modo limitado hasta que se active una licencia de pago. Para este laboratorio, 7 días son más que suficientes.

### Opción B — Licencia de pago

Para uso profesional o continuado, adquirir la licencia completa desde el portal de Tenable. El proceso de activación es idéntico al de la trial — solo cambia el código recibido.

---

## 🪟 Instalación en Windows

### Paso 2 — Descargar el instalador `.exe`

Desde la [página de descargas de Tenable](https://www.tenable.com/downloads/nessus), seleccionar la versión para **Windows (x86_64)**. Se descargará un archivo `.exe` del tipo:

```
Nessus-X.X.X-x64.exe
```

> [!TIP]
> Asegurarse de descargar la versión `x64` si el sistema es de 64 bits, que es lo habitual en cualquier equipo moderno.

---
![Instalacion Nessus](/assets/3_nessus.png)

### Paso 3 — Ejecutar el instalador

1. Hacer clic derecho sobre el archivo `.exe` descargado → **Ejecutar como administrador**.
2. Seguir el asistente de instalación: aceptar la licencia y dejar la ruta por defecto:
   ```
   C:\Program Files\Tenable\Nessus\
   ```
3. Al finalizar, el instalador arranca automáticamente el servicio **Tenable Nessus** en Windows.

![Instalacion Nessus](/assets/instalacion_8.png)
![Instalacion Nessus](/assets/instalacion_9.png)
![Instalacion Nessus](/assets/instalacion_10.png)
![Instalacion Nessus](/assets/instalacion_11.png)
![Instalacion Nessus](/assets/instalacion_12.png)
![Instalacion Nessus](/assets/instalacion_13.png)


> [!IMPORTANT]
> Si Windows Defender o el antivirus muestra una alerta durante la instalación, es un falso positivo habitual con herramientas de seguridad. Permitir la ejecución.

---

### Gestión del servicio en Windows


> [!NOTE]
> En Windows, Nessus se registra como un **servicio de Windows** que arranca automáticamente con el sistema. No es necesario abrirlo manualmente — basta con abrir el navegador y acceder a `https://localhost:8834` mientras el servicio esté corriendo.

![Instalacion Nessus](/assets/instalacion_29.png)

---

## Paso común — Activación y configuración desde el navegador

Una vez que el servicio está corriendo:

1. Abrir el navegador y acceder a: `https://localhost:8834`
2. Aceptar el aviso de certificado autofirmado — es normal, Nessus usa HTTPS con certificado propio.
3. En la pantalla de bienvenida, seleccionar **Nessus Expert**.
4. Introducir el **Activation Code** recibido por email.
5. Crear el usuario administrador (nombre de usuario y contraseña).
6. Esperar a que Nessus descargue e instale todos los plugins.

![Instalacion Nessus](/assets/instalacion_15.png)


> [!IMPORTANT]
> La descarga de plugins puede tardar entre **10 y 30 minutos** dependiendo de la conexión. No cerrar el navegador ni reiniciar el servicio durante este proceso.
>
> Si se interrumpe en **Windows**: reiniciar "Tenable Nessus" desde el Administrador de servicios.

![Instalacion Nessus](/assets/instalacion_16.png)
![Instalacion Nessus](/assets/instalacion_17.png)
![Instalacion Nessus](/assets/instalacion_18.png)
![Instalacion Nessus](/assets/instalacion_19.png)
![Instalacion Nessus](/assets/instalacion_21.png)


---

## Verificar la instalación

Una vez completada la descarga de plugins, confirmar que la versión activa es Expert:

```
Menú superior derecho → tu usuario → About
→ Debe mostrar: "Nessus Expert" con la fecha de expiración de la licencia
```

![Instalacion Nessus](/assets/instalacion_15.png)


---

← [Volver al índice](../README.md) · Siguiente: [Entorno de laboratorio →](04-entorno-laboratorio.md)
