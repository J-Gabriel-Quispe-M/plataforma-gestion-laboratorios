# Propuesta de Mejora en la Introducción

**Documento Complementario - Sección Introducción**

- **Responsable:** Daniel
- **Universidad:** Universidad Nacional de San Agustín (UNSA)
- **Fecha:** Julio 2026

---

## 1. Diagnóstico de la Propuesta Base (Riesgos Identificados)

La introducción del README presenta dos deficiencias claras:

- **Falta de Contexto de Origen:** No se explica el motivo ni la necesidad principal que da origen a la propuesta.
- **Decisión Híbrida sin Justificación:** Se afirma que la arquitectura es híbrida (local + nube), pero no se argumenta por qué se descartó un modelo 100% en la nube o 100% local.

---

## 2. Propuesta de Redacción Mejorada

Este proyecto propone el desarrollo de una Plataforma Híbrida para la gestión integral de laboratorios de computación, aplicable tanto en entornos universitarios como en empresas de software.

La propuesta surge de un problema recurrente: cada semestre se pierde tiempo valioso instalando y configurando manualmente el software que cada curso necesita, y no existe forma de asegurar que el entorno usado en el laboratorio sea el mismo que el estudiante puede replicar en su propia computadora.

La solución combina gestión de hardware, usuarios, proyectos/cursos, repositorios de código (GitLab) y un catálogo centralizado de imágenes de contenedores (Docker), garantizando estandarización, trazabilidad y reproducibilidad de entornos.

---

## 3. Justificación del Modelo Híbrido

| Criterio | Razón |
|---|---|
| **Costo** | Aprovechar servidores ya disponibles en los laboratorios reduce gasto frente a operar todo en la nube. |
| **Control y Latencia** | Procesar imágenes localmente reduce la dependencia de conexión a internet durante las prácticas. |
| **Escalabilidad** | La nube permite absorber picos de uso (evaluaciones, entregas) sin comprar hardware permanente. |

---

## 4. Conclusión de la Mejora

El modelo híbrido no es solo una elección técnica, sino una decisión de costo-beneficio: combina el control y bajo costo de la infraestructura local con la flexibilidad de la nube cuando el laboratorio lo necesite.