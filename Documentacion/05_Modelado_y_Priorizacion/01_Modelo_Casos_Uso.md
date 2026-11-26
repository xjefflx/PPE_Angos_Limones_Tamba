# 01. Modelo de Casos de Uso
## Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

### 1. Propósito
Este documento identifica los actores que interactúan con el SG-RAC y describe sus casos de uso. El modelo se deriva del SRS del proyecto. El sistema es una aplicación de escritorio monousuario, instalada localmente y operada por el Administrador del refugio.

### 2. Alcance y límite del sistema
El SG-RAC permite administrar el ingreso e identificación de animales, sus expedientes médicos, solicitantes y procesos de adopción, seguimiento posterior, revocatoria de custodia y donaciones. También contempla autenticación, generación de actas PDF y respaldo local.

### 3. Actores

| Actor | Tipo | Responsabilidad / interacción |
|---|---|---|
| Administrador del refugio | Primario | Usuario operativo del sistema. Registra animales, expedientes médicos, solicitantes, adopciones, seguimientos, revocatorias y donaciones. |
| Rescatista / Entregador | Secundario externo | Proporciona información del rescate y entrega del animal. La información es registrada por el Administrador. |
| Adoptante | Secundario externo | Proporciona sus datos y condiciones socioambientales y asume la titularidad y compromisos de custodia. |
| Veterinario / Clínica aliada | Secundario externo | Proporciona información clínica, tratamientos, revisiones y servicios médicos. |
| Donante | Secundario externo | Entrega donaciones en especie, dinero, suministros o servicios. |
| Soporte TI | Secundario de soporte | Apoya el respaldo local y mantenimiento técnico de la instalación. |

**Nota:** El perfil de acceso definido en el SRS es el Administrador. Los actores externos no tienen acceso directo al sistema en el alcance documentado; sus datos o aportes son ingresados por el Administrador.

### 4. Listado de casos de uso

| ID | Caso de uso | Actor principal | Requerimientos relacionados |
|---|---|---|---|
| CU-01 | Iniciar sesión | Administrador | RF-01, RNF-04 |
| CU-02 | Registrar ingreso de animal rescatado | Administrador | RF-02 |
| CU-03 | Gestionar ficha de identificación del animal | Administrador | RF-03 |
| CU-04 | Gestionar expediente médico | Administrador | RF-04, RD-02 |
| CU-05 | Registrar solicitante de adopción | Administrador | RF-05 |
| CU-06 | Procesar adopción temporal o definitiva | Administrador | RF-06, RD-01, RD-02 |
| CU-07 | Generar e imprimir acta de adopción | Administrador | RF-07, RNF-02 |
| CU-08 | Registrar seguimiento post-adopción | Administrador | RF-08 |
| CU-09 | Revocar custodia y reintegrar animal | Administrador | RF-09 |
| CU-10 | Registrar donación | Administrador | RF-10 |
| CU-11 | Realizar respaldo local de la base de datos | Administrador / Soporte TI | RNF-03 |

### 5. Descripción detallada de casos de uso

#### CU-01. Iniciar sesión
- **Actor principal:** Administrador.
- **Objetivo:** Acceder de forma segura a las funciones del SG-RAC.
- **Precondiciones:** La aplicación está instalada y existe una cuenta de Administrador.
- **Flujo principal:**
  1. El Administrador abre la aplicación.
  2. El sistema presenta el formulario de autenticación.
  3. El Administrador ingresa usuario y contraseña.
  4. El sistema verifica las credenciales.
  5. El sistema permite el acceso al panel principal.
- **Flujos alternativos:**
  - A1. Si los datos son incorrectos, el sistema rechaza el acceso y muestra un mensaje de error.
  - A2. Si faltan campos, el sistema solicita completar la información.
- **Postcondiciones:** Se inicia una sesión autorizada o se mantiene el acceso denegado.

#### CU-02. Registrar ingreso de animal rescatado
- **Actor principal:** Administrador.
- **Objetivo:** Registrar el ingreso de un animal y la información inicial del rescate.
- **Precondiciones:** El Administrador inició sesión y el animal fue entregado al refugio.
- **Flujo principal:**
  1. El Administrador selecciona la opción de registrar ingreso.
  2. El sistema presenta el formulario correspondiente.
  3. El Administrador ingresa fecha, lugar del hallazgo, datos de contacto del rescatista y condición física/emocional inicial.
  4. El Administrador confirma el registro.
  5. El sistema valida y almacena la información.
- **Flujos alternativos:**
  - A1. Si faltan datos obligatorios, el sistema solicita completarlos.
  - A2. Si ocurre un error de almacenamiento, el sistema informa que el registro no pudo completarse.
- **Postcondiciones:** El ingreso queda registrado y puede asociarse con la ficha del animal.

#### CU-04. Gestionar expediente médico
- **Actor principal:** Administrador.
- **Actor secundario relacionado:** Veterinario / Clínica aliada (fuente de información).
- **Objetivo:** Mantener el historial médico actualizado.
- **Precondiciones:** El animal está registrado en el sistema.
- **Flujo principal:**
  1. El Administrador busca y selecciona un animal.
  2. Abre su expediente médico.
  3. Registra o actualiza vacunas, desparasitaciones, cirugías, medicación activa y revisiones.
  4. Guarda los cambios.
  5. El sistema conserva la información asociada al animal.
- **Flujos alternativos:**
  - A1. Si el animal no existe, el sistema informa que primero debe registrarse.
  - A2. Si la información está incompleta, el sistema solicita corregirla.
- **Postcondiciones:** El expediente médico queda actualizado. La información clínica permite verificar restricciones de adopción.

