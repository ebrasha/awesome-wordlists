# Colección definitiva de diccionarios para pruebas de penetración, fuerza bruta y fuzzing web

> 🌐 **Leer en tu idioma:** 🇬🇧 [English](README.md) | 🇨🇳 [中文](README.zh.md) | 🇷🇺 [Русский](README.ru.md) | 🇪🇸 [Español](README.es.md) | 🇯🇵 [日本語](README.ja.md) | 🇮🇷 [فارسی](README.fa.md) | 🇸🇦 [العربية](README.ar.md) | 🇹🇷 [Türkçe](README.tr.md) | 🇩🇪 [Deutsch](README.de.md) | 🇮🇳 [हिन्दी](README.hi.md)


[![Security](https://img.shields.io/badge/Security-Pentesting-red.svg)](#)


El repositorio más completo de GitHub, que sirve como una colección maestra centralizada y altamente optimizada de diccionarios, datos para ataques de diccionario y cargas útiles avanzadas de fuzzing, diseñada específicamente para profesionales de seguridad, pentesters y hackers éticos.

---

## 🎯 Por qué existe este repositorio

Durante las evaluaciones de seguridad y las pruebas de penetración, contar con acceso inmediato a datos bien estructurados y de alta calidad es fundamental. Los diccionarios estándar suelen estar dispersos, desactualizados o llenos de datos redundantes que ralentizan los ataques de fuerza bruta y el fuzzing web.

Este repositorio se creó para cubrir esa brecha. Constituye un componente esencial de la infraestructura de la estación de trabajo de un especialista en seguridad. Al consolidar listas multipropósito en un único repositorio estructurado, puede clonarlo rápidamente en cualquier entorno de pruebas y desplegar de inmediato ataques de diccionario dirigidos, descubrimiento de directorios o inyecciones de cargas útiles.

---

## 📂 Contenido y estructura del repositorio

Los conjuntos de datos de este repositorio están categorizados y optimizados estratégicamente para maximizar la velocidad, minimizar el ruido y garantizar altas tasas de éxito durante las pruebas activas de penetración y los compromisos de hacking ético. A continuación, se presenta un desglose completo del plano estructural de este repositorio:

### 🤖 1. Inteligencia Artificial (IA) y Seguridad de LLM (`/Ai`)
Una colección de vanguardia diseñada para pruebas adversariales, verificación de alineación de seguridad y red-teaming de los LLMs y modelos de IA modernos:
* **Pruebas de sesgo y equidad:** Diccionarios estandarizados (`gender_bias.txt`, `race_ethnicity_bias.txt`) para auditar la alineación de los modelos.
* **Fuga de datos y privacidad:** Cargas útiles dirigidas para simular la recuperación accidental de PII y la exposición de metadatos (`personal_data.txt`).
* **Prompts adversariales y de jailbreak:** Conjuntos históricos y evolucionados de inyección de prompts diseñados para eludir los límites del modelo y poner a prueba restricciones estrictas de alineación.

### 🔍 2. Fuzzing Web, descubrimiento de activos y reconocimiento (`/Discovery`)
Listas exhaustivas estructuradas para mapear agresivamente la superficie de ataque empresarial en las capas de red, aplicación e infraestructura:
* **Enumeración de directorios y archivos:** Incluye diccionarios de alta fidelidad como las series curadas `raft` y `DirBuster` para identificar rutas web ocultas, puertas traseras del sistema y ubicaciones de shells.
* **Infraestructura y red:** Listas de enumeración de subdominios (incluidas variantes combinadas Top 1M), extensiones web comunes, nombres de servicios y cadenas de comunidad SNMP personalizadas (`snmp.txt`).
* **CMS y contextos de entorno:** Endpoints altamente específicos para sistemas empresariales y Sistemas de Gestión de Contenido, incluidas rutas completas para plugins/temas de WordPress, Drupal, Joomla, Apache, Nginx, Tomcat y WebSphere.

### 🔑 3. Autenticación y credenciales (contraseñas y conjuntos de filtraciones)
Listas maestras enfocadas en credential stuffing a alta velocidad, auditoría de accesos por defecto y sofisticados ataques de diccionario por fuerza bruta:
* **Credenciales filtradas y volcados:** Variantes optimizadas de conjuntos de datos legendarios de filtraciones (como fragmentos ordenados de `rockyou`, `myspace` y patrones históricos de comunidades filtradas) con o sin recuento de ocurrencias.
* **Registros de acceso por defecto:** Amplias asignaciones de cuentas predeterminadas de proveedores, contraseñas estándar de routers, IDs de transacciones CICS y perfiles de credenciales CCTV/DVR multifabricante.
* **Entornos específicos:** Archivos de credenciales adaptados y estructurados para protocolos de red concretos (SSH, Telnet, cuentas root de bases de datos y perfiles IPMI).

### ⚡ 4. Cargas útiles de inyección, fuzzing y mutación
Cargas útiles avanzadas compiladas para validar fallos de capa de aplicación y descartar los casos extremos no explotables:
* **Fallos del lado del servidor:** Listas dinámicas dirigidas a Local File Inclusion (LFI) optimizadas para rutas Unix/Windows, Remote File Inclusion y sobrescritura de variables del sistema.
* **Componentes nativos de la web:** Mapeos exhaustivos para el descubrimiento de parámetros (`burp-parameter-names.txt`), descubrimiento de APIs (`api-endpoints.txt`) y listas personalizadas de fuzz PHP diseñadas para romper los filtros de validación de entrada.


---

## ⚖️ Aviso legal

**Aviso importante:** Este repositorio y los conjuntos de datos aquí proporcionados se han creado estrictamente con fines educativos, pruebas de penetración autorizadas y auditorías de seguridad.

*   **Responsabilidad del usuario:** La responsabilidad última del uso de estos diccionarios recae enteramente en el usuario final. El mantenedor no asume ninguna responsabilidad por el uso indebido, los ataques no autorizados, las brechas de datos o las consecuencias legales derivadas del uso de estos archivos.
*   **Cumplimiento:** Asegúrese de contar con permiso explícito y por escrito de la organización objetivo o del propietario del activo antes de iniciar cualquier tipo de evaluación de seguridad, ataque de diccionario o fuzzing.

Al clonar o utilizar este repositorio, usted acepta estos términos y reconoce que sus actividades deben adherirse estrictamente a las leyes locales e internacionales en materia de ciberseguridad.



## 🐛 Reporte de problemas

Si encuentra algún problema o tiene dificultades con la configuración, póngase en contacto a través del correo electrónico Prof.Shafiei@Gmail.com. También puede reportar problemas en GitHub.


## ❤️ Donaciones

Si este proyecto le resulta útil y desea apoyar su desarrollo continuo, considere realizar una donación:

- [Donar aquí](https://t.me/AbdalDonationBot)


## 🤵 Mantenido por

Mantenido con pasión por **Ebrahim Shafiei (EbraSha)**

- **Correo electrónico**: Prof.Shafiei@Gmail.com

- **Telegram**: [@ProfShafiei](https://t.me/ProfShafiei)
