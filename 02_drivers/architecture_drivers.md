# Architecture Drivers
## Arquitectura Tecnológica Personal — Etma (2026)

---

# Descripción General

Los **Architecture Drivers** representan las motivaciones, riesgos y oportunidades tecnológicas que justifican la creación de la Arquitectura Tecnológica Personal de Etma.

Estos drivers guían:

- la definición de requerimientos
- las decisiones de arquitectura
- la evolución futura del ecosistema tecnológico

La clasificación utilizada sigue prácticas comunes de arquitectura empresarial como las propuestas por TOGAF.

Categorías utilizadas:

- Business Drivers
- Risk Drivers
- Technology Drivers

---

# 1. Business Drivers

## BD-01 — Secure and Ubiquitous Data Access

La información personal y profesional debe poder **accederse desde cualquier nodo autorizado de la red doméstica o desde internet**, siempre que se cuente con las credenciales correctas.

Esto incluye:

- repositorios de código
- documentos personales y profesionales
- fotografías
- proyectos de desarrollo

La arquitectura debe garantizar **acceso seguro, confiable y consistente a la información**.

---

## BD-02 — Operational Continuity

El ecosistema tecnológico debe permitir continuar las actividades profesionales **aunque uno o varios dispositivos no estén disponibles**.

Esto incluye:

- acceso remoto a la infraestructura
- disponibilidad de documentos y código
- capacidad de trabajar desde cualquier ubicación geográfica
- estaciones de trabajo de respaldo para emergencias

---

## BD-03 — Personal Media Platform

La arquitectura debe soportar una plataforma personal de distribución multimedia basada en **Plex Media Server**.

Esta plataforma permitirá:

- streaming de películas
- compartir fotografías familiares
- acceso controlado para familiares
- consumo desde televisiones inteligentes, tablets y dispositivos móviles
- acceso remoto seguro cuando sea necesario

---

## BD-04 — Structured Technology Organization

El ecosistema tecnológico personal debe mantenerse **organizado y documentado como un sistema coherente**, evitando el crecimiento desordenado de la infraestructura.

Esto incluye:

- inventario de hardware
- documentación de servicios
- control de accesos de usuarios
- integración de dispositivos consumidores como televisiones inteligentes y tablets

---

## BD-05 — Focused Study and Development Environment

La arquitectura debe proporcionar un entorno estable para **estudio técnico y desarrollo personal**.

Debe ser posible acceder a los recursos del laboratorio mediante:

- SSH
- RDP
- herramientas de desarrollo remoto
- dispositivos portátiles o móviles

---

# 2. Risk Drivers

## RD-01 — Data Loss Prevention

Existe el riesgo de pérdida de información crítica como:

- código histórico
- documentos personales
- fotografías familiares

La arquitectura debe mitigar este riesgo mediante:

- almacenamiento redundante
- mecanismos de respaldo
- separación entre capas de cómputo y almacenamiento

---

## RD-02 — Infrastructure Single Point of Failure

Actualmente algunos servicios o datos pueden depender de una sola máquina.

La arquitectura debe reducir los **puntos únicos de falla** permitiendo:

- migración de servicios
- redundancia de infraestructura
- distribución de almacenamiento y servicios

---

# 3. Technology Drivers

## TD-01 — Personal AI Capability

La infraestructura debe permitir experimentar con modelos de inteligencia artificial ejecutados localmente, como **DeepSeek** u otros modelos de lenguaje.

Esto habilita:

- aprendizaje práctico en inteligencia artificial
- ejecución local de inferencias
- integración futura con servicios personales

---

## TD-02 — Personal Technology Laboratory

Debe existir un laboratorio tecnológico **semi-productivo** que permita experimentar con tecnologías modernas.

La arquitectura contemplará dos tipos de nodos:

**Nodo de Producción**
- servicios estables
- almacenamiento
- plataforma multimedia
- servicios domésticos principales

**Nodo de Desarrollo**
- virtualización
- contenedores
- despliegues experimentales
- pruebas de nuevas tecnologías

---

## TD-03 — Hybrid Multi-Cloud Infrastructure Strategy

La arquitectura debe soportar una estrategia **híbrida y multi-nube**, integrando la infraestructura local con los principales proveedores de nube pública.

Proveedores considerados:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)

El objetivo es:

- aprovechar las fortalezas de cada proveedor
- optimizar costos operativos
- experimentar con arquitecturas multi-cloud
- evitar dependencia tecnológica de un solo proveedor

La nube actuará como **extensión del laboratorio tecnológico personal**, permitiendo ejecutar servicios o pruebas cuando sea necesario.
