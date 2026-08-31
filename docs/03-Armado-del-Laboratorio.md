# Laboratorio de Pruebas

---

## Descripción

Todos los equipos son máquinas virtuales corriendo sobre un virtualizador tipo 2, en este caso Virtual Box.

Como se ha comentado en el paso de Instalación, Nessus se ha instalado en una máquina virtual con sistema operativo Rocky Linux 9, desde la que se lanzarán todos los escaneos. Los objetivos a escanear son 2, una VM con Ubuntu Linux 16.04.3 LTS y un Windows 10.

---

## Esquema

En el siguente esquema se puede ver como se creo una red NAT aislada del Host, cuyo rango es 10.0.1.0/24 llamada NatNetwork-NESSUS.
![Esquema-Laboratorio](/images/18_Nessus-Diagrama-Lab.png)

---

## Servidor de prueba en la web:

En caso de queres probar el escaneo web, se puede realizar a una web vulnerable echa para usarla de esa manera por lo que no es ilegal lanzar el escaneo.

https://juice-shop.herokuapp.com/#/

![Esquema-Laboratorio](/images/19_Nessus-WebVulnerable.png)

Como se puede apreciar es una web de OWASP

![Esquema-Laboratorio](/images/20_Nessus-WebVulnerable.png)