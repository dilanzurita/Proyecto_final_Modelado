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

![Diagrama]()
![Diagrama]()