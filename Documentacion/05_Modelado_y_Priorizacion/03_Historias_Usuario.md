# 03. Historias de Usuario
## Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

Las historias se redactan desde la perspectiva de los interesados identificados en el SRS. Cada historia se vincula con uno o más requerimientos y contiene criterios de aceptación en formato Given/When/Then.

### HU-01. Autenticación del Administrador
**Como** Administrador del refugio, **quiero** iniciar sesión con usuario y contraseña, **para** proteger la información y permitir el acceso únicamente al perfil autorizado.

- **Requerimiento asociado:** RF-01, RNF-04.
- **Criterio 1**
  - **Given:** que el Administrador tiene credenciales registradas.
  - **When:** ingresa usuario y contraseña válidos.
  - **Then:** el sistema permite el acceso al panel principal.
- **Criterio 2**
  - **Given:** que el Administrador se encuentra en el formulario de acceso.
  - **When:** ingresa credenciales incorrectas.
  - **Then:** el sistema rechaza el acceso y muestra un mensaje de error.

### HU-02. Registro de ingreso de animales
**Como** Administrador del refugio, **quiero** registrar los datos del ingreso de cada animal rescatado, **para** conservar el origen y las condiciones iniciales de recepción.

- **Requerimiento asociado:** RF-02.
- **Criterio 1**
  - **Given:** que el Administrador inició sesión y dispone de los datos del rescate.
  - **When:** registra fecha, lugar, rescatista y condición inicial.
  - **Then:** el sistema guarda el ingreso asociado al animal.
- **Criterio 2**
  - **Given:** que el formulario de ingreso contiene campos obligatorios vacíos.
  - **When:** el Administrador intenta guardar.
  - **Then:** el sistema solicita completar la información requerida.

### HU-03. Gestión de identificación del animal
**Como** Administrador del refugio, **quiero** mantener una ficha de identificación por animal, **para** consultar y actualizar sus datos de manera centralizada.

- **Requerimiento asociado:** RF-03.
- **Criterio 1**
  - **Given:** que un animal ya fue registrado.
  - **When:** el Administrador ingresa o actualiza microchip/placa, especie, raza, edad o estado.
  - **Then:** el sistema almacena los cambios en su ficha.
- **Criterio 2**
  - **Given:** que el Administrador busca un animal registrado.
  - **When:** selecciona el resultado.
  - **Then:** el sistema muestra la ficha correspondiente.

### HU-04. Expediente médico
**Como** Administrador del refugio, **quiero** registrar vacunas, desparasitaciones, cirugías, medicación y revisiones, **para** disponer del historial clínico actualizado de cada animal.

- **Requerimiento asociado:** RF-04, RD-02.
- **Criterio 1**
  - **Given:** que el animal está registrado.
  - **When:** el Administrador añade información médica y guarda.
  - **Then:** el sistema asocia el registro al expediente del animal.
- **Criterio 2**
  - **Given:** que el expediente indica tratamiento médico crítico sin alta.
  - **When:** el Administrador intenta procesar una adopción definitiva.
  - **Then:** el sistema impide la entrega conforme a RD-02.

### HU-05. Registro de solicitante
**Como** Administrador del refugio, **quiero** registrar los datos personales y socioambientales del solicitante, **para** evaluar y documentar su idoneidad como responsable de un animal.

- **Requerimiento asociado:** RF-05.
- **Criterio 1**
  - **Given:** que una persona solicita adoptar.
  - **When:** el Administrador registra identificación, domicilio, ocupación, espacio disponible y convivientes.
  - **Then:** el sistema almacena la información del solicitante.
- **Criterio 2**
  - **Given:** que faltan datos obligatorios del solicitante.
  - **When:** el Administrador intenta guardar.
  - **Then:** el sistema indica los campos que deben completarse.

### HU-06. Procesamiento de adopción
**Como** Administrador del refugio, **quiero** registrar adopciones temporales o definitivas y asignar un titular, **para** formalizar la custodia del animal.

- **Requerimiento asociado:** RF-06, RD-01, RD-02.
- **Criterio 1**
  - **Given:** que el animal y el solicitante están registrados y cumplen las condiciones.
  - **When:** el Administrador confirma la modalidad de adopción y el titular.
  - **Then:** el sistema registra la adopción y asigna la titularidad al solicitante responsable.
