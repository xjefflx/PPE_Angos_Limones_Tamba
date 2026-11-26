# Requerimientos Refinados y Verificables — SG-RAC

**Proyecto:** Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)
**Asignatura:** Diseño y Programación de Software (ITID543) — Escuela Politécnica Nacional
**Entregable:** 4 — Requerimientos Refinados y Verificables
**Documentos base:** `03_Catalogo_y_Refinamiento/01_Catalogo_Requerimientos.md` y `02_Informe_Analisis_Refinamiento.md`

Este documento presenta la versión final de cada requerimiento (10 RF, 4 RNF y 2 RD), redactada conforme a las reglas de una especificación formal. Cada ficha incluye identificador, nombre, enunciado, fuente, prioridad, criterio de aceptación y dependencias.

---

## 1. Reglas de redacción aplicadas

| N.º | Regla | Cómo se aplicó |
|---|---|---|
| R1 | **Verbo preciso.** Cada enunciado usa "deberá" (obligación) seguido de un verbo de acción concreto: permitir, registrar, generar, bloquear, almacenar, mostrar. | Se evitaron verbos vagos como "gestionar", "manejar" o "soportar". |
| R2 | **Una idea por oración.** Cada oración expresa una sola obligación. | Los requerimientos con varias obligaciones (RF-06, RF-09, RNF-03) se redactaron en oraciones separadas. |
| R3 | **Sin términos ambiguos.** No se usan expresiones como "adecuado", "rápido", "seguro" o "fácil" sin una definición medible. | "Rápido" se reemplazó por "menos de tres segundos". "Seguro" se reemplazó por "hash bcrypt con factor de costo mínimo de 10". "Condiciones socioambientales" se reemplazó por la lista de datos. |
| R4 | **Verificable.** Cada requerimiento tiene un criterio de aceptación que una prueba puede confirmar o refutar. | Los criterios usan formato Dado / Cuando / Entonces, con resultados observables. |
| R5 | **Trazable.** Cada requerimiento tiene identificador único, fuente y dependencias. | Los identificadores coinciden con el SRS, el catálogo, los casos de uso (CU) y las historias de usuario (HU). |

## 2. Resumen de requerimientos

| ID	|		Nombre							|		Prioridad   |				Dependencias			|
|------	|-------------------|-------------------|-----------------------------------------------------------|
| RF-01 | Autenticación del Administrador		| Must				| Ninguna								|
| RF-02 | Registro de ingreso de animales		| Must				| RF-01									|
| RF-03 | Ficha de identificación del animal	| Must				| RF-01, RF-02							|
| RF-04 | Historial médico | Must				| RF-01, RF-03		|										|	
| RF-05 | Registro de solicitantes de adopción	| Must				| RF-01									|
| RF-06 | Procesamiento de adopciones			| Must				| RF-01, RF-03, RF-05, RD-01, RD-02		|
| RF-07 | Comprobante de adopción en PDF		| Must				| RF-06 (su tiempo se verifica )		|
| RF-08 | Bitácora de seguimiento				| Should			| RF-06									|	
| RF-09 | Revocatoria de custodia				| Should			| RF-06, RF-08							|
| RF-10 | Registro de donaciones				| Should			| RF-01									|
| RNF-01 | Operación local						| Must				| Ninguna								|
| RNF-02 | Tiempo de generación del PDF			| Should			| RF-07									|	
| RNF-03 | Respaldo local						| Must				| RNF-01								|
| RNF-04 | Protección de credenciales			| Must				| RF-01									|
| RD-01 | Titularidad única | Must				| RF-05				|										|
| RD-02 | Alta médica para adopción definitiva  | Must				| RF-04									|

---

## 3. Fichas de requerimientos funcionales (RF)

### RF-01 — Autenticación del Administrador

| Campo | Contenido |
|---|---|
| **Identificador** | RF-01 |
| **Nombre** | Autenticación del Administrador |
| **Enunciado** | El sistema deberá permitir el acceso únicamente al Administrador que ingrese un usuario y una contraseña válidos. El sistema deberá denegar el acceso cuando las credenciales sean inválidas. |
| **Fuente** | Administrador (I-09) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que ingreso credenciales válidas, **cuando** confirmo, **entonces** el sistema concede el acceso al panel principal. **Dado** que ingreso credenciales inválidas, **cuando** confirmo, **entonces** el sistema deniega el acceso, muestra un mensaje de error y permite reintentar. |
| **Dependencias** | Ninguna. |

### RF-02 — Registro de ingreso de animales

