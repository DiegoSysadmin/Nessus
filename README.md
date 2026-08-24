# Análisis y Tratamiento de Vulnerabilidades con Nessus

---

## Arsenal del Analista: Automatización y Priorización de Vulnerabilidades con Nessus y EPSS

Este repositorio contiene un recurso técnico avanzado diseñado para analistas de seguridad, enfocado en optimizar el ciclo de vida de la gestión de vulnerabilidades en entornos corporativos. En lugar de limitarse a la ejecución teórica de herramientas, este proyecto propone una metodología práctica basada en el **Análisis de Vulnerabilidades Basado en Riesgo (RBVM)**, integrando **Nessus** con el modelo predictivo **EPSS (Exploit Prediction Scoring System)**.

El objetivo principal es resolver el problema real al que se enfrentan los equipos de Blue Team y SOC: la saturación por alertas (*alert fatigue*) debido al volumen inmanejable de vulnerabilidades con criticidad teórica alta (CVSS), priorizando aquellas con probabilidad real de explotación activa en el ecosistema actual.

---

## ¿Qué es Nessus?

Nessus es una plataforma de escaneo de vulnerabilidades desarrollada por Tenable. Su función principal es analizar redes, sistemas y aplicaciones para detectar fallos de seguridad, puertos abiertos, software desactualizado y errores de configuración antes de que puedan ser explotados por atacantes maliciosos.

## Funciones clave

*Identificación de riesgos*: Evalúa vulnerabilidades, malware, parches faltantes y configuraciones incorrectas en una amplia variedad de sistemas operativos y dispositivos.

*Automatización*: Permite programar escaneos periódicos y generar reportes detallados para que los equipos de TI apliquen soluciones rápidamente.

*Tipos de análisis*: Ofrece diferentes plantillas, desde escaneos básicos de red hasta auditorías avanzadas de cumplimiento normativo y análisis de aplicaciones web.

## Versiones

**Nessus Essentials**: Es la versión gratuita para uso educativo, estudiantil o personal, diseñada para escanear hasta 16 direcciones IP.

**Nessus Professional**: Es la versión comercial estándar utilizada por consultores y profesionales de la seguridad para evaluaciones ilimitadas.

**Nessus Expert**: Incluye funciones adicionales como la evaluación de aplicaciones web y la gestión de la superficie de ataque.


***Essential vs Professional***

| Característica | Nessus Essentials | Nessus Essentials Plus | Nessus Professional |
|---|:---:|:---:|:---:|
| Uso | Non-commercial use only | Non-commercial use only | For commercial use |
| Technical Support | ❌ | ❌ | ✅ |
| Escaneo de vulnerabilidades ilimitado | Hasta 5 IPs | Hasta 20 IP | IP ilimitadas |
| Actualización de plug-ins. | Retraso de 30 días | En tiempo real | En tiempo real |
| Plantillas prediseñadas de detección y escaneo de vulnerabilidades | ✅ | ✅ | ✅ |
| Verificaciones de cumplimiento y configuración | ❌ | ❌ | ✅ |
||||(Includes audit scan templates for cloud infrastructure, internal PCI network, offline configuration, policy compliance, SCAP and OVAL)|
| Generación de informes | ❌ | ✅ | ✅ |
|||(Basic PDF and HTML)|(PDF, HTML, CSV)|
| Acceso a Tenable Connect (Tenable Community) | ❌ | ✅ | ✅ |
| Exportación de datos | ❌ | ❌ | ✅ |
| Live Results | ❌ | ❌ | ✅ |
| Modo sin conexión | ❌ | ❌ | ✅ |
| Opción de añadir soporte avanzado (complemento) | ❌ | ❌ | ✅ |
| Precio | Gratuita | Pago | Pago |

***Professional vs Expert***

![Instalacion Nessus](/images/Nessus_ExpertVsPro.png)

---

## Estructura del repositorio

Este repositorio esta organizado de la siguiente manera.

```text
NESSUS/
├── 📄 README.md                 # Presentación del proyecto, objetivos y TL;DR
├── 📂 docs/
│   ├── 📄 workflow.md           # Metodología y flujo visual de trabajo (Mermaid)
│   ├── 📄 operation-guide.md    # Guía rápida de operación avanzada y buenas prácticas
│   ├── 📄 operation-guide.md    # Guía rápida de operación avanzada y buenas prácticas
│   ├── 📄 operation-guide.md    # Guía rápida de operación avanzada y buenas prácticas
│   ├── 📄 operation-guide.md    # Guía rápida de operación avanzada y buenas prácticas
│   ├── 📄 operation-guide.md    # Guía rápida de operación avanzada y buenas prácticas
│   └── 📄 plugins-automation.md # Script de automatización (Python) e integración de datos

└── 📂 assets/
    └── 📂 diagrams/             # Directorio para diagramas y capturas de pantalla


## 📁 Estructura del Repositorio


.
├── 📂 assets/                      # Capturas del proceso completo
│
├── 📂 docs/
│   ├── 01-que-es-nessus.md
│   ├── 02-glosario.md
│   ├── 03-instalacion.md
│   ├── 04-entorno-laboratorio.md
│   ├── 05-tipos-escaneo.md
│   ├── 06-politicas-escaneo.md
│   ├── 07-como-leer-reporte.md
│   ├── 08-hallazgos.md
│   └── 09-remediacion.md
│
└── 📄 README.md                      # Este archivo — índice principal
```

---