- **Criterio 2**
  - **Given:** que se trata de una adopción temporal.
  - **When:** el Administrador registra fecha de inicio, fecha fin estimada y plan de medicación.
  - **Then:** el sistema conserva estos datos para controlar el período.
- **Criterio 3**
  - **Given:** que el solicitante no es el titular o el animal está en tratamiento crítico sin alta para una adopción definitiva.
  - **When:** el Administrador intenta confirmar.
  - **Then:** el sistema bloquea la operación.

### HU-07. Acta de adopción en PDF
**Como** Administrador del refugio, **quiero** generar un comprobante formal de adopción en PDF, **para** documentar los datos del animal, adoptante y compromisos asumidos.

- **Requerimiento asociado:** RF-07, RNF-02.
- **Criterio 1**
  - **Given:** que existe una adopción registrada con sus datos.
  - **When:** el Administrador solicita generar el acta.
  - **Then:** el sistema produce un PDF con los datos del animal, adoptante y firmas.
- **Criterio 2**
  - **Given:** que se solicita generar un comprobante.
  - **When:** el sistema procesa la solicitud.
  - **Then:** la generación se completa en menos de 3 segundos.

### HU-08. Seguimiento post-adopción
**Como** Administrador del refugio, **quiero** registrar visitas, fotografías y evaluaciones del estado corporal, **para** mantener una bitácora del bienestar del animal.

- **Requerimiento asociado:** RF-08.
- **Criterio 1**
  - **Given:** que existe una adopción registrada.
  - **When:** el Administrador registra una visita y su evaluación.
  - **Then:** el sistema guarda la información en la bitácora asociada.
- **Criterio 2**
  - **Given:** que se necesita revisar el historial de seguimiento.
  - **When:** el Administrador consulta la bitácora.
  - **Then:** el sistema presenta los registros existentes.

### HU-09. Revocatoria de custodia
**Como** Administrador del refugio, **quiero** registrar la revocatoria cuando existan causas objetivas, **para** proteger al animal y documentar su reintegro al refugio.

- **Requerimiento asociado:** RF-09.
- **Criterio 1**
  - **Given:** que la bitácora contiene una evaluación médica desfavorable, reincidencia en incumplimiento de cuidados o indicios de maltrato.
  - **When:** el Administrador registra la justificación y confirma la revocatoria.
  - **Then:** el sistema registra la revocatoria y el reintegro.
- **Criterio 2**
  - **Given:** que no existe una justificación documentada.
  - **When:** el Administrador intenta revocar la custodia.
  - **Then:** el sistema solicita registrar la causa objetiva.

### HU-10. Registro de donaciones
**Como** Administrador del refugio, **quiero** registrar y clasificar las donaciones recibidas, **para** mantener constancia de los aportes al refugio.

- **Requerimiento asociado:** RF-10.
- **Criterio 1**
  - **Given:** que el refugio recibe una donación.
  - **When:** el Administrador selecciona su categoría e ingresa los datos correspondientes.
  - **Then:** el sistema almacena el aporte clasificado.
- **Criterio 2**
  - **Given:** que se selecciona una categoría de donación.
  - **When:** faltan datos necesarios para registrarla.
  - **Then:** el sistema solicita completar la información.

### HU-11. Respaldo local
**Como** Administrador del refugio o personal de Soporte TI, **quiero** realizar un respaldo manual de la base de datos en una unidad externa, **para** disponer de una copia de seguridad local.

- **Requerimiento asociado:** RNF-03.
- **Criterio 1**
  - **Given:** que la aplicación está operativa y existe una unidad USB disponible.
  - **When:** se ejecuta la opción de respaldo.
  - **Then:** el sistema genera una copia local de la base de datos en la unidad seleccionada.
- **Criterio 2**
  - **Given:** que no se puede acceder a la unidad externa.
  - **When:** se intenta realizar el respaldo.
  - **Then:** el sistema informa que el respaldo no pudo completarse.

### Observación
Las historias y criterios son propuestas verificables derivadas del SRS. Deben revisarse con el Administrador del refugio antes de considerarse aprobadas.