| Campo | Contenido |
|---|---|
| **Identificador** | RF-02 |
| **Nombre** | Registro de ingreso de animales |
| **Enunciado** | El sistema deberá permitir registrar el ingreso de un animal indicando la fecha, el lugar del hallazgo, el contacto del rescatista y la condición física y emocional inicial. El sistema deberá indicar el campo faltante cuando falte un dato obligatorio. |
| **Fuente** | Administrador (I-01) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que completo los cuatro datos del ingreso, **cuando** guardo, **entonces** el ingreso aparece en el listado de animales del refugio. **Dado** que falta un dato obligatorio, **cuando** guardo, **entonces** el sistema no guarda el registro e indica el campo faltante. |
| **Dependencias** | RF-01. |

### RF-03 — Ficha de identificación del animal

| Campo | Contenido |
|---|---|
| **Identificador** | RF-03 |
| **Nombre** | Ficha de identificación del animal |
| **Enunciado** | El sistema deberá permitir crear la ficha de un animal con número de placa o microchip, especie, raza, edad y estado. El sistema deberá permitir editar los datos de una ficha existente. |
| **Fuente** | Administrador (I-02) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que ingreso placa o microchip, especie, raza, edad y estado, **cuando** guardo, **entonces** el sistema crea la ficha y, al consultarla, muestra los mismos datos. **Dado** que edito una ficha, **cuando** guardo, **entonces** el sistema conserva los cambios. |
| **Dependencias** | RF-01, RF-02. |

### RF-04 — Historial médico

| Campo | Contenido |
|---|---|
| **Identificador** | RF-04 |
| **Nombre** | Historial médico |
| **Enunciado** | El sistema deberá permitir al Administrador registrar vacunas, desparasitaciones, cirugías, medicación activa, revisiones periódicas y alta médica en el historial de cada animal. El sistema deberá permitir actualizar los registros del historial. |
| **Fuente** | Administrador, con información proveída por veterinarios y clínicas aliadas (I-02) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que selecciono un animal, **cuando** registro una vacuna con su fecha, **entonces** el sistema la agrega a su historial. **Dado** que registro el alta médica, **cuando** consulto el historial, **entonces** el sistema muestra el alta médica con su fecha. Cada registro queda asociado a la ficha del animal con su fecha. |
| **Dependencias** | RF-01, RF-03. |

### RF-05 — Registro de solicitantes de adopción

| Campo | Contenido |
|---|---|
| **Identificador** | RF-05 |
| **Nombre** | Registro de solicitantes de adopción |
| **Enunciado** | El sistema deberá permitir registrar al solicitante con cédula, domicilio, ocupación, tipo de vivienda, espacio disponible y número de convivientes. El sistema deberá ofrecer listas de selección para el tipo de vivienda y el espacio disponible. |
| **Fuente** | Administrador (I-03); resolución del conflicto de la matriz de interesados |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que completo los seis datos del solicitante, **cuando** guardo, **entonces** el sistema registra al solicitante. **Dado** que registré a un solicitante, **cuando** proceso una adopción, **entonces** el sistema permite seleccionarlo. **Dado** que falta un dato obligatorio, **cuando** guardo, **entonces** el sistema indica el campo faltante. |
| **Dependencias** | RF-01. |

### RF-06 — Procesamiento de adopciones

| Campo | Contenido |
|---|---|
| **Identificador** | RF-06 |
| **Nombre** | Procesamiento de adopciones |
| **Enunciado** | El sistema deberá registrar una adopción temporal con fecha de inicio, fecha límite y plan de medicación. El sistema deberá registrar una adopción definitiva asignando al solicitante como único titular. El sistema deberá bloquear la adopción definitiva de un animal sin alta médica registrada. El sistema deberá mostrar una alerta en el panel del Administrador cuando venza el plazo de una adopción temporal. |
| **Fuente** | Administrador (I-03, I-05); conflicto C-01 |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que el animal tiene alta médica, **cuando** registro una adopción definitiva, **entonces** el sistema la registra y actualiza el estado del animal. **Dado** que el animal no tiene alta médica, **cuando** intento una adopción definitiva, **entonces** el sistema la bloquea y muestra un mensaje. **Dado** que registro una adopción temporal con fecha de inicio, fecha límite y plan de medicación, **cuando** guardo, **entonces** el sistema la registra. **Dado** que una adopción temporal superó su fecha límite, **cuando** abro el panel, **entonces** el sistema muestra una alerta para esa adopción. |
| **Dependencias** | RF-01, RF-03, RF-05, RD-01, RD-02. |

### RF-07 — Comprobante de adopción en PDF

