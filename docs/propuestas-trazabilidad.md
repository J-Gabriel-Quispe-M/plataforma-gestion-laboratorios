# Propuesta de Arquitectura Técnica para la Gestión de Imágenes y Trazabilidad

**Documento Complementario - Sección Arquitectura Técnica**

- **Responsable:** Brigitte Noelia Mengoa Valeriano
- **Universidad:** Universidad Nacional de San Agustín (UNSA)
- **Fecha:** Julio 2026.

---

## 1. Diagnóstico de la Propuesta Base (Riesgos Identificados)

El flujo inicial para la gestión de imágenes contempla las etapas principales del proceso, pero presenta algunos aspectos que pueden afectar la seguridad, la trazabilidad y el mantenimiento del sistema.

- **Ausencia de Versionado Formal:** No se define una estrategia para identificar y conservar versiones estables de las imágenes, dificultando la recuperación de versiones anteriores.
- **Control de Acceso Limitado:** La descarga segura de imágenes no especifica mecanismos de autorización basados en roles institucionales.
- **Auditoría Incompleta:** No existe un registro centralizado que permita conocer quién creó, modificó, aprobó o descargó cada imagen.
- **Gestión de Vulnerabilidades:** Aunque se menciona el escaneo con Trivy, no se establece un procedimiento para bloquear automáticamente imágenes con vulnerabilidades críticas.

---

## 2. Arquitectura Propuesta (Modelo en Capas)

```text
[ CAPA 1: USUARIOS ]        ---> Docentes / Estudiantes / Administradores
[ CAPA 2: SEGURIDAD ]       ---> Keycloak (Autenticación y Control de Acceso)
[ CAPA 3: GESTIÓN ]         ---> Harbor + Trivy + Notary (Firma Digital)
[ CAPA 4: TRAZABILIDAD ]    ---> Base de Auditoría + Logs + API de Eventos
[ CAPA 5: ALMACENAMIENTO ]  ---> Registry de Imágenes + Backup Automatizado
```

---

## 3. Soluciones Técnicas Clave

### A. Versionado y Gestión del Ciclo de Vida

Implementación de etiquetas (`tags`) siguiendo un esquema de versionado semántico (`v1.0`, `v1.1`, `v2.0`), acompañado de políticas de retención para eliminar imágenes obsoletas y conservar únicamente versiones aprobadas.

### B. Escaneo Automático de Seguridad

Todas las imágenes serán analizadas mediante **Trivy** antes de ser publicadas. Las imágenes que presenten vulnerabilidades críticas permanecerán bloqueadas hasta su corrección.

### C. Firma Digital y Control de Integridad

Uso de **Notary** o **Cosign** para firmar digitalmente cada imagen antes de su publicación, garantizando que únicamente se distribuyan imágenes verificadas y sin modificaciones no autorizadas.

### D. Auditoría y Trazabilidad

Registro automático de todas las acciones realizadas sobre una imagen:

- Creación
- Importación
- Escaneo
- Firma digital
- Publicación
- Descarga
- Actualización
- Eliminación

Cada evento almacenará:

- Usuario responsable.
- Fecha y hora.
- Versión de la imagen.
- Resultado del escaneo.
- Estado de aprobación.

### E. Control de Acceso

Integración con **Keycloak** para aplicar autenticación mediante cuentas institucionales `@unsa.edu.pe`, asignando permisos según el rol del usuario (Administrador, Docente o Estudiante).

---

## 4. Automatización del Flujo de Gestión

1. **Solicitud de Imagen:** El usuario solicita la creación o importación de una imagen.
2. **Validación Automática:** Harbor verifica si la imagen ya existe y ejecuta el escaneo con Trivy.
3. **Firma Digital:** La imagen aprobada se firma mediante Notary/Cosign para garantizar su integridad.
4. **Publicación:** Harbor publica la imagen junto con su versión y metadatos.
5. **Auditoría:** Todos los eventos son registrados automáticamente para asegurar la trazabilidad completa.
6. **Distribución Segura:** Los estudiantes descargan únicamente imágenes autorizadas según sus permisos institucionales.

---

## 5. Beneficios de la Propuesta

- Trazabilidad completa durante todo el ciclo de vida de las imágenes.
- Mayor seguridad mediante escaneo automático y firma digital.
- Control de acceso basado en roles institucionales.
- Auditoría detallada para facilitar el seguimiento de incidentes.
- Gestión eficiente de versiones y actualizaciones.
- Estandarización y confiabilidad en la distribución de imágenes para los laboratorios virtuales de la UNSA.