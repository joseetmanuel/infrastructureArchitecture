# Technical Requirements
## Arquitectura Tecnológica Personal — Etma (2026)

> **Propósito:** Convertir los *Architecture Drivers* en requerimientos técnicos verificables y trazables.
> Este documento habilita la asignación de funciones (ETAPA 2) y el diseño de arquitectura lógica (ETAPA 3).

---

# 1. Catálogo de Requerimientos (Requirements Catalog)

**Convención**
- **R-xx** = Requerimiento
- Prioridad: **Must / Should / Could**
- Verificación: criterios mínimos para considerar cumplido

---

## R-01 — Estación de emergencia laboral (Operational Continuity Workstation)
**Driver(s):** BD-02, BD-05  
**Prioridad:** Must  
**Descripción:** Debe existir al menos una estación funcional en casa para continuar labores profesionales en caso de no contar con Quetzal o Tezca.  
**Criterios de verificación:**
- Puede conectarse a internet y VPN corporativa (si aplica)
- Puede atender videollamadas
- Puede acceder a documentos/código vía repositorios autorizados

---

## R-02 — Preservación y disponibilidad de información crítica (Data Preservation & Availability)
**Driver(s):** BD-01, RD-01, RD-02  
**Prioridad:** Must  
**Descripción:** Los datos personales/profesionales deben estar protegidos y disponibles sin depender de una sola máquina.  
**Criterios de verificación:**
- Los datos críticos existen al menos en 2 ubicaciones (local + respaldo)
- Se puede recuperar información crítica sin depender de Huitzi

---

## R-03 — Control de acceso unificado (Identity & Access Control)
**Driver(s):** BD-01, BD-04  
**Prioridad:** Must  
**Descripción:** El acceso a datos/servicios debe ser controlado por credenciales y roles (familia, externo, admin).  
**Criterios de verificación:**
- Existe un mecanismo de autenticación y autorización (roles/permisos)
- Accesos externos limitados por usuario/contraseña y/o MFA

---

## R-04 — Compartición segura de archivos en red (Local File Services)
**Driver(s):** BD-01, BD-04, RD-02  
**Prioridad:** Must  
**Descripción:** Debe existir un servicio de archivos accesible por nodos autorizados de la red doméstica (y opcionalmente remoto) con permisos.  
**Criterios de verificación:**
- Acceso desde laptops/PCs (SMB/NFS o equivalente)
- Permisos por usuario/carpeta
- Auditoría básica (al menos logs de acceso)

---

## R-05 — Plataforma multimedia (Plex) con acceso controlado (Personal Media Platform)
**Driver(s):** BD-03, BD-04  
**Prioridad:** Should  
**Descripción:** Debe existir un servidor Plex para películas y fotografías con acceso controlado para familia y externos (p. ej. sobrinas).  
**Criterios de verificación:**
- Plex disponible en red local
- Acceso remoto opcional con control de usuarios
- Biblioteca separada por tipo (películas / fotos)

---

## R-06 — Soporte para dispositivos consumidores (Smart TVs / Tablets / Móviles)
**Driver(s):** BD-03, BD-04  
**Prioridad:** Should  
**Descripción:** Televisiones inteligentes y tablets deben poder consumir servicios (Plex/archivos) sin comprometer seguridad.  
**Criterios de verificación:**
- Reglas de acceso por segmento o usuario
- Dispositivos consumidores sin permisos administrativos

---

## R-07 — Laboratorio tecnológico semi-productivo (Dev/Test Lab)
**Driver(s):** TD-02, BD-05  
**Prioridad:** Must  
**Descripción:** Deben existir entornos diferenciados para *producción personal* (servicios estables) y *desarrollo* (pruebas), evitando que el laboratorio afecte lo estable.  
**Criterios de verificación:**
- Separación lógica (VMs/containers/hosts) entre Prod y Dev
- Servicios críticos no dependen del nodo de experimentación

---

## R-08 — Capacidad de virtualización y contenedores (Virtualization & Containers)
**Driver(s):** TD-02, RD-02  
**Prioridad:** Must  
**Descripción:** La infraestructura debe soportar virtualización y contenedores para ejecutar servicios y pruebas.  
**Criterios de verificación:**
- Virtualización habilitada en firmware donde aplique
- Ejecución de contenedores (Docker/Podman) y/o hipervisor (Proxmox/Hyper-V/VMware)