| Campo | Contenido |
|---|---|
| **Identificador** | RF-07 |
| **Nombre** | Comprobante de adopción en PDF |
| **Enunciado** | El sistema deberá generar un comprobante de adopción en formato PDF al concluir el registro de una adopción. El comprobante deberá contener los datos del animal, los datos del adoptante, los compromisos del adoptante y los espacios de firma. El sistema deberá permitir imprimir el comprobante. |
| **Fuente** | Administrador (I-06) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que la adopción fue registrada, **cuando** concluyo el registro, **entonces** el sistema genera el PDF con los datos del animal, los datos del adoptante, los compromisos y los espacios de firma. **Dado** que el PDF fue generado, **cuando** selecciono imprimir, **entonces** el sistema envía el documento a la impresora. |
| **Dependencias** | RF-06. Su tiempo de generación se verifica con RNF-02. |

### RF-08 — Bitácora de seguimiento

| Campo | Contenido |
|---|---|
| **Identificador** | RF-08 |
| **Nombre** | Bitácora de seguimiento |
| **Enunciado** | El sistema deberá permitir registrar en la bitácora cada seguimiento posterior a la adopción con fecha, visita, fotos, estado corporal y evaluación del bienestar del animal. El sistema deberá listar los seguimientos de una adopción en orden cronológico. |
| **Fuente** | Administrador (I-07) |
| **Prioridad** | Should |
| **Criterio de aceptación** | **Dado** que existe una adopción vigente, **cuando** registro una visita con fotos y estado corporal, **entonces** el sistema la agrega a la bitácora de esa adopción. **Dado** que consulto la bitácora, **cuando** la abro, **entonces** el sistema muestra los seguimientos ordenados por fecha. |
| **Dependencias** | RF-06. |

### RF-09 — Revocatoria de custodia

| Campo | Contenido |
|---|---|
| **Identificador** | RF-09 |
| **Nombre** | Revocatoria de custodia |
| **Enunciado** | El sistema deberá permitir revocar la custodia únicamente cuando el Administrador registre un criterio objetivo. Los criterios objetivos son: evaluación médica desfavorable, reincidencia en incumplimiento de cuidados e indicios de maltrato. El sistema deberá reintegrar al refugio al animal cuya custodia se revoca. |
| **Fuente** | Administrador (I-07); conflicto C-02 |
| **Prioridad** | Should |
| **Criterio de aceptación** | **Dado** que no he seleccionado un criterio objetivo, **cuando** intento confirmar la revocatoria, **entonces** el sistema lo impide. **Dado** que registro un criterio objetivo y su justificación, **cuando** confirmo, **entonces** el sistema cambia la adopción al estado "Revocatoria", registra la fecha y reintegra al animal al refugio. |
| **Dependencias** | RF-06, RF-08. |

### RF-10 — Registro de donaciones

| Campo | Contenido |
|---|---|
| **Identificador** | RF-10 |
| **Nombre** | Registro de donaciones |
| **Enunciado** | El sistema deberá permitir registrar donaciones clasificadas en alimentos, dinero, medicamentos, suministros y servicios veterinarios. El sistema deberá registrar la fecha y el donante de cada donación. |
| **Fuente** | Administrador (I-08) |
| **Prioridad** | Should |
| **Criterio de aceptación** | **Dado** que ingreso categoría, donante, fecha y monto o cantidad, **cuando** guardo, **entonces** el sistema registra la donación en su categoría. **Dado** que consulto las donaciones, **cuando** filtro por categoría, **entonces** el sistema lista solo las donaciones de esa categoría. |
| **Dependencias** | RF-01. |

---

## 4. Fichas de requerimientos no funcionales (RNF)

### RNF-01 — Operación local

| Campo | Contenido |
|---|---|
| **Identificador** | RNF-01 |
| **Nombre** | Operación local |
| **Enunciado** | El sistema deberá operar en una sola computadora sin requerir conexión a Internet. |
| **Fuente** | Administrador y Soporte TI (I-09) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que la computadora está desconectada de toda red, **cuando** ejecuto cada función del sistema (RF-01 a RF-10 y RNF-03), **entonces** cada función se completa sin error. |
| **Dependencias** | Ninguna. |

### RNF-02 — Tiempo de generación del PDF

| Campo | Contenido |
|---|---|
| **Identificador** | RNF-02 |
| **Nombre** | Tiempo de generación del PDF |
| **Enunciado** | El sistema deberá generar el comprobante PDF de adopción en menos de tres segundos en el equipo de instalación. |
| **Fuente** | Administrador |
| **Prioridad** | Should |
| **Criterio de aceptación** | **Dado** el equipo de instalación, **cuando** se generan diez comprobantes consecutivos y se cronometra cada uno, **entonces** cada generación dura menos de tres segundos. |
| **Dependencias** | RF-07. |

### RNF-03 — Respaldo local

