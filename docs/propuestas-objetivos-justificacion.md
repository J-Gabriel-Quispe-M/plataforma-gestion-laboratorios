# Propuesta de Mejora para Objetivos, Justificación y Beneficios

**Documento Complementario - Sección Objetivos y Justificación**

* **Responsable:** Nagin Carfer
* **Universidad:** Universidad Nacional de San Agustín (UNSA)
* **Fecha:** Julio 2026.

---

## 1. Diagnóstico de la Propuesta Base (Riesgos Identificados)

Al analizar la sección base de Objetivos, Justificación y Beneficios, se identificaron los siguientes aspectos que requieren un mayor nivel de detalle para garantizar la viabilidad del proyecto:

* **Ambigüedad en la Integración de Sistemas:** La propuesta inicial menciona la "integración con herramientas de la universidad" de forma genérica, lo cual genera incertidumbre sobre el alcance real y la factibilidad técnica (ej. sincronización con Aula Virtual o Intranet UNSA).
* **Ausencia de un Plan de Adopción Docente:** La justificación abarca beneficios para los profesores, pero omite el impacto de la curva de aprendizaje necesaria para adaptarse a entornos basados en contenedores y la nube.
* **Falta de Énfasis en Empleabilidad:** Aunque se mencionan beneficios para los estudiantes, no se destaca explícitamente la ventaja competitiva de dominar metodologías modernas de la industria (CI/CD, GitOps, Kubernetes).
* **Falta de Indicadores de Éxito (KPIs):** Los objetivos actuales no cuentan con métricas cuantitativas que permitan verificar si el proyecto alcanzó sus metas de manera exitosa.

---

## 2. Propuesta de Redefinición de Objetivos

### Objetivo General
Desplegar una plataforma híbrida de gestión de laboratorios de cómputo que optimice el uso de recursos tecnológicos, garantice la trazabilidad académica y reduzca la brecha tecnológica en los estudiantes de la UNSA.

### Objetivos Específicos Mejorados
1. **Integración Institucional:** Conectar el control de acceso y autenticación de la plataforma con la Intranet/Aula Virtual UNSA mediante el protocolo SSO con Keycloak.
2. **Estandarización de Entornos:** Proveer un catálogo de imágenes Docker precargadas y auditadas para el 100% de los cursos del área de sistemas e informática.
3. **Capacitación y Adopción:** Implementar un programa de inducción técnica dirigido a docentes y encargados de laboratorio para asegurar una transición fluida al nuevo modelo.
4. **Optimización de Recursos:** Reducir la carga operativa y la dependencia de hardware local de alta gama en los clientes finales mediante el uso de cargas centralizadas en K3s/Talos.

---

## 3. Justificación Ampliada y Beneficios Esperados

```text
[ IMPACTO DEL PROYECTO ]
├── Para la Universidad ----> Eficiencia presupuestal + Gobernanza + Integración SSO
├── Para los Docentes  ----> Automatización de despliegues + Soporte continuo
└── Para Estudiantes   ----> Equidad tecnológica + Empleabilidad con CI/CD y Cloud
