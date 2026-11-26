# Documento de Adquisición de Requerimientos

**Proyecto:** Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)  
**Integrantes:** Cesar Ignacio Angos Sosa, Jeff Alejandro Limones Chachapoya, Erika Pahola Tamba Catucuamba  

## 1. Plan de Adquisición

### 1.1 Técnicas de elicitación utilizadas
* **Entrevistas semiestructuradas:** Sesiones de preguntas abiertas y cerradas con el Administrador del refugio para comprender el flujo diario de ingreso, atención médica, adopciones y donaciones.
* **Revisión documental:** Análisis de fichas físicas de ingreso, historiales veterinarios en papel, actas manuales de adopción y cuadernos de control de donativos del RAC.
* **Observación directa:** Seguimiento presencial de los procedimientos de recepción de animales rescatados y atención a solicitantes de adopción en la estación de trabajo del refugio.

### 1.2 Fuentes consultadas
* **Administrador del Refugio (RAC):** Principal responsable operativo de ingresos, evaluaciones de adoptantes, seguimientos y control de inventario.
* **Reglamento Interno del RAC:** Normativa operativa sobre requisitos de adopción temporal/definitiva, titularidad legal y causales de revocatoria.
* **Registros físicos históricos:** Formatos impresos de fichas clínicas, actas de entrega en adopción y libretas de registro de donaciones.
* **Personal veterinario aliado y soporte técnico:** Referencias sobre el registro de tratamientos clínicos y condiciones técnicas del equipo de cómputo del refugio.

### 1.3 Cronograma de adquisición y responsables

| Fase / Fecha | Actividad de adquisición | Técnica aplicada | Responsable |
| :--- | :--- | :--- | :--- |
| **Fase 1 (Semana 1)** | Levantamiento inicial del contexto operativo del refugio, roles y restricciones técnicas del equipo local. | Entrevista inicial y observación directa | Cesar Ignacio Angos Sosa |
| **Fase 2 (Semana 1)** | Revisión de formatos físicos de ingreso de rescates, historiales médicos y actas manuales de adopción. | Revisión documental | Erika Pahola Tamba Catucuamba |
| **Fase 3 (Semana 2)** | Entrevista de profundización sobre adopciones temporales, seguimiento post-adopción, revocatorias y tipos de donaciones. | Entrevista semiestructurada | Jeff Alejandro Limones Chachapoya |
| **Fase 4 (Semana 2)** | Sesión de validación de dudas, aclaración de reglas de negocio y resolución de conflictos detectados. | Reunión de validación en equipo | Todo el equipo (Angos, Limones, Tamba) |

---

## 2. Tabla de Información Registrada

| ID | Información obtenida | Fuente | Aclaración / Respuesta |
| :--- | :--- | :--- | :--- |
| **I-01** | El sistema requiere un control de acceso restringido antes de mostrar la información del refugio. | Administrador del RAC | Se confirma inicio de sesión mediante usuario y contraseña exclusivos para el perfil de Administrador. |
| **I-02** | Se debe registrar cada animal rescatado que ingresa al refugio junto con los datos de quien lo entrega. | Administrador del RAC | Se confirma registrar fecha de ingreso, lugar del hallazgo, nombre y contacto del rescatista y condición física inicial. |
| **I-03** | Cada animal necesita una identificación única dentro del sistema para evitar confusiones. | Registros físicos del RAC | Se aclara registrar código de microchip o número de placa/collar, además de especie, raza, sexo, color y edad estimada. |
| **I-04** | Es necesario llevar un expediente médico individualizado desde el ingreso del animal. | Administrador / Veterinario aliado | Se confirma incluir historial de vacunas, desparasitaciones, cirugías, diagnósticos, recetas y revisiones periódicas. |
| **I-05** | Los animales en tratamiento médico delicado requieren control especial antes de ser adoptados. | Reglamento Interno RAC | Se aclara que un animal en tratamiento crítico no puede pasar a adopción definitiva hasta contar con alta médica. |
| **I-06** | Las personas interesadas pueden postular a una adopción temporal o a una adopción definitiva. | Administrador del RAC | Se confirma que el sistema debe diferenciar claramente ambas modalidades al momento de registrar la solicitud. |
| **I-07** | Se deben recopilar datos personales y del entorno del hogar de cada solicitante de adopción. | Administrador del RAC | Se confirma registrar nombres completos, cédula, edad, ocupación, dirección, tipo de vivienda, espacio disponible y número de convivientes. |
| **I-08** | El solicitante debe figurar como único titular responsable del animal entregado. | Reglamento Interno RAC | Se confirma que no se permiten intermediarios; la persona que firma la solicitud asume la custodia legal directa. |
| **I-09** | En las adopciones temporales se necesita controlar el tiempo de permanencia y cuidados especiales. | Administrador del RAC | Se aclara registrar fecha de inicio, fecha límite de estadía y el esquema de medicación que debe cumplirse durante ese período. |
| **I-10** | Al aprobarse una adopción se debe entregar un documento físico de respaldo al adoptante. | Administrador / Actas manuales | Se confirma que el sistema debe generar un comprobante/acta oficial en formato PDF listo para imprimir con datos y compromisos. |
| **I-11** | El refugio realiza controles posteriores para verificar el bienestar de los animales adoptados. | Administrador del RAC | Se confirma registrar una bitácora de seguimiento periódico con fecha, observaciones del estado físico y cumplimiento de cuidados. |
| **I-12** | Si se detecta maltrato o descuido durante el seguimiento, el refugio debe poder recuperar al animal. | Reglamento Interno RAC | Se confirma habilitar la opción de revocatoria de custodia, registrando el motivo justificado y reintegrando el animal al refugio. |
| **I-13** | Se reciben donaciones de distintos tipos que actualmente se anotan en cuadernos separados. | Libretas de control RAC | Se aclara clasificar las donaciones en cinco categorías: comida, dinero, juguetes, medicinas y ayuda veterinaria. |
| **I-14** | Cada categoría de donación requiere datos específicos para llevar un inventario útil. | Administrador del RAC | Se confirma detallar marca, peso y etapa en comida; monto y método (efectivo/transferencia) en dinero; y tipo de atención en ayuda veterinaria. |
| **I-15** | El sistema operará en una sola computadora dentro de las instalaciones del refugio sin depender de Internet. | Administrador / Soporte TI | Se confirma arquitectura de escritorio local monousuario con opción de respaldo manual de la base de datos en unidad externa (USB). |

