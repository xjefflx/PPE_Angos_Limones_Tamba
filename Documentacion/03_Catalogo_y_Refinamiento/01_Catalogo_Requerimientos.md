# Catálogo de Requerimientos — SG-RAC
								----- Escuela Politécnica Nacional-------------
**Proyecto:** Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)
**Asignatura:** Diseño y Programación de Software (ITID543)
**Entregable:** 3 — Catálogo de Requerimientos y Análisis de Refinamiento
**Modalidad del sistema:** Aplicación de escritorio monousuario (instalación local). Perfil de acceso: Administrador del refugio.

---

## 1. Propósito del desarrollo del ssitema delr efugiode animales 

Este catálogo organiza y clasifica todos los requerimientos identificados en la adquisición (entrevistas con el Administrador, revisión de registros físicos y observación del flujo de rescate,adopción, refugios y donaciones).
La finalidad es establecer un marco de referencia para el desarrollo del sistema, lo que permite quese cumplan las necesidades del refugio y se respeten las restricciones del dominio.
Cada requerimiento se clasifica por 
	-Tipo
		-nivel 
			- Fuente
				- 	Estado

## 2. Convenciones de clasificación

| Campo | Valores | Significado |
|---|---|---|
| Tipo | Funcional (RF), No funcional (RNF), Dominio (RD) | RF: qué hace el sistema. RNF: cómo lo hace (calidad o restricción). RD: regla impuesta por el reglamento o el dominio del refugio. |
| Nivel | Usuario / Sistema | Usuario: acción que ejecuta el Administrador. Sistema: comportamiento que el sistema realiza por sí mismo. |
| Estado | Propuesto, Analizado, Refinado, Aprobado | Propuesto: recién capturado. Analizado: examinado críticamente. Refinado: reformulado tras detectar una problemática (ver Informe de Análisis). Aprobado: respaldado por el Reglamento RAC. |

## 3. Tabla de requerimientos

Total: **16 requerimientos** (10 RF, 4 RNF, 2 RD).

### 3.1 Requerimientos funcionales (RF)

| ID | Requerimiento | Tipo | Nivel | Fuente | Estado |
|---|---|---|---|---|---|
| RF-01 | Autenticar el acceso del Administrador mediante usuario y contraseña. | Funcional | Sistema | Administrador | Analizado |
| RF-02 | Registrar el ingreso de animales rescatados (fecha, lugar del hallazgo, contacto del rescatista y condición física y emocional inicial). | Funcional | Usuario | Administrador | Analizado |
| RF-03 | Gestionar la ficha de identificación del animal (placa o microchip, especie, raza, edad y estado). | Funcional | Usuario | Administrador | Analizado |
| RF-04 | Registrar y actualizar el historial médico (vacunas, desparasitaciones, cirugías, medicación activa, revisiones periódicas y alta médica). | Funcional | Usuario | Administrador | Refinado |
| RF-05 | Registrar solicitantes de adopción con sus datos personales y sus condiciones socioambientales (tipo de vivienda, espacio disponible, número de convivientes y ocupación). | Funcional | Usuario | Administrador | Refinado |
| RF-06 | Procesar adopciones temporales (con fecha límite y alerta de vencimiento) o definitivas, asignando la titularidad al solicitante. | Funcional | Usuario | Administrador | Refinado |
| RF-07 | Generar e imprimir el comprobante o acta formal de adopción en formato PDF con los compromisos del adoptante. | Funcional | Sistema | Administrador | Analizado |
| RF-08 | Registrar la bitácora de seguimiento posterior a la adopción con evaluación del bienestar del animal. | Funcional | Usuario | Administrador | Analizado |
| RF-09 | Permitir la revocatoria de custodia solo con un criterio objetivo registrado y reintegrar al animal al refugio. | Funcional | Sistema | Administrador | Refinado |
| RF-10 | Registrar donaciones clasificadas en alimentos, dinero, medicamentos, suministros y servicios veterinarios. | Funcional | Usuario | Administrador | Refinado |

### 3.2 Requerimientos no funcionales (RNF)

| ID | Requerimiento | Tipo | Nivel | Fuente | Estado |
|---|---|---|---|---|---|
| RNF-01 | Operar de manera local e independiente en una sola computadora, sin conexión obligatoria a Internet. | No funcional | Sistema | Administrador / Soporte TI | Analizado |
| RNF-02 | Generar el comprobante PDF de adopción en menos de 3 segundos en el equipo de instalación. | No funcional | Sistema | Administrador | Refinado |
| RNF-03 | Permitir el respaldo manual de la base de datos hacia una unidad externa USB, iniciado por el Administrador y con confirmación de finalización. | No funcional | Sistema | Soporte TI | Refinado |
| RNF-04 | Almacenar la contraseña del Administrador mediante un algoritmo de hash seguro con sal. | No funcional | Sistema | Estándar TI | Refinado |

### 3.3 Requerimientos de dominio (RD)

| ID | Requerimiento | Tipo | Nivel | Fuente | Estado |
|---|---|---|---|---|---|
| RD-01 | El responsable legal del animal adoptado debe corresponder únicamente al solicitante titular, sin intermediarios. | Dominio | Sistema | Reglamento RAC | Aprobado |
| RD-02 | Un animal en tratamiento médico crítico no podrá entregarse en adopción definitiva sin alta médica registrada. | Dominio | Sistema | Reglamento RAC | Aprobado |

## 4. Resumen de la clasificación

| Tipo | Cantidad | Mínimo exigido |
|---|---|---|
| Funcionales (RF) | 10 | 6 |
| No funcionales (RNF) | 4 | 3 |
| De dominio (RD) | 2 | 2 |

| Estado | Requerimientos |
|---|---|
| Analizado | RF-01, RF-02, RF-03, RF-07, RF-08, RNF-01 |
| Refinado | RF-04, RF-05, RF-06, RF-09, RF-10, RNF-02, RNF-03, RNF-04 |
| Aprobado | RD-01, RD-02 |

## 5. Trazabilidad con la adquisición

| Requerimiento | Información de origen (Documento de adquisición) |
|---|---|
| RF-01, RNF-04 | I-09 (autenticación del Administrador) |
| RF-02 | I-01 |
| RF-03, RF-04 | I-02 |
| RF-05, RD-01 | I-03, I-04 |
| RF-06 | I-03, I-05; conflicto C-01 |
| RF-07 | I-06 |
| RF-08, RF-09 | I-07; conflicto C-02 |
| RF-10 | I-08 |
| RNF-01 | I-09 |
| RNF-02, RNF-03 | I-06 y necesidad de Soporte TI (matriz de interesados) |
| RD-02 | Reglamento RAC |

## 6. Fuera del catálogo actual

| Elemento | Decisión | Motivo |
|---|---|---|
| RF-11 Reportes estadísticos de adopciones y donaciones | Pospuesto (prioridad "Could") | No aporta valor en la primera versión. |
| Portal web de adopción en línea | Descartado ("Won't") | Contradice la arquitectura monousuario local. |
