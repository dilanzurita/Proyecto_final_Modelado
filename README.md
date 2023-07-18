# Replicación de Bases de Datos en MongoDB con ETL y Visualización de Datos en una Aplicación Web Dockerizada
## Introduccion
La replicación de bases de datos en MongoDB con ETL (Extract, Transform, Load) y la visualización de datos en una aplicación web dockerizada es un enfoque integral que combina varias tecnologías para asegurar la disponibilidad, escalabilidad y eficiencia en el manejo de grandes volúmenes de información. MongoDB, un sistema de gestión de bases de datos NoSQL, permite replicar datos en múltiples nodos, lo que garantiza la redundancia y la tolerancia a fallos. Además, mediante el uso de herramientas de ETL, como MongoDB Connector for BI, es posible extraer datos de diversas fuentes, transformarlos según las necesidades y cargarlos en una base de datos MongoDB replicada. Por último, al dockerizar una aplicación web, se logra encapsular todo el entorno necesario para ejecutarla de manera independiente y escalable, permitiendo visualizar los datos de forma intuitiva y accesible a través de una interfaz web. Esta combinación de técnicas brinda a las organizaciones la capacidad de gestionar eficientemente grandes conjuntos de datos, obtener información valiosa y tomar decisiones basadas en análisis en tiempo real.
## Tecnologías implementadas en el proyecto
- Docker Desktop 23.0.5
- Docker Compose v2.17.3
- Python 3.11.3
- Flask 2.2.5
- UI (Diseño en Front-end)
## Herramientas Utilizadas
- Visual Studio Code 
- Mongo Compass
## Diagrama del Proyecto
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/WhatsApp%20Image%202023-07-18%20at%2010.57.56%20AM.jpeg?raw=true)
## Diagrama a la conexión de la Base de Datos en Mongo
![Diagrama2](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/WhatsApp%20Image%202023-07-18%20at%2010.59.30%20AM.jpeg?raw=true)
## Diagrama de Funcionamiento Replicaset
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/WhatsApp%20Image%202023-07-18%20at%2011.00.49%20AM.jpeg?raw=true)
## Desarrollo
### Puedes descargar el repositorio en tu escritorio para ver el funcionamiento desde tu máquina
### Creacion y configuracion de contenedores entre los cuales tenemos: 
- Bases de datos mongo con replicación 

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura.JPG)
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura2.JPG)
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura3.JPG)

- Shards cuya configuración solo difiere en el puerto, se ha creado shards (a,b,c) 

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura4.JPG)

- Puertos: 
    A = 27022
    B= 27023
    C= 27024

La aplicación se ha levantado mediante flask, para ello se realizó los siguientes métodos:

-	Conexión a la base de datos

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura5.JPG?raw=true)

Se conecta por defecto al puerto 27017 ya que es nuestro router 1 el cual engloba nuestras bases de datos distribuidas.

- Ingreso de datos
Para esto se ha trabajado de la mano con un archivo HTML llamado forms.html el cual se encarga de brindar la interfaz mediante la cual se recopilarán los datos, mientras que nuestra información los procesa con emtodo POST y los envía a nuestras bases de datos 
**App.py**

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/Captura6.JPG?raw=true)

**Form.html** 

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captura7.PNG?raw=true)

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captura8.PNG?raw=true)

-	Buscar un registro 
Para buscar un registro se ha especificado la búsqueda mediante ID proporcionado por el usuario o ID creado por Mongo

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captura9.PNG)
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captua10.PNG?raw=true)

-	Eliminar registro 
Para elminar un registro se realiza mediante ID de mongo para evitar confuciones con ID similares insertados por el usuario 

