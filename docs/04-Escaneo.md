# Escaneo de Vulnerabilidades

- Vamos a "My Scans-->New Scan"		
- Dentro de targets coloco la subred a escanear: 10.0.1.0/24
- Luego damos: "Submit"
- Luego seleccionamos el host que encontro y damos: "Run Scan"

![Instalacion Nessus](/images/21_Nessus-Escaneo.png)
![Instalacion Nessus](/images/22_Nessus-Escaneo.png)

---

## Tipos de Escaneo

![Instalacion Nessus](/images/23_Nessus-Escaneo.png)


Las plantillas de escaneo en Nessus están organizadas por categorías según el objetivo del análisis:

### Discovery (Descubrimiento)

**Host Discovery**: Identifica hosts activos en la red y mapea puertos abiertos básicos sin evaluar vulnerabilidades en profundidad.

**Ping-Only Discovery**: Detecta equipos vivos generando el mínimo tráfico de red posible (ICMP/ARP), ideal para no saturar enlaces sensibles o dispositivos frágiles.

### Vulnerabilities (Vulnerabilidades)

**Basic Network Scan**: Escaneo completo estándar adecuado para cualquier tipo de host. Evalúa puertos, servicios y vulnerabilidades conocidas en red de forma equilibrada.

**Credential Validation**: Comprueba rápidamente si las credenciales SSH, SMB o WMI suministradas funcionan correctamente contra los objetivos antes de lanzar un escaneo exhaustivo.

**Advanced Scan**: Plantilla en blanco que permite configurar manualmente cada parámetro (puertos, timeouts, plugins específicos y opciones de rendimiento).

**Advanced Dynamic Scan**: Similar al escaneo avanzado, pero permite definir reglas dinámicas para la selección de plugins según criterios específicos.

**Malware Scan**: Busca rastros de malware, troyanos o procesos maliciosos activos en sistemas Windows y Unix (requiere escaneo autenticado).

**Credentialed Patch Audit**: Realiza un escaneo autenticado conectándose localmente al sistema para enumerar de manera precisa los parches y actualizaciones de seguridad faltantes.

**Active Directory Starter Scan**: Evalúa malas configuraciones, permisos débiles y problemas de seguridad básicos en controladores de dominio y Active Directory.

**Find AI**: Detecta frameworks, servicios, modelos de lenguaje (LLM) y componentes de inteligencia artificial expuestos en la infraestructura, identificando posibles fallos asociados.

**Cryptographic Inventory**: Sondea los protocolos de red para identificar algoritmos criptográficos, versiones de TLS/SSL y certificados en uso.

**Mobile Device Scan / Web Application Tests**: Escaneos orientados a dispositivos móviles (vía MDM/Exchange) y análisis DAST básico de aplicaciones web.

### Compliance (Cumplimiento y Auditoría)

**Audit Cloud Infrastructure**: Evalúa configuraciones en proveedores de nube (AWS, Azure, GCP) frente a buenas prácticas.

**Internal PCI Network Scan / PCI Quarterly External Scan**: Diseñados para verificar los requisitos técnicos del estándar PCI DSS (versión 11.3.1) a nivel interno y externo.

**MDM & Offline Config Audit**: Audita administradores de dispositivos móviles o archivos de configuración exportados de switches, routers y firewalls sin conectarse en vivo a ellos.

**Policy Compliance Auditing & SCAP/OVAL Auditing**: Compara la configuración del sistema contra líneas base (CIS Benchmarks, DISA STIGs) o definiciones estándar OVAL/SCAP.

---

## Primer escaneo

### Descubrimiento

Lo primero a realizar es un descubrimiento de red, vamos a ver de que realmente detecta los host.

![Instalacion Nessus](/images/24_Nessus-Escaneo.png)
![Instalacion Nessus](/images/25_Nessus-Escaneo.png)
![Instalacion Nessus](/images/26_Nessus-Escaneo.png)
![Instalacion Nessus](/images/27_Nessus-Escaneo.png)
![Instalacion Nessus](/images/28_Nessus-Escaneo.png)
![Instalacion Nessus](/images/29_Nessus-Escaneo.png)
![Instalacion Nessus](/images/30_Nessus-Escaneo.png)

### Malware

![Instalacion Nessus](/images/31_Nessus-Escaneo.png)
![Instalacion Nessus](/images/32_Nessus-Escaneo.png)
![Instalacion Nessus](/images/33_Nessus-Escaneo.png)
![Instalacion Nessus](/images/34_Nessus-Escaneo.png)
![Instalacion Nessus](/images/35_Nessus-Escaneo.png)
![Instalacion Nessus](/images/36_Nessus-Escaneo.png)
![Instalacion Nessus](/images/37_Nessus-Escaneo.png)
