# Visión y Alcance del Proyecto

**Proyecto:** Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)  
**Integrantes:** Jeff Alejandro Limones Chachapoya, Erika Pahola Tamba Catucuamba, Cesar Ignacio Angos Sosa  

## 1. Propósito
El propósito de este proyecto es desarrollar una aplicación de escritorio local que permita al Refugio de Animales de Compañía (RAC) organizar el ingreso de animales rescatados, llevar un control de su historial médico, gestionar las adopciones temporales o definitivas y registrar las donaciones recibidas en un solo lugar.

## 2. Alcance
El sistema contemplará las siguientes funcionalidades:
* **Acceso al sistema:** Inicio de sesión con usuario y contraseña para el Administrador encargado del refugio.
* **Registro de animales y rescates:** Ingreso de datos del animal (identificación por chip o collar, edad estimada, estado inicial al ser encontrado) y de los rescatistas o personas que lo entregan.
* **Historial médico:** Registro de revisiones veterinarias, vacunas, tratamientos y medicación necesaria por cada animal.
* **Solicitudes y adopciones:** Registro de datos del solicitante (nombre, cédula, edad, ocupación, ubicación, tipo de vivienda, espacio disponible y número de personas en el hogar) para adopciones temporales (indicando tiempo de estadía y medicación) o definitivas, asegurando que el solicitante sea la persona a cargo.
* **Comprobante de registro:** Emisión de un comprobante imprimible que respalde la entrega y el registro de la adopción.
* **Seguimiento y retiro:** Control posterior de la mascota en su hogar temporal o definitivo, permitiendo registrar su retiro si se detecta que no recibe un trato adecuado.
* **Registro de donaciones:** Control de aportes recibidos en comida (marca, peso, edad, premios), dinero (efectivo o transferencia), juguetes, medicinas y ayuda veterinaria (operaciones, controles, rehabilitaciones, consultas y vacunas).

## 3. NO Alcance
Para esta versión del proyecto quedan excluidos los siguientes aspectos:
* Desarrollo de páginas web o aplicaciones móviles.
* Conexión en red o uso simultáneo desde varias computadoras.
* Procesamiento de pagos en línea o pasarelas bancarias.
* Emisión de facturas electrónicas con validez tributaria.

## 4. Restricciones
* El sistema se instalará y ejecutará en una sola computadora dentro del refugio.
* El acceso estará habilitado únicamente para el perfil de Administrador (con posibilidad de definir otros roles más adelante).
* No requiere conexión a Internet para operar; los respaldos de información se realizarán de forma manual en medios externos (como memorias USB).

## 5. Definiciones
* **RAC:** Refugio de Animales de Compañía.
* **Adopción temporal:** Entrega provisional de un animal por un tiempo definido para su cuidado o recuperación.
* **Adopción definitiva:** Entrega permanente de un animal a un solicitante que asume su responsabilidad.
* **Retiro por seguimiento:** Recuperación del animal por parte del refugio cuando las revisiones muestran maltrato o descuido en el hogar temporal o definitivo.
