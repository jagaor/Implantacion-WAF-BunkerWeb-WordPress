# Implantación de una Solución WAF (BunkerWeb)

## 📝 Descripción General
Este proyecto forma parte del módulo de "Puesta en Producción Segura". Su objetivo es desplegar y administrar una capa de seguridad perimetral para aplicaciones web utilizando **BunkerWeb**, un Web Application Firewall (WAF) de código abierto. La práctica documenta la integración de este WAF delante de una aplicación web (WordPress) alojada en un servidor Ubuntu, actuando como proxy inverso para inspeccionar, filtrar y proteger el tráfico HTTP/HTTPS en tiempo real.

## 🎯 Objetivos del Proyecto
* Implementar una arquitectura segura utilizando BunkerWeb como proxy inverso frente a aplicaciones web en producción.
* Centralizar la gestión de certificados TLS/SSL y políticas de seguridad en un único punto de entrada.
* Configurar reglas de filtrado para mitigar y bloquear ataques web comunes, bots maliciosos y escaneos automáticos.
* Analizar los registros (logs) y estadísticas de tráfico para identificar direcciones IP hostiles y patrones de ataque.
* Garantizar la escalabilidad del entorno, demostrando cómo proteger múltiples servicios bajo la misma barrera perimetral.

## 🛠️ Tecnologías y Herramientas
* **Sistema Operativo**: Máquina Virtual con Linux (Ubuntu).
* **Web Application Firewall (WAF)**: BunkerWeb.
* **Aplicación Objetivo**: WordPress (CMS).
* **Conceptos Aplicados**: Proxy inverso, criptografía (certificados TLS), mitigación de ataques y monitorización.

## ⚙️ Detalles de Implementación Destacados
* **Preparación del Entorno**: Se partió de un sistema base actualizado, configurando la red y las dependencias para soportar el flujo de tráfico hacia el motor de inspección.
* **Despliegue del Proxy Inverso**: BunkerWeb fue configurado para recibir todas las peticiones externas, procesar el tráfico seguro (TLS), inspeccionar la carga útil en busca de firmas o comportamientos anómalos y, si es legítima, reenviarla al servidor de backend (WordPress).
* **Monitorización y Bloqueo Activo**: Se validó la eficacia del WAF simulando ataques básicos contra el servidor. La herramienta logró interceptar y bloquear los intentos de intrusión, registrando las direcciones IP de origen y proporcionando estadísticas detalladas sobre el volumen y tipo de amenazas.
* **Ventajas Operativas**: La práctica evidenció que la arquitectura de proxy inverso centraliza la defensa, reduciendo la superficie de exposición del servidor final y facilitando el mantenimiento a largo plazo.

## 📄 Documentación Completa
Para consultar los comandos exactos de instalación en Ubuntu, la configuración de los servidores virtuales, el despliegue de los certificados TLS y las evidencias visuales de los ataques bloqueados por el WAF, puedes revisar la memoria técnica completa del proyecto:

👉 [Enlace al Informe Técnico en Google Drive](https://docs.google.com/document/d/1xlM3h7NSVcRkfLxJ51_pWHU6pq4rV8IfpWqdjhTPCFo/edit?usp=sharing)

## ⚠️ Aviso Legal / Ética
*El despliegue de esta arquitectura de seguridad se ha realizado en un entorno de laboratorio controlado con fines puramente académicos. Su objetivo es comprender el funcionamiento de las soluciones WAF para aplicar políticas de defensa robustas en infraestructuras de producción reales.*