---

## R-09 — Capacidad de IA local (Local AI Capability)
**Driver(s):** TD-01, TD-02  
**Prioridad:** Could  
**Descripción:** Debe existir la capacidad de ejecutar modelos de IA local (ej. DeepSeek u otros), priorizando aprendizaje y experimentación.  
**Criterios de verificación:**
- Se puede ejecutar inferencia local (CPU/GPU) en un nodo designado
- Recursos asignables sin afectar servicios estables

---

## R-10 — Estrategia híbrida multi-nube (Hybrid Multi-Cloud)
**Driver(s):** TD-03, BD-02  
**Prioridad:** Should  
**Descripción:** La arquitectura debe poder extenderse a AWS/Azure/GCP para escalar o experimentar, evitando lock-in.  
**Criterios de verificación:**
- Infra como código (IaC) portable (p. ej. Terraform)
- Servicios y despliegues diseñados para portabilidad (Docker/K8s)

---

## R-11 — Observabilidad mínima (Monitoring & Logs)
**Driver(s):** RD-02, Principle 9 (Observability and Control)  
**Prioridad:** Should  
**Descripción:** Debe existir monitoreo básico de disponibilidad, almacenamiento y servicios críticos.  
**Criterios de verificación:**
- Métricas mínimas (CPU/RAM/disco/servicio up/down)
- Alertas básicas (local o vía app)

---

## R-12 — Documentación e inventario vivo (Living Documentation)
**Driver(s):** BD-04  
**Prioridad:** Must  
**Descripción:** La arquitectura debe mantenerse documentada en Git (inventario, drivers, principios, requisitos, diagramas).  
**Criterios de verificación:**
- Repositorio Git con estructura acordada
- Cambios documentados por versión (commits)

---

## R-13 — Impresión/escaneo compartido (Shared Printing)
**Driver(s):** BD-04  
**Prioridad:** Could  
**Descripción:** La impresora Epson L5190 debe estar disponible para los nodos autorizados de la red doméstica.  
**Criterios de verificación:**
- Impresión desde al menos 2 tipos de nodos (PC/laptop/móvil)
- Escaneo disponible para usuarios autorizados (si aplica)

---

## R-14 — Acceso remoto seguro (Secure Remote Access)
**Driver(s):** BD-01, BD-02, RD-02  
**Prioridad:** Should  
**Descripción:** Debe existir acceso remoto seguro a servicios internos (archivos, lab, Plex si se decide) sin exponer servicios directamente.  
**Criterios de verificación:**
- Acceso remoto mediante VPN/WireGuard/Tailscale o equivalente
- No exponer SMB/servicios sensibles directamente a internet

---

# 2. Matriz de Trazabilidad (Traceability Matrix)
## Drivers → Requirements

| Driver | Tipo | Requerimientos derivados |
|---|---|---|
| BD-01 Secure and Ubiquitous Data Access | Business | R-02, R-03, R-04, R-14 |
| BD-02 Operational Continuity | Business | R-01, R-10, R-14 |
| BD-03 Personal Media Platform | Business | R-05, R-06 |
| BD-04 Structured Technology Organization | Business | R-03, R-04, R-06, R-12, R-13 |
| BD-05 Focused Study and Development Environment | Business | R-01, R-07, R-08 |
| RD-01 Data Loss Prevention | Risk | R-02, R-04 |
| RD-02 Infrastructure Single Point of Failure | Risk | R-02, R-07, R-08, R-11, R-14 |
| TD-01 Personal AI Capability | Technology | R-09 |
| TD-02 Personal Technology Laboratory | Technology | R-07, R-08, R-09 |
| TD-03 Hybrid Multi-Cloud Infrastructure Strategy | Technology | R-10 |

---

# 3. Notas para ETAPA 2 (Asignación de funciones)

Estos requerimientos habilitan decidir roles como:

- **Nodo de Producción personal:** servicios estables (archivos, Plex, monitoreo)
- **Nodo de Desarrollo/Lab:** virtualización, contenedores, pruebas, IA local
- **Nodo de Respaldo operativo:** estación de emergencia (R-01)

La asignación concreta se hará en ETAPA 2 utilizando el catálogo y la matriz de trazabilidad.
