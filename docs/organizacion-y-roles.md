# Definición de Organización, Roles y Procesos de Gestión

Este documento define la estructura organizacional, la asignación de roles y los procesos operativos clave para la administración de la plataforma de laboratorios de cómputo.

---

## 1. Estructura Organizacional y Roles

Para garantizar la correcta operatividad, soporte y gobernanza de la plataforma, se establecen cuatro roles principales:

| Rol | Descripción y Responsabilidades Clave |
| :--- | :--- |
| **Director de Escuela / Departamento** | • Aprobación de políticas institucionales y presupuestos.<br>• Supervisión general de la alineación académica y tecnológica. |
| **Encargado de Laboratorio (Administrador)** | • Gestión de infraestructura (Proxmox, Kubernetes, Harbor).<br>• Validación técnica y auditoría de seguridad de las imágenes.<br>• Asignación y control de cuotas de cómputo (CPU, RAM).<br>• Soporte técnico de nivel 2 y 3. |
| **Profesor / Docente** | • Solicitud formal de imágenes de software requeridas para sus asignaturas.<br>• Definición de guías de laboratorio y entornos de aprendizaje.<br>• Reserva de horarios de laboratorio para sus clases o proyectos. |
| **Estudiante** | • Despliegue y uso de los entornos de laboratorio asignados.<br>• Desarrollo de prácticas con prácticas responsables de consumo de recursos.<br>• Reporte de fallas e incidencias en la plataforma. |

---

## 2. Procesos Operativos del Laboratorio

### A. Proceso de Pedido e Integración de Imágenes para Cursos

Este proceso regula cómo un docente solicita software especializado para sus clases, garantizando que el entorno esté empaquetado, escaneado y disponible para los alumnos.

#### Flujo del Proceso:
1. **Solicitud:** El **Docente** envía la especificación del software, versiones y librerías requeridas antes de iniciar el semestre.
2. **Validación y Construcción:** El **Encargado de Laboratorio** crea el `Dockerfile`, verifica licencias y escanea vulnerabilidades con **Trivy**.
3. **Publicación:** La imagen aprobada se sube al registro privado (**Harbor**) con la etiqueta oficial del curso.
4. **Despliegue:** La plataforma expone la imagen para que los **Estudiantes** puedan levantar su laboratorio en un clic.

#### Diagrama del Proceso:
```mermaid
sequenceDiagram
    autonumber
    actor P as Profesor / Docente
    actor E as Encargado de Lab
    participant H as Registro (Harbor)
    actor A as Estudiantes

    P->>E: 1. Solicitud de software y requisitos
    E->>E: 2. Construye Dockerfile y audita seguridad (Trivy)
    E->>H: 3. Publica imagen aprobada con tag de curso
    H-->>A: 4. Disponible para ejecución en clases
