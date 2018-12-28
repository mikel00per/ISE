# Monitorización de servicios y programas

## Concepto de Monitor de actividad

 - Carga (workload): conjunto de tareas que ha de realizar un sistema. (= Todo aquello que demande recursos del sistema.)
 - Actividad de un sistema: conjunto de operaciones que se realizan en el sistema como consecuencia de la carga que soporta.

Un sistema informático no es “bueno” ni “malo” per se, sino que se adapta mejor o peor a un tipo determinado de carga. Algunas variables que reflejan la actividad de un sistema:

  - **Procesadores**: Utilización, temp., f CLK , no de procesos, no de interrupciones, cambios de contexto, etc.
  - **Memoria**: no de accesos, memoria utilizada, fallos de caché, fallos de página, uso de memoria de intercambio, latencias, anchos de banda, voltajes, etc.
  - **Discos**: lecturas/escrituras por unidad de tiempo, longitud de las colas de espera, tiempo de espera medio por acceso, etc.
  - **Red**: paquetes recibidos/enviados, colisiones por segundo, sockets abiertos, paquetes perdidos, etc.
  - **Sistema global**: no de usuarios, no de peticiones, etc.

**Monitor de actividad**: Herramienta diseñada para medir la actividad de un sistema informático y facilitar su análisis. Las acciones típicas deun monitor:
  - Medir la actividad.
  - Procesar y almacenar la información recopilada.
  - Mostrar los resultados.

**Utilidad de los monitores** según el punto de vista de cada ente:
  - **Administrador/Ingeniero**:
    - Conocer la utilización de los recursos (detección de cuellos de botella) para saber: Qué hardware hay que reconfigurar / sustituir/ añadir. Cómo ajustar los parámetros del sistema (sintonización).
    - Predecir cargas futuras (capacity planning).
    - Tarificar a los clientes.
    - Obtener un modelo un componente o de todo el sistema para poder deducir qué pasaría si...
  - **Programador**: Conocer las partes críticas de una aplicación de cara a su optimización.
  - **Sistema Operativo**: Adaptarse dinámicamente a la carga.

**Tipos de monitores**:

  - **Por eventos**: Evento: Cambio en el estado del sistema. Volumen de información recogida: Depende de la frecuencia de los eventos. Información exacta. Ejem.: Inicio/fin de la ejecución de un programa, fallo en memoria cache, interrupción de un dispositivo periférico.

  - **Por muestreo** (A intervalos regulares de tiempo): Volumen de información recogida: Depende del periodo de muestreo (T). Información estadística.

  - **Software**: Programas instalados en el sistema.
  - **Hardware**: Dispositivos físicos de medida (menor sobrecarga)
  - **Híbridos**: Utiliza los dos tipos anteriores

**¿Existe interacción con el analista/administrador?**
  - **Sí existe**. Durante el propio proceso de monitorización se pueden consultar los valores monitorizados y/o interactuar con ellos realizando representaciones gráficas diversas, modificando parámetros del propio monitor, etc.: monitores en primer plano o interactivos (on-line monitors).

  - **No existe**. La consulta sobre los resultados se realiza aparte mediante otra herramienta independiente al proceso de monitorización: monitores tipo batch, por lotes o en segundo plano (batch monitors).

**Atributos que caracterizan a un sensor/monitor**:
  - **Exactitud** de la medida (Accuracy, offset): ¿Cómo se aleja el valor medido del valor real que se quiere medir?
  - **Precisión** (Precision): ¿Cuál es la dispersión de las medidas?
  - **Resolución del sensor**: ¿Cuánto tiene que cambiar el valor a medir para detectar un cambio?
  - **Tasa Máxima de Entrada** (Max Input Rate): ¿Cuál es la frecuencia máxima de ocurrencia de los eventos que el monitor puede observar? (monitores por eventos)
  - **Periodo de Muestreo** (Sampling Time): ¿Cada cuánto tiempo tomamos la medida? (monitores por muestreo)
  - **Anchura de Entrada** (Input Width): ¿Cuánta información (no de bytes de datos) se almacena por cada medida que toma el monitor?
  - **Sobrecarga (Overhead)**: ¿Qué recursos le “roba” el monitor al sistema? El instrumento de medida puede perturbar el funcionamiento del sistema.

![img](http://latex.codecogs.com/svg.latex?%5Cfrac%7B%5Csigma%7D%7B%5Cmu%7D)

  ```
  $x-y$
  ```
































 -