| Campo | Contenido |
|---|---|
| **Identificador** | RNF-03 |
| **Nombre** | Respaldo local |
| **Enunciado** | El sistema deberá permitir al Administrador iniciar manualmente el respaldo de la base de datos hacia una unidad externa USB. El sistema deberá confirmar la finalización del respaldo. El sistema deberá informar al Administrador cuando no haya una unidad USB disponible. |
| **Fuente** | Soporte TI |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que conecto una unidad USB, **cuando** inicio el respaldo, **entonces** el sistema crea el archivo de respaldo en la unidad y muestra la confirmación de finalización. **Dado** que restauro el archivo de respaldo, **cuando** consulto los datos, **entonces** los datos coinciden con los del momento del respaldo. **Dado** que no hay unidad USB conectada, **cuando** inicio el respaldo, **entonces** el sistema muestra un mensaje de error. |
| **Dependencias** | RNF-01. |

### RNF-04 — Protección de credenciales

| Campo | Contenido |
|---|---|
| **Identificador** | RNF-04 |
| **Nombre** | Protección de credenciales |
| **Enunciado** | El sistema deberá almacenar la contraseña del Administrador como hash con sal mediante bcrypt, con factor de costo mínimo de 10. |
| **Fuente** | Estándar TI |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que inspecciono la base de datos, **cuando** consulto el registro del Administrador, **entonces** la contraseña no aparece en texto plano y el valor almacenado es un hash bcrypt con factor de costo igual o mayor a 10. |
| **Dependencias** | RF-01. |

---

## 5. Fichas de requerimientos de dominio (RD)

### RD-01 — Titularidad única

| Campo | Contenido |
|---|---|
| **Identificador** | RD-01 |
| **Nombre** | Titularidad única |
| **Enunciado** | El responsable legal de un animal adoptado deberá corresponder únicamente al solicitante titular. El sistema no deberá aceptar intermediarios como responsables legales. |
| **Fuente** | Reglamento RAC (I-04) |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que proceso una adopción, **cuando** intento asignar como titular a una persona distinta del solicitante, **entonces** el sistema no permite registrarla. |
| **Dependencias** | RF-05. |

### RD-02 — Alta médica para adopción definitiva

| Campo | Contenido |
|---|---|
| **Identificador** | RD-02 |
| **Nombre** | Alta médica para adopción definitiva |
| **Enunciado** | Un animal en tratamiento médico crítico no deberá entregarse en adopción definitiva sin alta médica registrada. |
| **Fuente** | Reglamento RAC |
| **Prioridad** | Must |
| **Criterio de aceptación** | **Dado** que el historial del animal no registra el alta médica, **cuando** intento una adopción definitiva, **entonces** el sistema la bloquea. **Dado** que el historial registra el alta médica, **cuando** intento una adopción definitiva, **entonces** el sistema la permite. |
| **Dependencias** | RF-04. |

---

## 6. Verificación de las reglas de redacción

Matriz de Validación de Requerimientos
Requerimiento	Precisión	Atomicidad	Claridad	Verificabilidad	Trazabilidad	Estado
RF-01				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-02				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-03				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-04				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-05				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-06				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-07				✔️			✔️			✔️				✔️				✔️	    Aprobado
RF-08				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-09				✔️			✔️			✔️				✔️				✔️		Aprobado
RF-10				✔️			✔️			✔️				✔️				✔️		Aprobado
RNF-01				✔️			✔️			✔️				✔️				✔️		Aprobado
RNF-02				✔️			✔️			✔️				✔️				✔️		Aprobado
RNF-03				✔️			✔️			✔️				✔️				✔️		Aprobado
RNF-04				✔️			✔️			✔️				✔️				✔️		AprobadoL
RD-01				✔️			✔️			✔️				✔️				✔️		Aprobado
RD-02				✔️			✔️			✔️				✔️				✔️		Aprobado|

## 7. Matriz de trazabilidad resumida

| Requerimiento | Fuente | Caso de uso | Historia de usuario |
|---|---|---|---|
| RF-01, RNF-04 | Administrador / Estándar TI | CU-01 | HU-01 |
| RF-02 | Administrador | CU-02 | HU-02 |L
| RF-03 | Administrador | CU-03 | HU-03 |
| RF-04 | Administrador | CU-04 | HU-04 |
| RF-05 | Administrador | CU-05 | HU-05 |
| RF-06, RD-01, RD-02 | Administrador / Reglamento RAC | CU-06 | HU-06 |
| RF-07, RNF-02 | Administrador | CU-07 | HU-07 |
| RF-08 | Administrador | CU-08 | HU-08 |
| RF-09 | Administrador | CU-09 | HU-09 |
| RF-10 | Administrador | CU-10 | HU-10 |
| RNF-01 | Administrador / Soporte TI | Todos | — |
| RNF-03 | Soporte TI | CU-11 | HU-11 |