#### CU-06. Procesar adopción temporal o definitiva
- **Actor principal:** Administrador.
- **Actor secundario relacionado:** Adoptante.
- **Objetivo:** Registrar la adopción y asignar la titularidad al solicitante responsable.
- **Precondiciones:** El animal y el solicitante están registrados; el animal cumple las condiciones de entrega.
- **Flujo principal:**
  1. El Administrador selecciona el animal y al solicitante.
  2. El sistema presenta los datos del animal y del solicitante.
  3. El Administrador selecciona adopción temporal o definitiva.
  4. Para una adopción temporal, registra fecha de inicio, fecha fin estimada y plan de medicación del período.
  5. El sistema verifica que el solicitante sea el titular y que no exista una condición médica crítica sin alta.
  6. El Administrador confirma la operación.
  7. El sistema registra la adopción y la titularidad.
- **Flujos alternativos:**
  - A1. Si el solicitante no es el titular responsable, el sistema impide continuar.
  - A2. Si el animal está en tratamiento médico crítico sin alta, se bloquea la adopción definitiva.
  - A3. Si la modalidad es temporal y falta la fecha fin, el sistema solicita completarla.
- **Postcondiciones:** La adopción queda registrada con su modalidad y titular. Si es temporal, queda definido el plazo y el plan correspondiente.

#### CU-07. Generar e imprimir acta de adopción
- **Actor principal:** Administrador.
- **Objetivo:** Obtener un comprobante formal en PDF.
- **Precondiciones:** Existe una adopción registrada con los datos necesarios.
- **Flujo principal:**
  1. El Administrador selecciona una adopción.
  2. Solicita generar el acta.
  3. El sistema reúne los datos del animal, adoptante y compromisos.
  4. El sistema genera el documento PDF.
  5. El Administrador revisa e imprime o conserva el archivo.
- **Flujos alternativos:**
  - A1. Si faltan datos requeridos, el sistema informa qué información debe completarse.
  - A2. Si ocurre un error al generar el PDF, el sistema notifica el fallo.
- **Postcondiciones:** Se dispone de un comprobante formal imprimible.

#### CU-08. Registrar seguimiento post-adopción
- **Actor principal:** Administrador.
- **Objetivo:** Documentar el bienestar del animal después de la adopción.
- **Precondiciones:** Existe una adopción registrada.
- **Flujo principal:**
  1. El Administrador localiza la adopción.
  2. Registra fecha y observaciones de seguimiento.
  3. Incorpora la evaluación del estado corporal y, cuando corresponda, fotografías.
  4. Guarda la bitácora.
  5. El sistema asocia el seguimiento con el animal y la adopción.
- **Flujos alternativos:**
  - A1. Si no existe una adopción asociada, el sistema impide registrar el seguimiento.
  - A2. Si faltan datos obligatorios, solicita completarlos.
- **Postcondiciones:** La bitácora queda almacenada para futuras evaluaciones.

#### CU-09. Revocar custodia y reintegrar animal
- **Actor principal:** Administrador.
- **Objetivo:** Registrar la revocatoria cuando existan causas justificadas.
- **Precondiciones:** El animal se encuentra bajo custodia de un adoptante y existe evidencia de seguimiento.
- **Flujo principal:**
  1. El Administrador revisa la bitácora de seguimiento.
  2. Identifica una causa objetiva: evaluación médica desfavorable, reincidencia en incumplimiento de cuidados o indicios de maltrato.
  3. Registra la justificación de revocatoria.
  4. Confirma la revocatoria.
  5. El sistema actualiza el estado de custodia y registra el reintegro al refugio.
- **Flujos alternativos:**
  - A1. Si no existe justificación documentada, el sistema solicita completar la evidencia.
  - A2. Si el animal no está bajo custodia de un adoptante, el sistema no permite la revocatoria.
- **Postcondiciones:** La revocatoria queda documentada y el animal figura reintegrado al refugio.

#### CU-10. Registrar donación
- **Actor principal:** Administrador.
- **Actor secundario relacionado:** Donante.
- **Objetivo:** Mantener un registro de los aportes recibidos.
- **Precondiciones:** El Administrador inició sesión y se recibió una donación.
- **Flujo principal:**
  1. El Administrador selecciona registrar donación.
  2. Selecciona la categoría: alimento, dinero, medicamentos, juguetes/suministros o servicios.
  3. Ingresa los datos correspondientes al tipo de aporte.
  4. Confirma el registro.
  5. El sistema almacena la donación.
- **Flujos alternativos:**
  - A1. Si faltan datos necesarios para la categoría seleccionada, el sistema solicita completarlos.
  - A2. Si el registro no puede guardarse, el sistema informa el error.
- **Postcondiciones:** La donación queda registrada y clasificada.

### 6. Reglas de dominio relevantes
- **RD-01:** El responsable legal del animal adoptado debe corresponder unívocamente con el solicitante titular.
- **RD-02:** Un animal en tratamiento médico crítico no podrá ser entregado en adopción definitiva sin alta médica.
- En adopciones temporales se controla la fecha límite de estadía y el plan de medicación.
- La revocatoria debe sustentarse en criterios objetivos documentados en la bitácora.

### 7. Requerimientos no funcionales relacionados
- **RNF-01:** Operación local e independiente, sin conexión obligatoria a Internet.
- **RNF-02:** Generación del comprobante PDF en menos de 3 segundos.
- **RNF-03:** Respaldo manual local de la base de datos hacia una unidad externa (USB).
- **RNF-04:** Credenciales protegidas mediante cifrado y algoritmos de hashing seguros.

### 8. Observaciones
Los casos de uso describen el comportamiento esperado a partir del SRS. Los detalles de interfaz, mensajes exactos y reglas adicionales deberán confirmarse durante el diseño y la validación con el Administrador.
