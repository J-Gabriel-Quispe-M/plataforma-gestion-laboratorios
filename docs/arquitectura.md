# Propuesta de Arquitectura Técnica y Soluciones

**Documento Complementario - Sección Arquitectura Técnica**

- **Responsable:** kennedy chirinos rojas
- **Universidad:** Universidad Nacional de San Agustín (UNSA)
- **Fecha:** Julio 2026.

---

## 1. Diagnóstico de la Propuesta Base (Riesgos Identificados)

El diseño técnico inicial del README presenta cuatro deficiencias críticas:

- **Falta de Almacenamiento Persistente:** Los contenedores en Kubernetes son efímeros. Sin un sistema como Longhorn, si un Pod se cae, los proyectos del alumno se pierden.
- **Sin Límites de Consumo (Multi-tenancy):** Un script infinito de un alumno podría agotar la CPU/RAM de todo el nodo físico del laboratorio.
- **Falta de Observabilidad:** No hay visibilidad del estado de las PC ni del consumo de red en tiempo real.
- **Sin Integración Institucional:** La autenticación no aprovecha el correo `@unsa.edu.pe`.

---

## 2. Arquitectura Propuesta (Modelo en Capas)

```
[ CAPA 1: CLIENTES ]      ---> PC de Lab / Laptops + Acceso VPN (WireGuard)
[ CAPA 2: IDENTIDAD ]     ---> Keycloak IAM (SSO con Google Workspace UNSA)
[ CAPA 3: SERVICIOS ]     ---> Harbor (Registry + Trivy) + GitLab CE + API Core
[ CAPA 4: INFRAESTRUCTURA]---> Proxmox VE + K3s + Longhorn + Prometheus/Grafana
```

---

## 3. Soluciones Técnicas Clave

### A. Almacenamiento Distribuido (Longhorn)

Implementación de Longhorn en K3s para gestionar volúmenes persistentes (`PV/PVC`). Permite a los alumnos conservar sus datos aunque la máquina física se reinicie.

### B. Control de Recursos por Alumno (ResourceQuota)

Aislamiento mediante `Namespaces` por curso y reglas estrictas de consumo por usuario:

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: cuota-estudiante-unsa
  namespace: laboratorio-sistemas
spec:
  hard:
    requests.cpu: "2"
    requests.memory: 2Gi
    limits.cpu: "4"
    limits.memory: 4Gi
    pods: "10"
```

### C. Autenticación Única (Keycloak + SSO UNSA)

Integración mediante OAuth2/OpenID con el directorio institucional `@unsa.edu.pe`. Mapeo automático de permisos según las asignaturas matriculadas.

### D. Monitoreo (Prometheus + Grafana)

Stack de observabilidad para medir en tiempo real el uso de CPU, RAM, disco y ancho de banda en cada estación del laboratorio.

---

## 4. Automatización del Despliegue (IaC)

1. **Terraform:** Aprovisionamiento automático de VMs sobre los hypervisores Proxmox VE.
2. **Ansible:** Configuración rápida de nodos K3s y dependencias de software en las PC del laboratorio.
