# 04. Matriz de Priorización MoSCoW
## Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

### 1. Objetivo
Priorizar los requerimientos del SG-RAC según su importancia para la operación del refugio. MoSCoW clasifica los elementos en Must have, Should have, Could have y Won't have (por ahora).

### 2. Criterios utilizados
- **Must have (M):** indispensable para que el sistema cumpla su propósito y las reglas esenciales del refugio.
- **Should have (S):** importante, pero su ausencia temporal no impide la operación básica.
- **Could have (C):** aporta valor adicional y puede implementarse si existen recursos.
- **Won't have (W):** no se contempla en la versión actual; podría evaluarse en una versión futura.

### 3. Matriz de priorización propuesta

| ID | Requerimiento | Prioridad | Justificación |
|---|---|---|---|
| RF-01 | Autenticar al Administrador | Must have | Protege el acceso a la información del refugio. |
| RF-02 | Registrar ingreso de animales | Must have | Es el punto inicial del control de los animales. |
| RF-03 | Gestionar ficha de identificación | Must have | Permite identificar inequívocamente a cada animal. |
| RF-04 | Mantener historial médico | Must have | Es necesario para el cuidado y para verificar condiciones de adopción. |
| RF-05 | Registrar solicitantes y condiciones socioambientales | Must have | Permite documentar quién solicita la adopción y su contexto. |
| RF-06 | Procesar adopciones temporales y definitivas | Must have | Formaliza la asignación de custodia y titularidad. |
| RF-07 | Generar acta de adopción PDF | Should have | Formaliza documentalmente la entrega; es importante para el proceso. |
| RF-08 | Registrar seguimiento post-adopción | Must have | Permite evaluar el bienestar y sustentar decisiones posteriores. |
| RF-09 | Revocar custodia y reintegrar al animal | Must have | Es necesario para actuar ante incumplimientos o indicios de maltrato. |
| RF-10 | Registrar donaciones | Should have | Facilita el control de aportes, aunque no constituye el flujo central de adopción. |
| RNF-01 | Operar localmente sin Internet obligatorio | Must have | Define la modalidad de despliegue establecida para el proyecto. |
| RNF-02 | Generar PDF en menos de 3 segundos | Should have | Establece un objetivo medible de rendimiento para el comprobante. |
| RNF-03 | Respaldo manual en unidad externa | Should have | Reduce el riesgo de pérdida de información. |
| RNF-04 | Proteger credenciales mediante hashing seguro | Must have | Es esencial para proteger el acceso. |
| RD-01 | Titular legal igual al solicitante titular | Must have | Regla obligatoria para formalizar la custodia. |
| RD-02 | No entregar definitivamente animales en tratamiento crítico sin alta | Must have | Regla esencial de protección y seguridad del animal. |

### 4. Elementos fuera del alcance actual
No se incorporan funcionalidades adicionales no descritas en el SRS, como portal web público, aplicación móvil, acceso multiusuario remoto, pagos en línea o integración automática con clínicas. Se consideran fuera del alcance de esta versión, no como compromisos de desarrollo.

### 5. Acuerdo de negociación
La matriz anterior constituye una **propuesta de priorización** derivada del alcance y los riesgos descritos en el SRS. Para convertirla en acuerdo formal, el Administrador del refugio y el equipo del proyecto deben revisar las prioridades y registrar su aprobación.

| Participante | Decisión | Fecha | Evidencia |
|---|---|---|---|
| Administrador del refugio | Pendiente de revisión y aprobación | Por definir | Acta o confirmación de aprobación |
| Equipo de desarrollo | Prioridades propuestas | Por definir | Revisión interna del documento |

### 6. Conclusión
La prioridad se concentra en el registro e identificación de animales, el expediente médico, la gestión de adopciones y el seguimiento. Las reglas RD-01 y RD-02 y la protección de credenciales se consideran obligatorias para evitar asignaciones incorrectas de custodia y accesos no autorizados.
