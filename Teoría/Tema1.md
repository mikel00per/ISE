# Introducción A la Ingeniería de Servidores

## ¿Qué es un servidor?

**Sistema Informático**

Conjunto de elementos hardware, software y humanware interrelacionados entre sí que permite obtener, procesar y almacenar información.
  - Hardware: conjunto de componentes físicos que forman el sistema informático: procesadores, memoria, almacenamiento, cables, etc.
  - Software: conjunto de componentes lógicos que forman el sistema informático: sistema operativo y aplicaciones.
  - Humanware: conjunto de recursos humanos. En nuestro caso, personal técnico que crea y mantiene el sistema (administradores, analistas, programadores, operarios, etc.) y los usuarios que lo utilizan.

**Clasificación de Sistemas Informáticos**

Los Sistemas Informáticos pueden clasificarse según numerosos
criterios. Por supuesto las clasificaciones no son estancas y es común
encontrar sistemas híbridos que no encajen en una única categoría.

Ejemplos de clasificación:
  - Según el nivel de paralelismo de su arquitectura: SISD, SIMD, MISD o MIMD.
  - Según su uso: De uso general o de uso específico.
  - Según la arquitectura de servicio (para el caso de servidores): Sistema aislado, Arquitectura cliente-servidor, Arquitectura de n capas o Arquitectura Cliente-Cola-Cliente.

**Paralelismo arquitectura**

Según el paralelismo de su arquitectura:
  - SISD: Single Instruction Single Data
  - SIMD: Single Instruction Multiple Data
  - MISD: Multiple Instruction Single Data
  - MIMD: Multiple Instruction Multiple Data

**Según su uso**

Según su uso, un sistema informático puede considerarse:
  - **De uso general**, como los computadorespersonales (PC) que son utilizados por un usuario para ejecutar muy diversas aplicaciones.
  - **De uso específico**:
    - **Sistemas empotrados (embedded systems**: Sistemas informáticos acoplados a otro dispositivo o aparato, diseñados para realizar una o algunas funciones dedicadas, frecuentemente con fuertes restricciones de tamaño, tiempo de respuesta (sistemas de tiempo real), consumo y coste. Suelen estar formados por un microcontrolador, memoria y una amplia gama de interfaces de comunicación. Ejemplo: un taxímetro, un sistema de control de acceso, el sistema de control de una fotocopiadora, una cámara de vigilancia...

    - **Servidores (servers)**: Son sistemas informáticos que, formando parte de una red, proporcionan servicios a otros sistemas informáticos denominados clientes. Un servidor no es necesariamente una máquina de última generación de grandes proporciones; un servidor puede ser desde un computador de gama baja (coste bajo) hasta un conjunto de clusters de computadores (=asociación de computadores de modo que pueden ser percibidos externamente como un único sistema) en un Centro de Procesamiento de Datos (CPD). **Tipos de servidores:**
      - **Servidor de archivos**: permite el acceso remoto a archivos almacenados en él o directamente accesibles por este.
      - **Servidor web**: almacena documentos HTML, imágenes, archivos de texto, escrituras, y distribuye este contenido a clientes que lo soliciten en la red.
      - **Servidor de base de datos**: provee servicios de base de datos a otros programas u otras computadoras. Servidor de comercio-e: cumple o procesa transacciones comerciales (comercio electrónico). Valida el cliente y genera un pedido al servidor de bases de datos.
      - **Servidor de impresión**: controla una o más impresoras y acepta trabajos de impresión de otros clientes de la red.
      - **Servidor de correo-e**: almacena, envía, recibe, re-enruta y realiza otras operaciones relacionadas con e-mail para los clientes de la red.

**Según la arquitectura de servicio**
  - **Sistema aislado**: Sistema computacional que no interactúa con otros sistemas. Arquitectura monolítica en la que no existe distribución de la información. Por ejemplo: computadores personales.
  - **Arquitectura cliente/servidor**: Es un modelo de aplicación distribuida en el que las tareas se reparten entre los proveedores de recursos o servicios, llamados servidores, y los demandantes, llamados clientes. los clientes (remitentes de solicitudes) y los servidores (receptores de solicitudes)
  - **Arquitectura cliente/servidor de n capas** Es una arquitectura cliente/servidor que tiene n tipos de nodos en la red. Mejora la distribución de carga entre los diversos servidores. Es más escalable. Pone más carga en la red. Difícil de programar y administrar. Ejemplo de arquitectura de 3 capas:
    - **Capa 1**: Servidores que interactúan con los usuarios finales (clientes).
    - **Capa 2**: Servidores de comercio-e que procesan los datos para los servidores de la capa 1.
    - **Capa 3**: Servidores de bases de datos que almacenan/buscan/gestionan los datos para los servidores de comercio-e.
  - **Arquitectura Cliente-Cola-Cliente**: Habilita a todos los clientes para desempeñar tareas semejantes interactuando cooperativamente para realizar una actividad distribuida, mientras que el servidor actúa como una cola que va capturando las peticiones de los clientes y sincronizando el funcionamiento del sistema. La arquitectura P2P se basa en el concepto "Cliente-Cola-Cliente". Aplicaciones: Intercambio y búsqueda de ficheros (BitTorrent, eDonkey2000, eMule). Sistemas de telefonía por Internet (Skype).

## Fundamentos Ingeniería de Servidores

**Requisitos funcionales**

  - **Prestaciones (Performance)**: Medida o cuantificación de la velocidad con que se realiza una determinada cantidad de trabajo (carga, workload/load). El servidor que realiza la misma cantidad de trabajo (carga) en el menor tiempo es el que mejor prestaciones tiene. Magnitudes medibles implican índices de prestaciones. Tiempo que tarda un componente o el sistema en realizar una tarea. Número de trabajos realizados por algún componente o por el sistema completo por unidad de tiempo. Medidas fundamentales de prestaciones de un servidor:
    - **Tiempo de respuesta (response time) o latencia (latency)**: Tiempo total desde que se solicita una tarea al servidor o a un componente del mismo y la finalización de la misma. Por ejemplo: Tiempo de ejecución de un programa o tiempo de acceso a un disco.
    - **Productividad (throughput) o ancho de banda (bandwidth)**: Cantidad de trabajo realizado por el servidor o por un componente del mismo por unidad de tiempo. Por ejemplo: Programas ejecutados por hora, páginas por hora servidas por un servidor web, correos por segundo procesados por un servidor de correo...
  - **Disponibilidad (Availability)**: Un servidor está disponible si se encuentra en estado operativo. Tiempo de inactividad (Downtime): cantidad de tiempo en el que
el sistema no está disponible.
