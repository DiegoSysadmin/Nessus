# Laboratorio de Pruebas

---

## Descripción

Todos los equipos son máquinas virtuales corriendo sobre un virtualizador tipo 2, en este caso Virtual Box.

Como se ha comentado en el paso de Instalación, Nessus en su versión Expert se ha instalado en una máquina virtual con sistema operativo Rocky Linux 9, desde la que se lanzarán todos los escaneos.

Para poder escanear más de un sistema operativo, se armó un laboratorio con un servidor Ubuntu Linux y un Windows 10.

---

## Esquema

![Esquema-Laboratorio](/images/18_Nessus-Diagrama-Lab.png)


```
┌────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                  Red Interna / NAT Network                   │                                     │
│                       192.168.1.0/24                         │                                     │
│                                                              │                                     │
│  ┌───────────────────┐       ┌──────────────────────────┐    │      ┌──────────────────────────┐   │
│  │ Rocky 9-objetivo  │       │   Windows 10-objetivo    │    │      │   Rocky 9                │   │
│  │                   │       │                          │    │      │   (Analista)             │   │
│  │                   │       │                          │    │      │                          │   │
│  │ 192.168.1.134     │       │  192.168.1.165           │    │      │  192.168.1.134           │   │
│  │                   │       │                          │    │      │  Nessus Expert           │   │
│  │                   │       │                          │    │      │  :8834                   │   │
│  └───────────────────┘       └──────────────────────────┘    │      └──────────────────────────┘   │
└────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## Servidor de prueba en la web:
https://juice-shop.herokuapp.com/#/






































































































































> [!NOTE]
> El host `192.168.1.134` es la misma máquina Windows 11 donde está instalado Nessus — es decir, Nessus se escaneó a sí mismo además de a los otros dos hosts. Esto es una práctica válida para analizar la propia máquina de trabajo.

---

## Máquina Analista — Windows 11

| Parámetro | Valor |
|---|---|
| **Sistema Operativo** | Windows 11 |
| **Herramienta** | Nessus Expert v10.x (trial 7 días) |
| **Configuración de red** | Red local / NAT |
| **IP** | `192.168.1.134` |
| **Interfaz Nessus** | `https://localhost:8834` |

---

## Máquinas Objetivo — Targets

| Host | Sistema Operativo | Servicios destacados |
|---|---|---|
| `192.168.1.134` | Windows 11 (misma máquina analista) | XAMPP (Apache, MySQL) activos durante el escaneo |
| `192.168.1.165` | Linux (Metasploitable 2 / Ubuntu) | Samba, NFS, Telnet, OpenSSH |
| `192.168.1.163` | Linux (Ubuntu 14.04 EOL) | Apache Tomcat, OpenSSH, SMB |

> [!NOTE]
> **XAMPP:** antes de lanzar el escaneo se activó XAMPP en la máquina Windows para levantar servicios de Apache y MySQL y poder ver resultados más completos en el análisis del host local.

> [!NOTE]
> **¿Por qué Metasploitable 2?** Es una máquina virtual diseñada específicamente para ser vulnerable, usada en entornos de aprendizaje. Viene con servicios intencionalmente desactualizados y configuraciones inseguras que permiten practicar análisis y explotación sin riesgo legal ni ético.
> Descargable en: [sourceforge.net/projects/metasploitable](https://sourceforge.net/projects/metasploitable/)

---

## Configuración de red en VirtualBox / VMware

Para que ambas máquinas se vean entre sí, deben estar en la **misma red**. Hay dos opciones:

**Opción A — NAT Network (recomendada):**
```
VirtualBox: Archivo → Preferencias → Red → Añadir NAT Network
→ Asignar la misma NAT Network a ambas VMs en su configuración de red
```

**Opción B — Red Interna:**
```
En la configuración de cada VM:
→ Adaptador de red → Conectado a: Red Interna
→ Nombre: intnet (el mismo en ambas)
```

> [!TIP]
> La opción NAT Network permite también que las VMs tengan acceso a internet (para actualizaciones), mientras que la Red Interna es completamente aislada.

---

## Verificación de conectividad

Antes de lanzar cualquier escaneo, confirmar que ambas máquinas se ven:

```bash
# Desde Kali Linux — comprobar visibilidad del target
ping -c 4 192.168.1.134
```

Salida esperada:
```
PING 192.168.1.134 (192.168.1.134): 56 bytes de datos
64 bytes de 192.168.1.134: icmp_seq=0 ttl=64 time=0.8 ms
64 bytes de 192.168.1.134: icmp_seq=1 ttl=64 time=0.6 ms
--- 192.168.1.134 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss
```

```bash
# Reconocimiento previo con nmap (referencia antes de Nessus)
nmap -sV 192.168.1.134
```
---