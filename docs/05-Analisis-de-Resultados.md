# Analisis de Resultados

Para ver los resultados del escaneo, nos paramos sobre **My Scans** y elegimos el escaneo que vamos a analizar, en este caso **EscaneoDeMalware**.

En la solapa **Hosts** vemos los activos encontrados en la red, nos muestra su ip y si pudo autenticarse con las credenciales que le configuramos (Auth). En **Vulnerabilities** aparecen las vulnerabilidades encontradas, en este caso son todas de tipo informativas. A la derecha vemos los detalles del escaneo donde muestra la Policy, nos dice utilizó como base el CVSS en su version 3.0  y si el escaneo fue local y la fecha/hora de inicio y fin del mismo junto con el tiempo que duró. También apreciamos un resumen grafico de las vulnerabilidades.

![Instalacion Nessus](/images/44_Nessus-Resultados.png)
![Instalacion Nessus](/images/45_Nessus-Resultados.png)

Haciendo clic sobre una de las IP vemos el detalle de lo encontrado para este host.

![Instalacion Nessus](/images/46_Nessus-Resultados.png)
![Instalacion Nessus](/images/47_Nessus-Resultados.png)
![Instalacion Nessus](/images/48_Nessus-Resultados.png)
![Instalacion Nessus](/images/49_Nessus-Resultados.png)

## Gravedad

https://docs.tenable.com/nessus/10_12/Content/Severity.htm#CVSS-based-Severity

https://docs.tenable.com/nessus/10_12/Content/manage-vulnerabilities.htm#View

En la solapa **Vulnerabilities** vemos el detalle de las vulnerabilidades y su severidad. La gravedad es una categorización del riesgo y la urgencia de una vulnerabilidad.

![Instalacion Nessus](/images/50_Nessus-Resultados.png)
![Instalacion Nessus](/images/51_Nessus-Resultados.png)

Para obtener más información, consultar [Puntuaciones CVSS frente a VPR](https://docs.tenable.com/nessus/10_12/Content/RiskMetrics.htm).

**Gravedad basada en CVSS**

Al visualizar las vulnerabilidades en los resultados del análisis, Tenable Nessus muestra la gravedad en función de las puntuaciones CVSSv2, CVSSv3 o CVSSv4, según su configuración.

- Se puede elegir si Tenable Nessus calcula la gravedad de las vulnerabilidades utilizando las puntuaciones CVSSv2, CVSSv3 o CVSSv4 configurando la base de gravedad predeterminada. Para obtener más información, consultar [Configurar la base de gravedad predeterminada](https://docs.tenable.com/nessus/10_12/Content/ConfigureDefaultSeverity.htm).

- También se puede configurar análisis individuales para que utilicen una base de gravedad específica, lo que anula la base de gravedad predeterminada para los resultados de dichos análisis. Para obtener más información, consultar [Configurar la base de gravedad para un análisis individual](https://docs.tenable.com/nessus/10_12/Content/ConfigureIndividualScanSeverity.htm).

**VPR**

Al visualizar las vulnerabilidades en los resultados del escaneo, Tenable Nessus muestra la gravedad en función de VPR .

**Gravedad basada en EPSS**

Al visualizar las vulnerabilidades en los resultados del escaneo, Tenable Nessus muestra la gravedad según el Sistema de Puntuación de Predicción de Exploits (EPSS).