![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captura11.PNG)
![Diagrama](https://github.com/dilanzurita/Proyecto_final_Modelado/blob/main/img/captura12.PNG)

La replicación de bases de datos con sharding es una técnica avanzada utilizada para mejorar la escalabilidad y el rendimiento en sistemas de bases de datos distribuidos. El sharding, también conocido como particionamiento horizontal, consiste en dividir los datos en fragmentos más pequeños o shards y distribuirlos en múltiples servidores o nodos. Cada shard es una partición independiente con su propio conjunto de datos, lo que permite distribuir la carga de trabajo y evitar cuellos de botella en la base de datos.

En el proceso de replicación con sharding, cada shard se replica en varios servidores para garantizar la alta disponibilidad y la tolerancia a fallos. Esta redundancia permite que, en caso de que un nodo falle, los datos todavía estén accesibles a través de otras réplicas. Además, la replicación mejora el rendimiento al distribuir la carga de lectura entre las réplicas, reduciendo así la latencia y mejorando la capacidad de respuesta del sistema.

La replicación de bases de datos con sharding ofrece ventajas significativas, pero también plantea desafíos. Por un lado, el diseño adecuado del esquema de particionamiento es esencial para garantizar una distribución equitativa de datos y un rendimiento óptimo. Asimismo, la sincronización y consistencia de los datos entre las réplicas pueden ser complejas de manejar, especialmente en entornos de alta concurrencia. Sin embargo, con una implementación cuidadosa y el uso de tecnologías modernas, la replicación con sharding se convierte en una poderosa solución para satisfacer las demandas de aplicaciones y sistemas cada vez más grandes y exigentes en el mundo actual.

## ETL
ETL es un acrónimo que hace referencia a "Extracción, Transformación y Carga" en el contexto del procesamiento de datos. Se trata de un proceso fundamental en el ámbito de la gestión y análisis de datos, especialmente en entornos empresariales y sistemas de inteligencia de negocios (BI). La primera fase, Extracción, implica recopilar datos desde diversas fuentes, como bases de datos, archivos, sistemas en línea, y más, para luego prepararlos para su posterior procesamiento.

**Pasos**
1. Identificar la fuente de datos: Determine la base de datos de la cual deseas extraer los datos. Asegúrate de conocer los detalles de acceso, como la dirección IP o nombre del servidor, el puerto, el nombre de la base de datos y las credenciales de inicio de sesión necesarias para acceder a ella.

2. Seleccionar la herramienta ETL: Elige una herramienta ETL adecuada para tu proyecto. Hay varias opciones disponibles en el mercado, como Apache NiFi, Talend, Microsoft SQL Server Integration Services (SSIS) o Apache Spark.

3. Configurar la conexión de origen: En la herramienta ETL seleccionada, configura la conexión a la base de datos de origen. Proporciona la información requerida, como el tipo de base de datos, dirección del servidor, puerto, nombre de la base de datos y credenciales de acceso.

4. Definir la consulta de extracción: Especifica la consulta SQL o el método de extracción que se utilizará para recuperar los datos de la base de datos de origen. Esto podría ser una consulta simple para obtener todos los registros o una consulta más compleja para filtrar datos específicos.

5. Establecer transformaciones (opcional): Si es necesario, realiza transformaciones en los datos extraídos para adaptarlos al formato requerido en el destino. Estas transformaciones pueden incluir limpieza de datos, conversión de tipos, cálculos, agregaciones, entre otros.

6. Configurar la conexión de destino: Ahora, configura la conexión a la base de datos de destino, donde se cargarán los datos transformados. Proporciona los detalles de acceso y asegúrate de que la estructura de la base de datos de destino coincida con los datos transformados.

7. Definir el proceso de carga: Especifica cómo se cargarán los datos transformados en la base de datos de destino. Puedes optar por una carga completa (siempre reemplazando todos los datos), una carga incremental (solo cargando datos nuevos o modificados desde la última ejecución) o una combinación de ambas.

8. Ejecutar el flujo ETL: Ejecuta el flujo ETL que has configurado. La herramienta ETL se encargará de extraer los datos de la base de datos de origen, aplicar las transformaciones y cargar los datos en la base de datos de destino.

9. Monitorear y mantener el proceso: Supervisa el proceso ETL para asegurarte de que se ejecute correctamente y sin errores. Realiza un mantenimiento regular y ajustes si es necesario, especialmente si hay cambios en las fuentes de datos o en los requisitos de transformación.