---

## 3. Preguntas de Aclaración y Respuestas Obtenidas

1. **¿El sistema será utilizado simultáneamente por varios voluntarios desde distintas computadoras o teléfonos?**  
   * **Respuesta:** No. El refugio dispone de una única computadora en recepción y por ahora solo el Administrador operará el sistema de forma local, aunque a futuro podrían definirse otros roles.
2. **¿Puede un familiar o representante retirar al animal en nombre del solicitante registrado en la adopción?**  
   * **Respuesta:** No. Por política del refugio, el solicitante registrado en el formulario debe ser obligatoriamente la persona titular que asume el cuidado directo del animal.
3. **¿Qué diferencia existe en los datos registrados entre una adopción temporal y una definitiva?**  
   * **Respuesta:** En ambas se registran los datos completos del adoptante y su vivienda, pero en la adopción temporal se debe especificar obligatoriamente la fecha de finalización de la estadía y la medicación o tratamiento que requiere el animal durante ese tiempo.
4. **¿Qué ocurre en el sistema si durante una visita o llamada de seguimiento se comprueba que el animal está en malas condiciones?**  
   * **Respuesta:** Se registra el hallazgo en la bitácora de seguimiento y se ejecuta el retiro del animal, cambiando su estado nuevamente a disponible o en recuperación dentro del refugio.
5. **¿Qué nivel de detalle se necesita registrar cuando alguien dona alimentos o servicios veterinarios?**  
   * **Respuesta:** Para alimentos se necesita la marca, el peso y si es para cachorro o adulto; para ayuda veterinaria se debe registrar si corresponde a consulta, vacuna, cirugía, control o rehabilitación.
6. **¿Cómo se protegerá la información si ocurre un fallo eléctrico o daño en la computadora del refugio?**  
   * **Respuesta:** El sistema incluirá una función sencilla para exportar una copia de seguridad de la base de datos hacia una memoria USB externa de forma periódica.

---

## 4. Registro de Conflictos Detectados

| ID | Conflicto detectado | Interesados involucrados | Descripción | Estado |
| :--- | :--- | :--- | :--- | :--- |
| **C-01** | **Cantidad de requisitos solicitados vs. agilidad del trámite** | Administrador del RAC y Adoptantes | El Administrador exige registrar múltiples datos personales y condiciones de vivienda para garantizar la seguridad del animal, mientras que los adoptantes esperan un proceso rápido y sencillo. Se acordó organizar el formulario con listas desplegables estandarizadas y emisión automática del comprobante PDF. | Resuelto |
| **C-02** | **Ambigüedad en el control de plazos de hogares temporales** | Administrador del RAC y Adoptantes temporales | En los registros manuales no existía una fecha estricta de retorno ni recordatorios de medicación, generando retrasos en la devolución de animales en recuperación. Se estipuló el registro obligatorio de fecha fin de estadía y alertas visuales en el sistema. | Resuelto |
| **C-03** | **Criterios subjetivos para ejecutar el retiro de un animal** | Administrador del RAC, Veterinarios y Adoptantes | El retiro de una mascota por descuido podía generar discusiones al no existir un respaldo formal de las observaciones. Se estableció el registro obligatorio de una bitácora de seguimiento con evidencias y causales objetivas antes de activar la revocatoria. | Resuelto |
