# Plataforma Híbrida de Gestión de Laboratorios de Computación

**Proyecto Académico-Empresarial**  
**Carrera de Sistemas / Ingeniería de Software**  
**Universidad [Nombre de la Universidad]**  
**Versión:** 1.0 (Propuesta)  
**Fecha:** Julio 2026

---

## 📋 Tabla de Contenidos

- [Introducción](#introducción)
- [Problemática Común](#problemática-común)
- [Objetivos](#objetivos)
- [Justificación y Beneficios](#justificación-y-beneficios)
- [Enfoque Metodológico](#enfoque-metodológico)
- [Modelo Organizacional Ágil (Spotify Adaptado)](#modelo-organizacional-ágil-spotify-adaptado)
- [Requisitos de Conocimientos y Habilidades](#requisitos-de-conocimientos-y-habilidades)
- [Arquitectura Técnica Propuesta](#arquitectura-técnica-propuesta)
- [Gestión de Imágenes y Trazabilidad](#gestión-de-imágenes-y-trazabilidad)
- [Fases de Implementación](#fases-de-implementación)
- [Conclusiones y Recomendaciones](#conclusiones-y-recomendaciones)
- [Anexos](#anexos)

---

## Introducción

Este proyecto propone el desarrollo de una **Plataforma Híbrida** para la gestión integral de laboratorios de computación, aplicable tanto en entornos universitarios como en empresas de software.

La solución combina gestión de hardware (computadoras, servidores, impresoras), usuarios, proyectos/cursos, repositorios de código (GitLab) y un catálogo centralizado de imágenes de contenedores (Docker), garantizando **estandarización, trazabilidad y reproducibilidad** de entornos.

---
```diff
- [Comentario de Daniel Guillen - Responsable de Introducción]:

- 1. A favor: La propuesta plantea con claridad el uso de contenedores para unificar los entornos de trabajo, tanto para universidad como para empresa.
- 2. Observación/Riesgo: No se explica el motivo o la necesidad principal que origina esta propuesta, falta ese contexto inicial.
- 3. Observación/Riesgo: No se justifica por qué se eligió una arquitectura híbrida en lugar de una completamente en la nube o completamente local.
- 4. Mejora propuesta: Agregar un párrafo breve al inicio explicando el origen del problema y el criterio detrás de la decisión híbrida.
```

## Problemática Común

Los laboratorios universitarios y las empresas de software enfrentan problemas similares:

- Gestión fragmentada de recursos físicos y digitales.
- Pérdida significativa de tiempo en instalaciones y configuraciones manuales.
- Entornos no estandarizados que generan inconsistencias ("funciona en mi máquina").
- Falta de trazabilidad del software e imágenes utilizadas.
- Dificultad para replicar entornos entre laboratorio y computadoras personales de estudiantes/desarrolladores.
- Escalabilidad limitada al pasar de academia a industria.

**En el ámbito universitario** se busca especialmente que los alumnos **no pierdan tiempo** en instalaciones y que puedan llevarse las mismas imágenes oficiales a sus computadoras personales para practicar fuera del laboratorio.

---

```diff
- [Comentario de Daniel Guillen - Responsable de Problemática Común]:

- 1. A favor: Se identifican con claridad los principales problemas, falta de estandarización y tiempo perdido en configuraciones.
- 2. Observación/Riesgo: Los problemas se presentan como afirmaciones generales, sin datos ni ejemplos reales que los respalden.
- 3. Mejora propuesta: Incluir cifras o casos concretos, por ejemplo tiempo promedio perdido por práctica, para sustentar mejor la necesidad de la plataforma.
```

## Objetivos

### Objetivo General
Desarrollar una plataforma híbrida (local + nube) que permita la gestión estandarizada, segura y trazable de laboratorios de computación en contextos académicos y empresariales.

### Objetivos Específicos
- Implementar catálogo centralizado de imágenes de contenedores con procesos automatizados.
- Gestionar usuarios, proyectos/cursos y recursos físicos de forma eficiente.
- Garantizar trazabilidad completa del software utilizado.
- Permitir a los estudiantes descargar y ejecutar localmente las imágenes del laboratorio.
- Crear dos versiones: Académica y Empresarial (con estándares superiores).
- Formar estudiantes bajo metodologías ágiles reales (Modelo Spotify).

---

## Justificación y Beneficios

**Beneficios Universitarios:**
- Ahorro de tiempo para estudiantes y administradores.
- Entornos idénticos y reproducibles.
- Mayor calidad de proyectos y prácticas.
- Trazabilidad académica.

**Beneficios Empresariales:**
- Plataforma lista para entornos productivos.
- Estudiantes formados con estándares profesionales.
- Reducción de riesgos operativos.

```diff
- [Comentario de Nagin Carfer - Responsable de Objetivos + Justificación y Beneficios]:

- 1. A favor: Los objetivos están planteados de forma muy ordenada. El beneficio de lograr una menor dependencia de hardware local es un gran acierto, ya que facilitará mucho las prácticas para los estudiantes que no cuentan con equipos de alto rendimiento.
- 2. Observación/Riesgo: En los objetivos específicos se menciona la integración con herramientas de la universidad, lo cual es un poco ambiguo y podría complicar el alcance del proyecto si no se especifica exactamente qué sistemas (como el aula virtual o la intranet) se van a conectar.
- 3. Observación/Riesgo: Dentro de la justificación para la universidad, no se observa cómo se manejará la curva de aprendizaje inicial para que los docentes se adapten a este nuevo entorno.
- 4. Mejora propuesta: Añadir en los beneficios para los estudiantes que el uso de estas tecnologías (como CI/CD y plataformas en la nube) nos otorgará una ventaja competitiva y nos preparará de forma más directa para el mercado laboral.
```


---

## Enfoque Metodológico

El proyecto se desarrollará utilizando el **Modelo Spotify** adaptado al contexto universitario:

- **Tribe:** Platform Lab
- **Squads** multidisciplinarios (5-9 miembros)
- **Chapters** liderados por profesores con experiencia en industria
- **Guilds** temáticos

Se ejecutarán dos proyectos secuenciales:
1. **Proyecto Universitario** (Fase 1)
2. **Proyecto Empresa** (Fase 2)

```diff
- [Comentario de Cristhian Bravo - Responsable de Enfoque Metodológico]:

- 1. A favor: La propuesta utiliza un enfoque ágil y organiza el trabajo en equipos multidisciplinarios, lo cual se ajusta bien al contexto universitario y empresarial.
- 2. Observación/Riesgo: El uso del Modelo Spotify adaptado puede resultar poco claro si no se detallan los roles, responsabilidades y mecanismos de coordinación entre Tribes, Squads, Chapters y Guilds.
- 3. Observación/Riesgo: La separación en dos proyectos secuenciales podría generar problemas de continuidad si no se define cómo se transicionará entre la fase universitaria y la fase empresarial.
- 4. Mejora propuesta: Complementar el enfoque metodológico con un cuadro de roles, ceremonias ágiles y entregables esperados por fase para que sea más aplicable y fácil de implementar.
```

---

## Modelo Organizacional Ágil (Spotify Adaptado)

### Squads Principales

**Proyecto 1 - Universitario**
- Squad Core Platform
- Squad Image & Container Management
- Squad Hardware & Lab Operations
- Squad Frontend & User Experience

**Proyecto 2 - Empresa** (evolución)
- Squad Core Enterprise Platform
- Squad Advanced Image & Security
- Squad Hardware Fleet & Hybrid Operations
- Squad Enterprise Experience & Analytics
- Squad Integration & Ecosystem

Los **Chapters** serán liderados por profesores con mínimo 5 años de experiencia industrial.

---

## Requisitos de Conocimientos y Habilidades

### Cuadro Comparativo (Resumen)

| Rol                          | Proyecto 1 (Nivel)     | Tiempo Mín. Práctica | Proyecto 2 (Nivel)      | Tiempo Mín. Práctica |
|-----------------------------|------------------------|----------------------|-------------------------|----------------------|
| Tech Lead / Arquitecto      | Avanzado              | 2 semestres         | Senior                 | 4 semestres         |
| Backend Developer           | Intermedio-Avanzado   | 2 semestres         | Avanzado               | 3-4 semestres       |
| DevOps / Platform Engineer  | Intermedio            | 1-2 semestres       | Senior                 | 3-4 semestres       |
| Security Engineer           | Básico-Intermedio     | 1 semestre          | Avanzado               | 2-3 semestres       |
| UX/UI Designer              | Intermedio            | 1-2 semestres       | Avanzado               | 2-3 semestres       |

**Requisitos Generales:**
- Proyecto 1: 3er-4to semestre, promedio mínimo 14, portafolio GitHub.
- Proyecto 2: Haber participado en Proyecto 1 (preferible), conocimientos avanzados en Kubernetes, GitOps y Seguridad.

```diff
- [Comentario de Gabriel - Responsable de Requisitos de Conocimientos y Habilidades]:

- 1. A favor: Establecer requisitos para cada rol permite distribuir las responsabilidades según la preparación de los participantes.
- 2. Observación/Riesgo: Algunos requisitos son demasiado elevados para una primera fase universitaria, especialmente los conocimientos avanzados en Kubernetes, GitOps, seguridad y arquitectura. Esto podría limitar la participación de estudiantes que todavía están en proceso de formación.
- 3. Mejora propuesta: Diferenciar los conocimientos obligatorios para ingresar al proyecto de aquellos que se aprenderán durante su desarrollo, incorporar capacitaciones progresivas y definir competencias concretas y verificables para cada rol.
```

---

## Arquitectura Técnica Propuesta

- **Modelo Híbrido**: On-premise (Proxmox + Kubernetes) + Nube
- **Componentes principales**:
  - GitLab (código y CI/CD)
  - Harbor (Registry de imágenes)
  - Keycloak (Identity & Access)
  - PostgreSQL + MinIO
- **Infraestructura**: Proxmox VE, Kubernetes (K3s/Talos), Ansible + Terraform

```diff
- [Comentario de kennedy chirinos - Responsable de Arquitectura Técnica]:

- 1. A favor: La elección de K3s y Harbor es muy acertada para entornos universitarios.
- 2. Observación/Riesgo: Falta definir el almacenamiento persistente (PV/PVC) como Longhorn o Ceph.
- 3. Observación/Riesgo: Falta limitar consumo (ResourceQuotas) por usuario para no agotar la RAM del nodo.
- 4. Mejora propuesta: Incluir Grafana/Prometheus y conectar Keycloak con las cuentas @unsa.edu.pe.
```

---

## Gestión de Imágenes y Trazabilidad

**Flujo Principal:**
1. Solicitud de imagen
2. Búsqueda automática en Harbor
3. Creación/Importación + Escaneo (Trivy)
4. Firma digital y aprobación
5. Publicación con metadatos
6. Descarga segura por estudiantes
7. Actualizaciones controladas

Esto garantiza **estandarización y trazabilidad completa**.
```diff
- [Comentario de Brigitte Mengoa - Responsable de gestión de imágenes y trazabilidad]&#58; 
- 1. A favor: El flujo propuesto asegura una buena trazabilidad de las imágenes desde su creación hasta su distribución.
- 2. Observación/Riesgo: No se especifica una política de versionado y retención de imágenes para evitar el uso de versiones obsoletas.
- 3. Observación/Riesgo: Falta definir el mecanismo de control de acceso para la descarga segura de imágenes por parte de estudiantes y docentes.
- 4. Mejora propuesta: Incorporar auditoría de eventos y notificaciones automáticas ante imágenes con vulnerabilidades críticas detectadas por Trivy.
```

---

## Fases de Implementación

1. Análisis y Diseño (1 mes)
2. Desarrollo Proyecto Universitario (4-6 meses)
3. Evolución a Proyecto Empresa (5-7 meses)
4. Piloto y Puesta en Producción
5. Mejora Continua

---

## Conclusiones y Recomendaciones

Esta plataforma representa una oportunidad estratégica para modernizar los laboratorios de la universidad, elevar la calidad formativa y generar un activo tecnológico de alto valor transferable a la industria.

**Recomendaciones:**
- Aprobar como proyecto inter-cátedra.
- Asignar presupuesto para infraestructura base.
- Formalizar participación de profesores como Chapter Leads.

---

## Anexos

### Anexo 1: Tabla Detallada de Roles y Habilidades

*(Ver documento complementario `roles-habilidades.md`)*

### Anexo 2: Diagrama de Arquitectura (C4)

*(Se incluirán diagramas en formato PlantUML o Draw.io dentro de la carpeta `/docs/architecture`)*

### Anexo 3: Backlog Inicial de Épicas

*(Ver carpeta `/backlog`)*

### Anexo 4: Plan de Dedicación Semanal por Squad

*(Ver documento `plan-dedicacion.md`)*

### Anexo 5: Estimación de Costos Iniciales

*(Ver documento `costos.md`)*

---

## Cómo Contribuir

1. Leer el [Code of Conduct](CODE_OF_CONDUCT.md)
2. Seguir las [guías de contribución](CONTRIBUTING.md)
3. Crear issues y pull requests

---

**Licencia:** MIT  
**Estado del Proyecto:** Propuesta Inicial (En fase de aprobación)

---

*Documento preparado para repositorio GitHub. Puedes copiar todo este contenido directamente en un archivo `README.md`.*
