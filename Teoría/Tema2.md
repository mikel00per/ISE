# Componentes HArdware de un Servidor

## Placa base

Una placa base (o placa madre, motherboard, mainboard) es la tarjeta de circuito impreso (PCB) principal de un computador. En ella se conectan los principales componentes del computador y contiene diversos conectores para los distintos periféricos.

**PCB (Printed Circuit Board)**: Están hechas de pistas de cobre rodeadas de láminas de un substrato no conductor (normalmente fibra de vidrio con una resina no inflamable). Las placas base actuales son multi-capa. A través de unos agujeros (vías) podemos conectar las pistas de una capa a otra. Las placas base se suelen fabricar con distintos tamaños y formas (form factors), según distintos estándares: ATX, BTX, EATX, Mini- ITX, etc.

**Componentes de una placa base:**

![placa real]()
![esquema placa]()

**Montaje de los componentes de una placa base**

¡¡Cuidado con las descargas electrostáticas!! (ESD, Electrostatic discharge). Pueden dañar algunos chips de la placa base: conviene descargar la electricidad estática previamente tocando una superficie amplia de metal, usar una muñequera de descarga o guantes especiales.

No tocar nunca ningún contacto metálico de ningún componente de la placa ni de ningún conector. Desconectar el cable de alimentación antes de instalar/quitar cualquier componente. Normalmente un componente o un conector solo puede instalarse de una única manera: no forzar la inserción de componentes/conectores.

**Fuente alimentación**: convierte corriente alterna en corriente continua.
  - Entrada: AC (220v – 50hz)
  - Salidas: DC(±5v, ±12v, ± 3,3v)  
Alimenta tanto la placa base como los periféricos. Potencia: 250w a 1000w.

**Regulador voltaje**: Convierte la corriente continua de la fuente de alimentación en las tensiones continuas que necesitan los diferentes elementos de un computador (CPU, memoria, chipset, etc.) Estos compoenentes son: Capacitores, MOSFET, Transistores etc.

**Disipadores de calor**: Reducen la temperatura de los componentes debido al paso continuo de electricidad.
  - Pasivos: Disipadores
  - Antivos: Ventilladores, refrigeración líquida...

**Zócalos de la CPU (CPU Sockets)**: Facilitan la conexión entre el microprocesador y la placa base de tal forma que el microprocesador pueda ser remplazado sin necesidad de soldaduras.

Los zócalos para micros con un número grande de pines suelen ser del tipo PGA-ZIF (pin grid array - zero-insertion force) o LGA (land grid array), que hacen uso de una pequeña palanca (PGA-ZIF) o una pequeña placa de metal (LGA) para fijar el micro al zócalo. De esta forma, se minimiza el riesgo de que se doble alguna patilla durante el proceso de inserción.

**Interl Xeon**: Son los procesadores de Intel para servidores.

Incorporan más soporte para multiprocesamiento, más memoria caché, mayor número de "tecnologías" y mejores prestaciones, en general, que los procesadores para equipos de sobremesa de la misma generación.

**AMD: EPYC y Opteron**:  Son los procesadores de AMD para servidores.

El primer Opteron, presentado en 2003, fue el primer procesador con el conjunto de instrucciones AMD x86-64. En 2004, los Opteron fueron los primeros procesadores x86 con 2 núcleos. En 2009 presenta Opteron con 6 núcleos. Actualmente hay 3 grandes familias de CPU de AMD para servidores: EPYC, Opteron (X-Series) y Opteron (A-Series).

  - **AMD Opteron X Series**: Es un tipo de “arquitectura de sistema heterogénea” basada en APU (Accelerated Processing Units) que integran CPU y GPU en un mismo chip. GPU: Graphics Processing Unit. Además, también integran la E/S por lo que es un verdadero SoC (System-on-a-chip). Intel también incorpora un controlador gráfico (GPU) en muchos de sus procesadores.
  - **AMD Opteron A Series**: O ARM, en muchos servidores de streaming (Spotify, Youtube, Netflix, etc.) el cuello de botella no está en el procesador. Basados en microprocesadores de ARM (RISC) usados en dispositivos móviles con excelentes ratios prestaciones-consumo. Son SoC (System-on-a-chip) con controladores PCI-e, Ethernet y SATA en el propio chip. Consumos inferiores a 30W.

**IBM POWER**: Performance Optimization With Enhanced RISC. Resultado del trabajo conjunto entre Apple, IBM y Motorola para servidores de gama alta.

**Ranuras para la memoria DRAM**: (Dynamic Random Access Memory), son los conectores en los que se insertan los módulos de memoria principal: R/W, volátil, necesitan refresco, velocidad inferior a SRAM (caché) pero mayor densidad.

**Canales y bancos de memoria DRAM**: Estas ranuras están agrupadas en canales de memoria (memory channels) a los que la CPU puede acceder en paralelo, pudiendo conectarse varios módulos de memoria en cada canal (bancos).

**Rangos de una memoria DRAM**: Cada módulo de memoria está, a su vez, distribuido en rangos de  memoria que no son más que agrupaciones de chips que me  proporcionan una palabra completa de 64 bits (72 bits en caso de  memorias ECC). En el caso de un módulo de un solo rango (single  rank) todos los chips de memoria del módulo se asocian para dar una  palabra de 64 bits (72 si ECC). Notación: 1Rx4 : Módulo de 1 rango con chips de 4 bits (64/4=16chips)

**Almacenamiento permanente**

  - **Discos duros (HDD, Hard Disk Drives)**: Almacenamiento a lo largo de la superficie de unos discos recubiertos de material magnético. Escritura permanente (no volátil). La lectura y escritura se realiza a través de unos cabezales magnéticos controlados por un brazo motor y la ayuda del giro de los discos. Los datos se distribuyen en pistas. Cada pista se subdivide en sectores de 512 bytes. Los sectores se agrupan en clusters lógicos. Tiempos de respuesta (latencias) muy variables: dependen del sector concreto donde esté el cabezal y el sector concreto al que se quiere acceder. Velocidades de rotación más habituales (r.p.m.): 5400, 7200, 10000, 15000.

  - **Unidades de estado sólido (SSD, Solid State Drives)**: Almacenamiento no volátil distribuido en varios circuitos integrados (chips) de memoria flash (=basados en transistores MOSFET de puerta flotante). Acceso aleatorio: mismo tiempo de respuesta (latencia) independientemente de la celda de memoria a la que se quiere acceder. Un controlador se encarga de distribuir la dirección lógica de las celdas de memoria para evitar su desgaste tras múltiples re-escrituras. Tipos de celdas habituales: SLC (Single-level cell), MLC (multi-level cell).

  - **RAID (Redundant Array of Independent Disks)**: Combinan diversas unidades de almacenamiento (normalmente de idénticas características) para generar unidades de almacenamiento lógicas con mayor tolerancia a fallos y/o ancho de banda.
    - **RAID por software**: Creado por el propio sistema operativo.
    - **RAID por hardware**: Mediante una tarjeta específica (hay placas base que ya incluyen un controlador de este tipo).




























-
