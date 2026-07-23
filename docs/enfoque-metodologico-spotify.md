# Propuesta de Enfoque Metodológico: Modelo Spotify Adaptado

**Documento Complementario**

- **Responsable:** Cristhian Bravo
- **Fecha:** Julio 2026

---

## Riesgos Identificados

- Roles ambiguos: No está claro quién decide, quién coordina ni límites de autoridad
- Sin ceremonias definidas: Falta Sprint Planning, Retrospectives, Dailys
- Continuidad P1→P2 indefinida: Riesgo de fragmentación de equipos
- Participación cruzada sin reglas: Múltiples roles sin claridad de dedicación

---

## Modelo Spotify Adaptado

### Estructura Organizacional

| Nivel | Rol | Responsabilidades |
|-------|-----|------------------|
| **TRIBE** | Coordinación máxima | Roadmap, decisiones estratégicas, arbitraje entre squads |
| **SQUADS (4)** | Equipos autónomos (5-9 miembros) | Entrega de incrementos cada sprint (2 semanas) |
| **CHAPTERS** | Liderazgo vertical (Profesores) | Mentoría técnica, code reviews, estándares |
| **GUILDS** | Comunidades temáticas | Mejores prácticas, talleres, voluntarios |

### Squads Proyecto 1 (Universitario)
- **Squad Core Platform:** Backend, Base de Datos, APIs
- **Squad Image & Container:** DevOps, Registry (Harbor), Automatización
- **Squad Hardware & Lab Ops:** Proxmox, Networking, Seguridad Física
- **Squad Frontend & UX:** Diseño, Frontend, User Experience

### Chapters (Liderados por Profesores con 5+ años experiencia)
- Backend | DevOps | Security | UX Design

### Guilds (Temáticas)
- CI/CD | Security & Compliance | Cloud Native | Documentación

---

## Reglas de Participación Cruzada

1. **Un miembro máx. 2 roles:** Squad Principal (75%) + Chapter/Guild secundario (15-20%)
2. **Matriz RACI simplificada:**
   - Squad → Responsable ejecución
   - Chapter → Aprueba calidad técnica
   - Tribe → Arbitra conflictos
3. **Escalada:** Si hay conflicto de dedicación → Tribe decide prioridades

---

## Ceremonias Ágiles (Sprint de 2 semanas)

| Ceremonia | Día | Duración | Participantes | Objetivo |
|-----------|-----|----------|---------------|----------|
| Sprint Planning | Lunes | 2-3 h | Tribe + Squads | Definir tareas, estimaciones |
| Daily Standup | L-V | 15 min | Squad + Chapter Lead | Bloqueos, progreso |
| Chapter Meeting | Miércoles | 1 h | Chapter + miembros | Code review, mentoría, estándares |
| Sprint Review | Viernes 16:00 | 1 h | Tribe, Squads, Stakeholders | Demo, feedback |
| Retrospective | Viernes 17:00 | 45 min | Squad + Scrum Master | Mejoras para próximo sprint |

**Guild Meetings (Mensual):** Voluntarios, sin agenda formal, mejores prácticas temáticas.

---

## Transición Proyecto 1 → Proyecto 2

### Estrategia Overlap (Semanas 1-8 de P2)

- **P1 en Transición:** 30% del equipo en modo mantenimiento, transferencia de conocimiento
- **P2 en Ramp-up:** 70% del equipo iniciando proyecto empresarial
- **Mecanismo:** Pair programming cruzado, Wiki de decisiones (ADR), Tech talks mensuales

### Evolución de Squads

| P1 Squad | P2 Squad | Cambio |
|----------|----------|--------|
| Core Platform | Core Enterprise | Senior lideran nuevas features |
| Image Management | Advanced Image & Security | Enfoque en compliance |
| Hardware Ops | Fleet & Hybrid Ops | Escalabilidad multi-datacenter |
| Frontend UX | Enterprise Exp & Analytics | Agregan analytics avanzados |

---

## Matriz de Decisiones

| Tipo | Quién Decide | Tiempo |
|------|-------------|--------|
| **Estratégica** (Ej: cambiar tech stack) | Tribe | 1-2 semanas |
| **Arquitectónica** (Ej: cambiar ORM) | Squad Lead + Chapter Lead | 2-3 días |
| **Táctica** (Ej: algoritmo) | Squad con mentoría | Dentro del sprint |
| **Operativa** (Ej: testing en PR) | Dev + Code Reviewer | Durante review |

---

## Criterios de Éxito

### Proyecto 1 (Meses 1-6)
- ✓ 100% entregas por sprint | ✓ ≥80% cobertura tests | ✓ ≥90% retención estudiantes
- ✓ Documentación actualizada | ✓ <10% deuda técnica

### Proyecto 2 (Meses 7-18)
- ✓ ≥99.5% uptime | ✓ <200ms response time (API) | ✓ Security score A-
- ✓ NPS ≥40 | ✓ ≥1000 RPS throughput

---

## Conclusiones

**Fortalezas:** Claridad de roles | Escalabilidad | Transferencia de conocimiento | Continuidad P1→P2

**Riesgos a Mitigar:**
- Conflicto de dedicación → Matriz RACI clara
- Pérdida de miembros → Overlap de 8 semanas
- Desalineamiento → Standups + Retrospectives + Tribe
- Comunicación → Ceremonias regulares

**Implementación:**
1. Semana 0: Entrenar a todos en Spotify Model
2. Semana 1: Lanzar Sprint 1 con Jira preconfigurado
3. Mes 2: Revisar métricas y ajustar
4. Mes 6: Retrospective P1, planear P2

---

**Responsable:** Cristhian Bravo | **Próxima revisión:** Septiembre 2026