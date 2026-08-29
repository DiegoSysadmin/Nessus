# Instalación de Nessus Essential

Para instalar cualquiera de las versiones los pasos son los mismos, solo cambia en la etapa del registo y en la elección de la versión a instalar una vez ya instalado cuando accedemos desde la web.
El paso previo a la instalación es decidir qué verisión se utilizará, la gratuita para entornos reducidos y recomendada para estudiantes y entornos de laboratorio. O una versión paga como Nessus Professional o Expert, para empresas y con prestaciones avanzadas.
Para este laboratorio se utiliza Nessus Essential.

---

## 1.— Registro en la web para obtener el código de la licencia de activación

Accedemos a la [Web de Tenable](https://www.tenable.com/products/nessus) para registrarnos con nuestros datos. Nos va a pedir nombre, apellido y un email. En caso de querer instalar la versión Proffessional o Expert, se debe introducir un email empresarial y solicita algunos datos básicos de la empresa como el nombre, cantidad de empleados, teléfono.
![Instalacion Nessus](/images/01_Nessus-Registro.png)
---
## 2.— Descarga

https://www.tenable.com/downloads/nessus?loginAttempted=true

Hacemos clic en Download Now para poder descargar el producto.
![Instalacion Nessus](/images/02_Nessus-Registro.png)
![Instalacion Nessus](/images/03_Nessus-Descarga.png)
![Instalacion Nessus](/images/04_Nessus-Descarga.png)
![Instalacion Nessus](/images/05_Nessus-Descarga.png)

Es posible descargarlo para instalar en Linux o Windows. Ademas permite realizar un pull de docker, o acceder a un Appliance. En este caso vamos se utiliza la opción por línea de comandos con curl.
```Text
curl --request GET \
  --url 'https://www.tenable.com/downloads/api/v2/pages/nessus/files/Nessus-10.12.4-el9.x86_64.rpm' \
  --output 'Nessus-10.12.4-el9.x86_64.rpm'
```
![Instalacion Nessus](/images/07_Nessus-Curl.png)


Haciendo clic sobre Checksum podemos copiar el hash para comprobar la correcta descarga.
![Instalacion Nessus](/images/06_Nessus-Checksum.png)


---

## 3.- Instalación
Para instalar Nessus Expert en Rocky Linux nueve se siguen [estos pasos](https://docs.tenable.com/nessus/Content/InstallNessusLinux.htm)

### Pasos para la instalación en Rocky Linux 9 (o cualquier RHEL)

**Instalar el paquete descargado:**
```text
dnf install Nessus-<version number>-el8.x86_64.rpm
```
![Instalacion Nessus](/images/08_Nessus-Instalacion.png)

**Levantar el demonio nessusd:**
```text
systemctl start nessusd
```

**Verificamos que el servicio quede activo**
```text
systemctl status nessusd.service
```
![Instalacion Nessus](/images/09_Nessus-Instalacion.png)

**Acceder a la web de Tenable Nessus de forma remota:**
```text
https://<remote IP address>:8834
```

**Acceder a la web de Tenable Nessus de forma local:**
```text
https://localhost:8834
```

---

## 4.—  Activation Code

**Acceder a la web de Tenable Nessus de forma local:**
```text
https://localhost:8834
```
- Seguimos los pasos y elegimos la versión que vamos a utilizar.
- Introducimos nuestro mail para que nos llegue el código de activación.
- Nos llega un email con el Código de Activación.
![Instalacion Nessus](/images/10_Nessus-Activar.png)
![Instalacion Nessus](/images/11_Nessus-Activar.png)
![Instalacion Nessus](/images/12_Nessus-Activar.png)
![Instalacion Nessus](/images/13_Nessus-Activar.png)
![Instalacion Nessus](/images/14_Nessus-Activar.png)

> [!NOTA]
> Nota: Conservar el código en caso de necesitar reinstalar el producto.

## 5.- Acceso

- Creamos un usuario y contraseña.
- Cuando inicializa actualiza los plugins, cada plugin sirve para hacer una prueba puntual. Hay que esperar que temine de instalarlos antes de continuar.
- Podemos crear un escaneo para cada uno de los targets que quieramos evaluar.

---

### Politicas
Se utilizan para crear templates customizados, definiendo que acciones ejecutar durante el escaneo (tipo de escaneo que va a realizar). Con el "Advanced Scan" podemos escanear incluyendo credenciales de usuario y contraseña del servidor.
	Settings/Credentials/Plugins